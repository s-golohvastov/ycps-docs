---
external help file: yc.compute.dll-Help.xml
Module Name: ycps
online version:
schema: 2.0.0
---

# Get-YcVM

## SYNOPSIS
Получение данных о виртуальной машине в облаке

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
Команда предназначена для получения детальной информации о виртуальной машине в облаке.

## EXAMPLES

### Example 1
```powershell
Get-YcVM -FolderId "folder_id"
```

Получить список всех виртуальных машин в указанном каталоге

### Example 2
```powershell
Get-YcVM -InstanceId "instance_id"
```

Получить виртуальную машину по ее идентификатору

### Example 3
```powershell
Get-YcVM -FolderId "folder_id" -InstanceName "test-vm"
```

Получить виртуальную машину из указанного каталога по имени

### Example 4
```powershell
$cloudId = "cloud_id"
$vm = Get-YcCloud -CloudId $cloudId | Get-YcFolder | Get-YcVM
```

Получить виртуальные машины из облака с идентификатором "cloud_id", по всем каталогам этого облака

## PARAMETERS

### -Folder
Объект каталога, возвращаемый командой Get-YcFolder

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
Идентификатор каталога

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
Идентификатор виртуальной машины

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
Имя виртуальной машины

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
