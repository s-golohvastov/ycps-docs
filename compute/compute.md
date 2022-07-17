# Обзор

Команды управления виртуальными машинами.

Аутентифицируемся в облаке

```powershell
Connect-YcAccount -OAuthToken "FDFJFUEVPEFWEFHDVJKSB=="
```

## Получение информации о виртуальных машинах

Начнем с получения списка облаков

```powershell
Get-YcCloud | Format-Table -AutoSize
```

```console
Id                   CreatedAt              Name                Description OrganizationId       
--                   ---------              ----                ----------- --------------       
b2glq9sffsdfdfsghqt0 "2022-06-12T21:12:55Z" test-org-cloud                  bpfsdfdfdsfdsfdsffse
b3g6sfdfdfsdfdsfdt2l "2021-01-04T17:11:39Z" cloud-stuff                                  
```

Теперь можно найти каталоги, в одном из облаков

```powershell
Get-YcFolder -CloudId b3g6sfdfdfsdfdsfdt2l | Format-Table -AutoSize
```

```console
Id                   CloudId              CreatedAt              Name    Description Labels Status
--                   -------              ---------              ----    ----------- ------ ------
b2dfsdfdfsdfdfdfdsf3 b3g6sfdfdfsdfdsfdt2l "2021-01-04T17:11:39Z" default             {}     Active
```

ну и поскольку мы знаем каталог, можно посмотреть все виртуальные машины в этом каталоге

```powershell
Get-YcFolder -CloudId b3g6sfdfdfsdfdsfdt2l | Get-YcVM | Format-Table -AutoSize
```

```console
Id                   FolderId             CreatedAt              Name   Description Labels ZoneId        PlatformId  Resources                                                       Status
--                   --------             ---------              ----   ----------- ------ ------        ----------  ---------                                                       ------
fhmdsdfdsfsdfdsfdsfs b2dsfdfsdsfdsfdsfsdf "2022-06-03T01:43:26Z" ya-vm  vm          {}     ru-central1-a standard-v3 { "memory": "2147483648", "cores": "2", "coreFraction": "50" } Stopped
```

## Создание виртуальных машин

Для создания простой виртуальной машины с одним диском нам нужно знать:

* Размер машины - количество ядер и памяти, параметры загрузочного диска и образа, из которого будет создана машина
* Платформу, а проще говоря тип процессора, на котором она будет исполняться
* Зону, или регион, в котором ее запустить
* Каталог, где она будет храниться
* Сеть и подсеть, к которой ее нужно подключить

Подготовим некоторые параметры. Для простоты будем предполагать чо мы их получили предыдущими командами:

```powershell
$testFolderId = "<some_folder_id>"
$platformId = "standard-v1"
$zoneId = "ru-central1-a"
$subnetId = "<some_subnet_id>"
```

Теперь нужно указать размеры виртуальной машины

```powershell
$vmSpec = New-YcVmSpecification -Memory 4GB -Cores 4 -CoreFraction 5
```

Так же укажем параметры загрузочного диска, и образ:

```powershell
$bootDisk = New-YcDiskSpecification -Name "boot01" `
                                    -Size (32GB) `
                                    -TypeId "network-hdd" `
                                    -BlockSize 8192 `
                                    -ImageId (Get-YcVmImage -Family "ubuntu-2004-lts").id
```

Тут мы используем команду `Get-YcVmImage`, которая позволяет получить самый новый образ из "семьи" образов

Поскольку мы создаем виртуальную машину на основе Linux, необходимо предоставить `ssh` ключ, который будет использоваться для подключения к ней. Ключ нам необходимо передаь как метаданные при создании машины:

```powershell
$sshKey = get-content "C:\temp\.ssh\testkey.pub"
$vm = New-YcVm -Name "test-vm-from-pester" `
               -FolderId $testFolderId `
               -ZoneId $zoneId `
               -Platform $platformId `
               -SubnetId $subnetId `
               -ResourceSpec $vmSpec `
               -BootDiskSpec $bootDisk `
               -Metadata @{"ssh-key" = $sshKey }
```

Результатом исполнения команды будет виртуальная машина с одним диском. Чтобы создать виртуальную машину с несколькими дисками, можно поступить следующим образом:

```powershell
$dataDisk = New-YcDiskSpecification -Name "data01" -Size (32GB) -TypeId "network-hdd" -BlockSize 8192
$dataDisk2 = New-YcDiskSpecification -Name "data02" -Size (32GB) -TypeId "network-hdd" -BlockSize 8192

$vm = New-YcVm -Name "test-vm-from-pester" `
               -FolderId $testFolderId `
               -ZoneId $zoneId `
               -Platform $platformId `
               -SubnetId $subnetId `
               -ResourceSpec $vmSpec `
               -BootDiskSpec $bootDisk `
               -Metadata @{ "ssh-keys" = "ycuser:$sshKey"; "serial-port-enable" = "1" } `
               -DataDiskSpec ($dataDisk, $dataDisk2)
```

Здесь, в качестве параметра `DataDiskSpec` можно передать массив дисков.