# API

Можно получать данные из базы данных сервера через HTTP API. Все данные возвращаются в JSON.
На данный момент доступно только 4 метода.

```lua title="Пример запроса к API на MoonLoader с использованием lua-requests"
local requests = require('requests')

function getUserInfo(nickname)
  local requestUrl = 'https://training-server.com/api/user/' .. nickname
  local response = requests.get(requestUrl)

  return response
end

local userInfo = getUserInfo('T0P4')
print(userInfo)
```

```py title="Пример запроса к API на Python"
from requests import get


def get_user_info(nickname: str) -> dict:
    request_url = 'https://training-server.com/api/user/' + nickname
    response = get(request_url)
    return response.json()

user_info = get_user_info('T0P4')
print(user_info)
```

## `/api/user/login`

Возвращает данные об игроке по его логину. Пример: **[/api/user/T0P4](https://training-server.com/api/user/T0P4)**

### Возвращаемые данные

| параметр     | описание                                                          | пример                                                                         |
|--------------|-------------------------------------------------------------------|--------------------------------------------------------------------------------|
| `id`         | ID аккаунта                                                       | `556588`                                                                       |
| `login`      | никнейм аккаунта                                                  | `T0P4`                                                                         |
| `access`     | VIP доступ                                                        | `0`                                                                            |
| `moder`      | уровень модератора                                                | `0`                                                                            |
| `verify`     | верификация. `5` если вечный VIP                                  | `5`                                                                            |
| `verifyText` | текст верификации                                                 | `"спонсор сервера"`                                                            |
| `mute`       | мут. если есть - указан timestamp окончания мута. если нету - `0` | `0`                                                                            |
| `online`     | `1` если аккаунт в сети, `0` если нет                             | `0`                                                                            |
| `playerid`   | ID игрока на сервере. `0` если офлайн                             | `0`                                                                            |
| `regdate`    | дата регистрации                                                  | `"2023-01-08 10:14:0"`                                                         |
| `lastlogin`  | дата последней авторизации                                        | `"2023-04-15 15:45:20"`                                                        |
| `warn`       | список предупреждений                                             | `[{"reason":"непослушание","admin":"Haiser","bantime":"2021-01-07 01:24:07"}]` |


### Пример ответа (JSON)
```
{
  "data": {
    "id": 556588,
    "login": "T0P4",
    "access": 0,
    "moder": 0,
    "verify": 5,
    "verifyText": "спонсор сервера",
    "mute": 0,
    "online": 0,
    "playerid": 0,
    "regdate": "2023-01-08 10:14:05",
    "lastlogin": "2023-04-15 15:45:20",
    "warn": []
  }
}
```

## `/api/user`

Возвращает список игроков сервера длиной до 100 игроков на одну страницу. Пример: **[/api/user](https://training-server.com/api/user)**

### Параметры запроса

| тип   | параметр | описание        | пример             |
|-------|----------|-----------------|--------------------|
| `GET` | `page`   | страница списка | `/api/user?page=3` |

### Возвращаемые данные

[/api/user/login > Возвращаемые данные](#_1)

### Пример ответа (JSON)

```
{
  "data": [
    {
      "id": 578966,
      "login": "auro",
      ...
    },
    {
      "id": 578965,
      "login": "3BYK",
      ...
    }
  ]
}
```

## `/api/online`

Возвращает список игроков, которые на данный момент находятся онлайн на сервере. Пример: **[/api/user](https://training-server.com/api/online)**

### Возвращаемые данные

[/api/user/login > Возвращаемые данные](#_1)

### Пример ответа (JSON)

[/api/user > Пример ответа](#json_1)

## `/api/admin`

Возвращает список состоящий из всех модераторов сервера. Пример: **[/api/admin](https://training-server.com/api/admin)**

### Возвращаемые данные

| параметр    | описание                        | пример       |
|-------------|---------------------------------|--------------|
| `id`        | ID аккаунта                     | `85405`      |
| `login`     | никнейм аккаунта                | `"Sog"`      |
| `lastLogin` | timestamp последней авторизации | `1681566388` |
| `warn`      | кол-во выданных варнов          | `2868`       |

### Пример ответа (JSON)

```
[
  {
    "id": 85405,
    "login": "Sog",
    "lastLogin": 1681566388,
    "warn": 2868
  },
  {
    "id": 44012,
    "login": "sciden",
    "lastLogin": 1681504620,
    "warn": 1657
  },
  {
    "id": 17212,
    "login": "orangefest",
    "lastLogin": 1681380559,
    "warn": 1134
  }
]
```