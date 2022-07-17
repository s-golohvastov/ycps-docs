---
external help file: yc.compute.dll-Help.xml
Module Name: ycps
online version:
schema: 2.0.0
---

# New-YcVM

## SYNOPSIS
Создание новой виртуальной машины в облаке

## SYNTAX

```
New-YcVM -Name <String> -FolderId <String> -ZoneId <String> -PlatformId <String> -SubnetId <String>
 -ResourceSpec <ResourcesSpec> -BootDiskSpec <AttachedDiskSpec> [-DataDiskSpec <AttachedDiskSpec>]
 [-Metadata <Hashtable>] [<CommonParameters>]
```

## DESCRIPTION
Создание новой виртуальный машины в облаке. Команда выполняется синхронно, то есть ожидает окончания создания машины и возвращает объект машины

## EXAMPLES

### Example 1
```powershell
$testFolderId = "SOME_FOLDER_ID"
$platformId = "standard-v1"
$zoneId = "ru-central1-a"
$subnetId = "SOME_SUBNET_ID"

$vmSpec = New-YcVmSpecification -Memory 4GB -Cores 4 -CoreFraction 5
$bootDisk = New-YcDiskSpecification -Name "boot01" -Size (32GB) -TypeId "network-hdd" -BlockSize 8192 -ImageId (Get-YcVmImage -Family "ubuntu-2004-lts").id
$vm = New-YcVm -Name "test-vm-from-pester" -FolderId $testFolderId -ZoneId $zoneId -Platform $platformId -SubnetId $subnetId -ResourceSpec $vmSpec -BootDiskSpec $bootDisk
```

Скрипт создает виртуальную машину и возвращает ее объект после того, как она создана

## PARAMETERS

### -BootDiskSpec
Объект диска, который будет использоваться для старта ВМ. Должен быть создан из образа

```yaml
Type: AttachedDiskSpec
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataDiskSpec
Объект диска, который будет подключен как диск для данных

```yaml
Type: AttachedDiskSpec
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FolderId
Папка, в которой следует создать ВМ

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metadata
Объект метаданных. Один из сценариев использования - задание пароля или ssh ключа для входа в систему

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Имя виртуальной машины

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlatformId
Тип аппратной платформы виртуальной машины

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceSpec
Объект конфигурации, задающий размер ВМ

```yaml
Type: ResourcesSpec
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
Идентификатор подсети виртуальной машины

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ZoneId
Зона доступности ВМ

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
