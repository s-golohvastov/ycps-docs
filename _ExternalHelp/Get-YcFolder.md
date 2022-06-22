---
external help file: yc.resmgr.dll-Help.xml
Module Name: ycps
online version:
schema: 2.0.0
---

# Get-YcFolder

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### CloudId (Default)
```
Get-YcFolder -CloudId <String> [<CommonParameters>]
```

### FolderId
```
Get-YcFolder [-FolderId <String>] [<CommonParameters>]
```

### Cloud
```
Get-YcFolder -Cloud <Cloud[]> [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -Cloud
{{ Fill Cloud Description }}

```yaml
Type: Cloud[]
Parameter Sets: Cloud
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CloudId
{{ Fill CloudId Description }}

```yaml
Type: String
Parameter Sets: CloudId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -FolderId
{{ Fill FolderId Description }}

```yaml
Type: String
Parameter Sets: FolderId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Yandex.Cloud.Resourcemanager.V1.Cloud[]

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
