# ТекстДравы

## Префабы

### Horizontal progress bar (by lester)
![Progress bar](https://i.imgur.com/w2gwa17.png "Progress bar")

|Описание|Бокс/Текст|Строка|
|:--------------------------|:-----|:----------------------------------------------------------|
|`Background`|Бокс|id 320 400 105 5 0xFF000000 2 0|
|`Progress bar background`|Бокс|id 320 402 100 2.5 0xFFFF101015 2 0|
|`Progress bar`|Бокс|id #floatnum(273 + value)# 402 267 2.5 0xFFC0C0C0 3 0|
|||value - переменная/массив от 0 до 100|
|||Условие: если value < 1 - скрывать текстдрав|
|||0xFFC0C0C0 - цвет прогресс бара|
|`Counter` (по желанию)|Текст|id 3 263 396.5 10 10 1 0.4 1.3 -1 FF000000 2 0 1 0 -1 value|


### Vertical progress bar (by lester)
![Progress bar](https://i.imgur.com/VIJM74o.png "Progress bar")

|Описание|Бокс/Текст|Строка|
|:--------------------------|:-----|:----------------------------------------------------------|
|`Background`|Бокс|id 615 336 40 85 FF050505 2 0 0 -1|
|`Progress bar background`|Бокс|id 615 339 35 80 FF282828 2 0 0 -1|
|`Progress bar`|Бокс|id 615 443 35 -(#floatnum(value * 80)#+6) FF00A5FF 2 0 0 -1|
|||value - переменная/массив от 0 до 100|
|||Условие: если value < 1 - скрывать текстдрав|
|||FF00A55FF - цвет прогресс бара|
|`Icon` (по желанию)|Бокс|id 606 390 20 20 -1 2 2 0 -1 HUD:radar_burgerShot|
|`Counter` (по желанию)|Текст|id 616 411 20 20 3 0.5 1.5 -1 FF000000 2 0 2 0 -1 value|
