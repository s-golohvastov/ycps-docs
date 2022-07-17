# Общая информация

Модуль предназначен для работы с Яндекс Облаком средствами PowerShell. Для этого использется GRPC API, предоставляемые Облаком.

Модуль устанавливается из PowerShel gallery обычным способом. На данный момент молуль находится в стадии `preview`, поскольку все еще в разработке, поэтому устанавливаем `prerelease` версию.

```powershell
Install-Module -Name ycps -AllowPrerelease
```

Посмотреть команды, предоставляемые модулем можно командой

```powershell
Get-Command -Module ycps
```

```console
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Connect-YcAccount                                  0.0.1      ycps
Cmdlet          Get-YcCloud                                        0.0.1      ycps
Cmdlet          Get-YcDiskType                                     0.0.1      ycps
Cmdlet          Get-YcFolder                                       0.0.1      ycps
Cmdlet          Get-YcOrganization                                 0.0.1      ycps
Cmdlet          Get-YcSubnet                                       0.0.1      ycps
Cmdlet          Get-YcVM                                           0.0.1      ycps
Cmdlet          Get-YcVmImage                                      0.0.1      ycps
Cmdlet          Get-YcVpc                                          0.0.1      ycps
Cmdlet          Get-YcZone                                         0.0.1      ycps
Cmdlet          New-YcAttachedDiskSpecification                    0.0.1      ycps
Cmdlet          New-YcDiskSpecification                            0.0.1      ycps
Cmdlet          New-YcSubnet                                       0.0.1      ycps
Cmdlet          New-YcVM                                           0.0.1      ycps
Cmdlet          New-YcVmSpecification                              0.0.1      ycps
Cmdlet          New-YcVpc                                          0.0.1      ycps
Cmdlet          Remove-YcVM                                        0.0.1      ycps
Cmdlet          Remove-YcVpc                                       0.0.1      ycps
Cmdlet          Start-YcVm                                         0.0.1      ycps
Cmdlet          Stop-YcVm                                          0.0.1      ycps
```

После установки необходимо авторизоваться облаке, командой `Connect-YcAccount`:

```powershell
Connect-YcAccount -OAuthToken "jfgfkjgbdkjgbdkfgbkdfbdkfbkjfdb"
```

После этого можно выполнять другие команды, например подучить список облаков, связанных с вашей учетной записью:

```powershell
Get-YcCloud
```

или список всех каталогов облака:

```powershell
$testCloudId = "cloud_id_одного_из_облаков"
Get-YcFolder -CloudId $testCloudId | Get-YcFolder
```

ну и наконец, список всех виртуальных машил в этом каталоге:

```powershell
$testCloudId = "cloud_id_одного_из_облаков"
Get-YcCloud -CloudId $testCloudId | Get-YcFolder | Get-YcVM
```

Исходный код модуля [тут](https://github.com/s-golohvastov/ycps)
