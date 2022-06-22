---
external help file: yc.vpc.dll-Help.xml
Module Name: ycps
online version:
schema: 2.0.0
---

# Get-YcSubnet

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### FolderId (Default)
```
Get-YcSubnet -FolderId <String> [<CommonParameters>]
```

### FolderIdNameFiler
```
Get-YcSubnet -FolderId <String> [-SubnetName <String>] [<CommonParameters>]
```

### FolderObj
```
Get-YcSubnet -FolderObj <Folder> [<CommonParameters>]
```

### FolderObjNameFiler
```
Get-YcSubnet -FolderObj <Folder> [-SubnetName <String>] [<CommonParameters>]
```

### SubnetId
```
Get-YcSubnet -SubnetId <String> [<CommonParameters>]
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

### -FolderId
{{ Fill FolderId Description }}

```yaml
Type: String
Parameter Sets: FolderId, FolderIdNameFiler
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FolderObj
{{ Fill FolderObj Description }}

```yaml
Type: Folder
Parameter Sets: FolderObj, FolderObjNameFiler
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SubnetId
{{ Fill SubnetId Description }}

```yaml
Type: String
Parameter Sets: SubnetId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
{{ Fill SubnetName Description }}

```yaml
Type: String
Parameter Sets: FolderIdNameFiler, FolderObjNameFiler
Aliases: Name

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Yandex.Cloud.Resourcemanager.V1.Folder

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
