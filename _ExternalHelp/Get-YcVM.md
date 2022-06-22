---
external help file: yc.compute.dll-Help.xml
Module Name: ycps
online version:
schema: 2.0.0
---

# Get-YcVM

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### AllInFolderId (Default)
```
Get-YcVM -FolderId <String> [<CommonParameters>]
```

### FilterByInstanceName
```
Get-YcVM -FolderId <String> -InstanceName <String> [<CommonParameters>]
```

### AllInFolderObj
```
Get-YcVM -Folder <Folder> [<CommonParameters>]
```

### FilterFolderObjByInstanceName
```
Get-YcVM -Folder <Folder> -InstanceName <String> [<CommonParameters>]
```

### ByInstanceId
```
Get-YcVM [-InstanceId <String>] [<CommonParameters>]
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

### -Folder
{{ Fill Folder Description }}

```yaml
Type: Folder
Parameter Sets: AllInFolderObj, FilterFolderObjByInstanceName
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
Parameter Sets: AllInFolderId, FilterByInstanceName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId
{{ Fill InstanceId Description }}

```yaml
Type: String
Parameter Sets: ByInstanceId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceName
{{ Fill InstanceName Description }}

```yaml
Type: String
Parameter Sets: FilterByInstanceName, FilterFolderObjByInstanceName
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

### Yandex.Cloud.Resourcemanager.V1.Folder

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
