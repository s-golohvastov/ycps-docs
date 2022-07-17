---
external help file: yc.connect.dll-Help.xml
Module Name: ycps
online version:
schema: 2.0.0
---

# Connect-YcAccount

## SYNOPSIS
Команда для аутентификации в облаке

## SYNTAX

```powershell
Connect-YcAccount -OAuthToken <String> [<CommonParameters>]
```

## DESCRIPTION
Команда для аутентификации в облаке. Получает на вход OAuth токен и "обменивает" его на IAM токен, который, в свою очередь, используется далее для авторизации на ресурсах. Ни OAuth ни IAM не сохраняются на файловой системе. Они сужествуют только в рамказ PowerShell сессии в которой вызвался командлет

## EXAMPLES

### Example 1
```powershell
Connect-YcAccount -OAuthToken "jfgfkjgbdkjgbdkfgbkdfbdkfbkjfdb"
```

Команда аутентифицирует текущую PowerShell сессию в облаке

## PARAMETERS

### -OAuthToken
OAuth токен Яндекс Облака

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
