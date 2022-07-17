---
external help file: yc.compute.dll-Help.xml
Module Name: ycps
online version:
schema: 2.0.0
---

# New-YcDiskSpecification

## SYNOPSIS
Возвращает объект конфигурации диска виртуальной машины

## SYNTAX

```
New-YcDiskSpecification -Name <String> [-Description <String>] [-TypeId <String>] -Size <Int64>
 [-Blocksize <Int32>] [-Autodelete <Boolean>] -ImageId <String> [<CommonParameters>]
```

## DESCRIPTION
Возвращает объект конфигурации диска виртуальной машины

## EXAMPLES

### Example 1
```powershell
PS C:\> New-YcDiskSpecification -Name "boot01" -Size (32GB) -TypeId "network-hdd" -BlockSize 8192 -ImageId (Get-YcVmImage -Family "ubuntu-2004-lts").id
```

Создает конфигурацию диска для виртуальной машины, размером 32GB, типа network-hdd. Зоздается загрузочный диск, поэтому указываем идентификатор образа, используемого для создания виртуальной машины

## PARAMETERS

### -Autodelete
Удалять или не удалять диск при удалении ВМ

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Blocksize
Размер блока диска в байтах

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Описание

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageId
Идентификатор образа диска, который будет являться базовым для этого диска

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

### -Name
Имя диска

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

### -Size
Размер в байтах

```yaml
Type: Int64
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TypeId
Тип диска

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
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
