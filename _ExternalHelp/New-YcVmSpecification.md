---
external help file: yc.compute.dll-Help.xml
Module Name: ycps
online version:
schema: 2.0.0
---

# New-YcVmSpecification

## SYNOPSIS
Создание объекта, описывающего конфигурацию виртуальной машины

## SYNTAX

```
New-YcVmSpecification -Memory <Int64> -Cores <Int32> [-CoreFraction <Int32>] [-Gpus <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
Создание объекта, описывающего конфигурацию виртуальной машины. Объект задает объем памяти? количество ядер, уровень потребления (CoreFraction), количество GPUs

## EXAMPLES

### Example 1
```powershell
PS C:\> New-YcVmSpecification -Memory 4GB -Cores 4 -CoreFraction 5
```

Возвращает объект, содержащий конфигурацию виртуальной машины с 4GB RAM, 4 ядрами и 5% уровнем потребления

## PARAMETERS

### -CoreFraction
Задает максимальный процент потребления ресурсов виртуальной машины

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

### -Cores
Задает количество ядер для виртуальной машины

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Gpus
Задает количество GPU ядер для виртуальной машины

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

### -Memory
Задает количество оперативной памяти виртуальной машины

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
