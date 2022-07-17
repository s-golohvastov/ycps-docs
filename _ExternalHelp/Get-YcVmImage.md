---
external help file: yc.compute.dll-Help.xml
Module Name: ycps
online version:
schema: 2.0.0
---

# Get-YcVmImage

## SYNOPSIS
Получает информацию об опубликованных образах виртуальных машин

## SYNTAX

### ByFolderId (Default)
```
Get-YcVmImage [-FolderId <String>] [<CommonParameters>]
```

### LatestByFamily
```
Get-YcVmImage [-FolderId <String>] -Family <String> [<CommonParameters>]
```

## DESCRIPTION
Получает информацию об опубликованных образах виртуальных машин. Можно получить список всех образов, образов из определенной папки или самый новый образ из семейства образов

## EXAMPLES

### Example 1
```powershell
PS C:\> Get-YcVmImage -Family "ubuntu-2004-lts"
```

Получить самы новый образ из семейства образов ubuntu-2004-lts

## PARAMETERS

### -Family
Идентификатор семейства образов

```yaml
Type: String
Parameter Sets: LatestByFamily
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FolderId
Идентификатор папки, в которой содержатся образы

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
