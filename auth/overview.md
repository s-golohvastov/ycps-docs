# Общая информация

Прежде чем начать работать с облаком, необходимо аутентифицироваться в облаке. Сделать это, на данный момент, можно при помощи [OAuth токена](https://cloud.yandex.ru/docs/iam/concepts/authorization/oauth-token), который можно [получить](https://oauth.yandex.ru/authorize?response_type=token&client_id=1a6990aa636648e9b2ef855fa7bec2fb) у самого Яндекса. Затем этот токен необходимо передать команде, и она "обменяет" его на IAM токен, который и будет использоваться во всех последующих запросах в облако. Оба эти токена существуют только в рамках PowerShell сессии, при ее закрытии, необходимо аутентифицироваться повторно.

Пример использования команды:

```powershell
Connect-YcAccount -OAuthToken "jfgfkjgbdkjgbdkfgbkdfbdkfbkjfdb"
```
