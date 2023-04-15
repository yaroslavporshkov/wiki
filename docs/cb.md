# КБ

Командные блоки позволяют игрокам создавать уникальный функционал и расширять возможности игровых миров.

## Базовая работа с КБ

Команды:

|команда|описание|
|:----|:----|
|`/cb`|создать командный блок|
|`/cbdell`|удалить командный блок|
|`/cbtp`|телепортироваться к командному блоку|
|`/cbedit`|редактировать командный блок|
|`/cblist`|список всех командных блоков в мире|
|`/cmb` `//`|активировать аллиас командного блока|
|`/oldcb`|включить старый движок текстовых команд|
|`/timers`|управление таймерами мира|
|`/tb`|управление триггер блоками в мире|
|`/sb`|создать свитч блок|
|`/sbedit`|редактировать свитч блок|
|`/sbdell`|удалить свитч блок|
|`/shopmenu`|управление магазинами мира для командных блоков|
|`/data`|информация об игроке, его деньгах, очках и значений массивов|
|`/setdata`|установить значение массива игроку|
|`/server`|посмотреть значения серверных массивов мира|
|`/setserver`|установить значение серверному массиву|
|`/varlist`|управление переменными мира|
|`/pvarlist`|управление пользовательскими переменными мира|
|`/pvar`|редактировать значение текстовых переменных игрока|
    
## Текстовые функции

??? abstract "Список текстовых функций"

    |функция|описание|
    |:----|:----|
    |`#playerID#`|вернет ID игрока.|
    |`#array(slot, *playerID)#`|вернуть массив (СЛОТ: 0-26) игрока. *playerID - необязательный параметр, но если указываете то обратите внимание на ЗАПЯТУЮ.|
    |`#server(slot)#`|вернуть массив сервера (СЛОТ: 0-49)|
    |`#var(name)#`|вернуть переменную мира, из /varlist|
    |`#pvar(name, *playerID)#`|вернуть переменную игрока, из /pvarlist|
    |`#teamOnline(teamID)#`|вернуть онлайн команды (/team) по teamID|
    |`#online#`|вернуть онлайн мира|
    |`#anim(*playerID)#`|вернуть числовой индекс активной анимации игрока|
    |`#skin(*playerID)#`|вернуть модель скина игрока|
    |`#acID(*playerID)#`|глобальный ID игрока|
    |`#gun(*playerID)# or #weapon(*playerID)#`|ID оружия игрока|
    |`#ammo(*playerID)#`|кол-во патронов в активном слоте оружия игрока|
    |`#timestamp#`|секунды|
    |`#team(*playerID)#`|вернуть ID команды (/team) игрока|
    |`#score(*playerID)#`|вернуть кол-во очков в TABe игрока|
    |`#money(*playerID)#`|вернуть кол-во грошей игрока|
    |`#health(*playerID)#`|вернуть уровень здоровья игрока|
    |`#armour(*playerID)#`|вернуть уровень брони игрока|
    |`#name(*playerID)#`|вернуть никнэйм игрока по playerID|
    |`#xyz(*playerID)# #x(*playerID)# #y(*playerID)# #z(*playerID)#`|вернуть позицию игрока|
    |`#speed(*playerID)#`|скорость игрока|
    |`#gunName(*playerID)#`|вернуть названия оружия в активном слоте игрока|
    |`#time#`|вернуть время мира|
    |`#weather#`|вернуть погоду мира|
    |`#drunk(*playerID)#`|вернуть ур. опьянения игрока|
    |`#channel(*playerID)#`|вернуть канал игрока (/channel)|
    |`#vehSeat(*playerID)#`|вернуть место игрока в авто|
    |`#waterlvl(*playerID)#`|вернуть уровень нахождения игрока в море|
    |`#zone(*playerID)#`|название района игрока|
    |`#getzone(x, y)#`|названия района по x, y|
    |`#getzoneID(x, y)#`|ID района по x, y (исп. в проверке на район в КБ)|
    |`#ping(*playerID)#`|пинг игрока|
    |`#ban(*playerID)#`|есть ли варн у игрока (0/1)|
    |`#netstat(*playerID)#`|процент потери пакетов|
    |`#hr(*playerID)#`|соотношение попаданий к выстрелам (процент попаданий)|
    |`#fa(*playerID)#`|угол поворота игрока|
    |`#afk(*playerID)#`|кол-во секунд AFK игрока|
    |`#death(*playerID)#`|кол-во секунд стадии смерти (РП) игрока|
    |`#target(*playerID)#`|вернет ид игрока на которого наведен игрок с помощью ПКМ (если игрока нет то вернет 65535)|
    |`#teamName(*playerID)#`|название команды игрока|
    |`#ext(blockID value)#`|вернет строку значения командного блока|
    |`#bodypart(*playerID)#`|-|
    |`#issuerGun(*playerID)#`|-|
    |`#GetDistPlayer(targetID, *playerID)#`|вернет дистанцию к targetID|
    |`#GetDistPos(x y z *playerID)#`|вернет дистанцию к позиции x y z|
    |`#nearply(*playerID)#`|-|
    |`#getZ(x y)#`|-|
    |`#retval(ID, *playerID)#`|-|
    |`#retstr(*ID, **playerID)#`|-|
    |`#GetDist(x1 y1 z1 ×2 y2 z2)#`|-|
    |`#randomPlayer(*category)#     list: team <ID>, skin <ID>, veh <ID>, data <slot> <value>, wanted <value>, action                                                   <ID>, dead, alive`|-|
    |`#moder(*playerID)#`|ур. модерки игрока в мире (хост - 999)|
    |`#specState(*playerID)#`|-|
    |`#specTarget(*playerID)#`|-|
    |`#int(*playerID)#`|интерьер игрока|
    |`#vip(*playerID)#`|-|
    |`#raycast(cam/pos dist col coord)#`|-|
    |`#chatStyle(*playerID)#`|-|
    |`#freeze(*playerID)#`|-|
    |`#freezeTime(*playerID)#`|-|
    |`#gm(*playerID)#`|-|
    |`#mute(*playerID)#`|-|
    |`#muteTime(*playerID)#`|-|
    |`#taser(*playerID)#`|-|
    |`#lastActor(*playerID)#`|-|
    |`#clist(*playerID)#`|-|
    |`#fightStyle(*playerID)#`|-|
    |`#isWorld(playerID)#`|-|
    |`#pame(slot, *playerID)#`|вернет строку /pame игрока из слота|
    |`#customRaycast(x y z angle dist 0/1 x/y/z/xyz)#`|-|
    |`#playerCount(category 0)# | category: team, skin, veh, data, wanted, action, dead, alive, score, gun/weapon, channel, afk, vip, taser, surfingveh, int, attach, attachmodel, retval, vehseat`|-|
    |`#playerList(item category 0)# | category: (см. выше)`|-|
    |`#key(sIDe, *playerID)#`|-|
    |`#weaponState(*playerID)# or #gunState(*playerID)#`|-|
    |`#front(dist <x/y>, *playerID)#`|-|
    |Транспортные средства||
    |`#vehicle(*playerID)# or #veh(*playerID)#`|вернуть ID т/c из /dll||
    |`#vdata(vehID slot)#`|вернуть массив транспорта (СЛОТ: 0-49)|
    |`#GetDistVeh(vehID, *playerID)#`|вернет дистанцию к vehID|
    |`#vehPos(vehID)#`|вернет позицию ТС по vehID|
    |`#vehColor(*playerID)#`|цвет автомобиля в HEX формате|
    |`#vehColor1(*playerID)#`|цвет автомобиля 1 в числовом формате САМПа|
    |`#vehColor2(*playerID)#`|цвет автомобиля 2 в числовом формате САМПа|
    |`#vehModel(*playerID)# or #GetVehModel(vehID)#`|вернет модель ТС игрока по playerID или вернет модель ТС по vehID|
    |`#vehHealth(*playerID)#`|вернуть уровень здоровья ТС|
    |`#gearState(vehID)#`|-|
    |`#surfingVeh(*playerID)#`|вернет ID автомобиля на котором стоит игрок, ИНАЧЕ ВОЗВРАЩАЕТ 65535. Работает только при условии нахождении водителя в ТС.|
    |`#nearveh(radius, *playerID)#`|вернет ближ. автомобиль в радиусе radius|
    |`#vehParam(vehicleID param)#`|вернет параметр автомобиля, вместо vehicleID можно указать 0 - заменет на ид вашего транспорта. Вместо param указываете параметр 0-6; 0 - engine - получает статус двигателя, если 1 - двигатель включен. 1 - lights - получает статус фар, если 1 - включены. 2 - alarm - получает сигнал тревоги, если 1 - звучит. 3 - doors - получает статус дверей, если 1 - закрыты. 4 - bonnet - получает статус капота, если 1 - открыт. 5 - boot - получает статус багажника, если 1 - открыт. 6 - objective - метка на карте, если 1 - включено. (аналог параметров из действия “изменить параметры ТС”)|
    |`#vehdriver(vehID)#`|вернет ID водителя машины vehID|
    |`#gmcar(vehID)#`|вернет статус ГМ кара автомобиля vehID|
    |`#siren(vehID)#`|вернет статус cирены автомобиля по vehID|
    |`#getVehName(vehID)#`|вернет названия модели машины по VEHID|
    |`#getModelName(modelID)#`|вернет название модели машины по MODELID|
    |`#getVehName(vehID)#`|вернет названия машины по vehID|
    |`#vehCount#`|вернет кол-во машин в мире|
    |Объекты||
    |`#GetDistObject(objectID| *playerID)#`"|вернет дистацию к объекту|
    |`#omodel(objectID)#`|вернет модель объекта по мировому objectID|
    |`#oxyz(objectID)# #ox(objectID)# #oy(objectID)# #oz(objectID)#`|вернет координаты объекта по мировому objectID|
    |`#rxyz(objectID)# #rx(objectID)# #ry(objectID)# #rz(objectID)#`|вернет угол поворота по осям объекта по мировому objectID|
    |`#nearObj(dist modelID)#`|вернет ближ. объект в радиусе dist меетров (НЕ БОЛЬШЕ 200 МЕТРОВ). Необязательный параметр: modelID|
    |`#oMove(objectID)#`|вернет статус движется ли объект - 0/1|
    |`#oMoveXYZ(objectID)# #oMoveX(objectID)# #oMoveY(objectID)# #oMoveZ(objectID)#`|вернет координаты к которым движется объект|
    |`#oArray(objectID)#`|вернет массив объекта|
    |`#oState(objectID)#`|вернет статус отображения объекта|
    |`#objectCount#`|вернет кол-во объектов в мире|
    |`#maxObj# or #maxObjectCount#`|вернет макс. возможное кол-во объектов в мире|
    |`#getDistAction(actionID)#`|вернет дистанцию к /action|
    |`#actionXYZ(actionID)# #actionX(actionID)# #actionY(actionID)# #actionZ(actionID)#`|вернет координаты /actrion|
    |`#actionText(actionID)#`|вернет текст акшиона|
    |`Действия со строками`|-|
    |`#strfind(str, substr, caps)#`|найдет substr в str и вернет символ начала substr в str. CAPS: 0/1 - учитывать ли регистр, по умолчанию: учитывать (1)|
    |`#strcmp(str, substr, caps)#`|проверит идентичные строки и вернет символ начала substr в str. CAPS: 0/1 - учитывать ли регистр, по умолчанию: учитывать (1). Функция подходит для сравнения введенных параметров (паролей, которые содержат символы, а не только числа).|
    |`#strdel(str, start, stop)#`|удалит со str символы начиная с start и заканчивая stop|
    |`#strlen(str)#`|вернет длину строки str|
    |`#strins(str, substr, index)#`|вставит substr в str на index место|
    |`#worldName#`|вернет название мира|
    |`#worldDesc#`|вернет описание мира|
    |`#sscanf(text, d, &)#`|функция для разделения параметров из text; d - порядковый номер элемента; & - разделитель|
    |`/pass`|-|
    |`#passinfo(*playerID)#`|вернет ID ближ. pass к игроку|
    |`#pXYZ(passID)# #pX(passID)# #pY(passID)# #pZ(passID)#`|координаты /pass|
    |`#pRX(passID)#`|-|
    |`#pInt(passID)#`|-|
    |`#pLock(passID)#`|-|
    |`#pOwner(passID)#`|-|
    |`#pVehicle(passID)#`|-|
    |`#getDate(*category)#     list: day, month, year, days/daynum`|-|
    |`#getTime(*category)#     list: hour, minute, second`|-|
    |`#pModel(passID)#`|-|
    |`#pStatus(passID)# or #pState(passID)#`|-|
    |`#pTeam(passID)#`|-|
    |Актеры||
    |`#nearActor(dist| skinID)#`|вернет ближ. актера в радиусе radius. Необязательный параметр: модель скина.|
    |`#actorXYZ(actorID)# #actorX(actorID)# #actorY(actorID)# #actorZ(actorID)#`|-|
    |`#GetDistActor(actorID, *playerID)#`|вернет координаты актера|
    |`#actorState(actorID)# or #actorStatus(actorID)#`|вернет статус актера|
    |`#actorAnim(actorID)#`|вернет анимацию актера из списка|
    |`#actorAltAnim(actorID)#`|вернет альтернативную анимацию актера из списка|
    |`#actorSkin(actorID)#`|вернет модель скина актера|
    |`#actorHealth(actorID)#`|вернет уровень здоровья актера|
    |`#actorInvulnerable(actorID)# or #actorGM(actorID)#`|вернет статус GM’a у актера|
    |Аттачи||
    |`#attach(ID| *playerID)#`|вернет статус (0/1) занят ли слот аттача ID|
    |`#attachModel(ID, *playerID)#`|вернет модель аттача в слоте ID|
    |`#isAttachModel(modelID, *playerID)#`|проверит есть ли данная модель аттача у игрока и вернет cлот. Если нет то вернет -1.|
    |`#attachBone(slot, *playerID)#`|кость к которой прикреплен аттач в слоте|
    |`#attachOffsetXYZ(slot, *playerID)# -`|-|
    |`#attachOffsetX(slot, *playerID)#`|-|
    |`#attachOffsetY(slot, *playerID)#`|-|
    |`#attachOffsetZ(slot, *playerID)#`|-|
    |`#attachRotXYZ(slot, *playerID)#`|-|
    |`#attachRotX(slot, *playerID)#`|-|
    |`#attachRotY(slot, *playerID)#`|-|
    |`#attachRotZ(slot, *playerID)#`|-|
    |`#attachScaleXYZ(slot, *playerID)#`|-|
    |`#attachScaleX(slot, *playerID)#`|-|
    |`#attachScaleY(slot, *playerID)#`|-|
    |`#attachScaleZ(slot, *playerID)#`|-|
    |`#vAttach(slot, vehicleID)#`|-|
    |`#vAttachModel(slot,*vehicleID)#`|-|
    |`#isvAttachModel(modelID, vehicleID)#`|-|
    |`#vAttachXYZ(slot, vehicleID)#`|-|
    |`#vAttachX(slot, vehicleID)#`|-|
    |`#vAttachY(slot, vehicleID)#`|-|
    |`#vAttachZ(slot, vehicleID)#`|-|
    |`#vAttachRotXYZ(slot, vehicleID)#`|-|
    |`#vAttachRotX(slot, vehicleID)#`|-|
    |`#vAttachRotY(slot, vehicleID)#`|-|
    |`#vAttachRotZ(slot, vehicleID)#`|-|
    |`#vAttachOffsetXYZ(slot, vehicleID)#`|-|
    |`#vAttachOffsetX(slot, vehicleID)#`|-|
    |`#vAttachOffsetY(slot, vehicleID)#`|-|
    |`#vAttachOffsetZ(slot, vehicleID)#`|-|
    |/gate||
    |`#gateStatus(gateID)# or #gateState(gateID)#`|-|
    |`#gateID(gateID)# (MODEL)`|-|
    |`#gateTeam(gateID)#`|-|
    |`#gateType(gateID)#`|-|
    |`#gateLocal(gateID)#`|-|
    |`#gateSpeed(gateID)#`|-|
    |`#gateStartPosXYZ(gateID)#`|-|
    |`#gateStartPosX(gateID)#`|-|
    |`#gateStartPosY(gateID)#`|-|
    |`#gateStartPosZ(gateID)#`|-|
    |`#gateStartPosRXYZ(gateID)#`|-|
    |`#gateStartPosRX(gateID)#`|-|
    |`#gateStartPosRY(gateID)#`|-|
    |`#gateStartPosRZ(gateID)#`|-|
    |`#gateStopPosXYZ(gateID)# or gateEndPos`|-|
    |`#gateStopPosX(gateID)# or gateEndPos`|-|
    |`#gateStopPosY(gateID)# or gateEndPos`|-|
    |`#gateStopPosZ(gateID)# or gateEndPos`|-|
    |`#gateStopPosRXYZ(gateID)# or gateEndPos`|-|
    |`#gateStopPosRX(gateID)# or gateEndPos`|-|
    |`#gateStopPosRY(gateID)# or gateEndPos`|-|
    |`#gateStopPosRZ(gateID)# or gateEndPos`|-|
    |Действия с числами||
    |`#random(numb1| numb2)#`|вернет случайное число|
    |`#floatnum(numb1 type numb2)#`|действия с плавающими числами. Пример использования: #floatnum(5.12 + 6.15)#, #floatnum(3.33 * 1.37)#, #floatnum(2.0 * 2.0)#|
    |`#round(number *method)#` или `#floatround(number *method)#`|методы: round - метод по дефолту, округляет к ближ. целому числу; floor - округляет вниз; ceil - округляет вверх; tozero - округляет ближе к 0;|
    |`#log(number base)#`|логарифм|
    |`#sin(number *method)#`|синус от числа number (методы ниже)|
    |`#cos(number *method)#`|косинус от числа number (методы ниже)|
    |`#tan(number *method)#`|тангенс от числа number (методы вот тут) | методы: radian - по дефолту; degrees; grades|
    |`#sqroot(number)#`|найдет квадратный корень из числа number|
    |`#power(numb1 numb2)#`|возведет число numb1 в степень numb2|
    |`#min(value1 value2)#`|вернет наименьшее из двух чисел|
    |`#max(value1 value2)#`|вернет наибольшее из двух чисел|
    |`#clamp(value min_value max_value)#`|сведет число value к диапазону чисел. Если число меньше min_value то оно вернет min_value, если больше max_value то вернет max_value|


**Текстовые функции** - текстовые команды, которые вы можете использовать внутри командных блоков в качестве условий для проверки, получения данных, арифметики и многого другого.
Примеры использования текстовых функций:
```title="Получить никнейм игрока"
#getplayername#
```
```title="Получить никнейм случайного игрока из мира"
#getplayername(`randomplayer`)#
```

## Коллбэки

??? abstract "Список коллбэков"

    | коллбэк                                                | описание                                                                                      |
    | ------------------------------------------------------ | --------------------------------------------------------------------------------------------- |
    | Нанесение урона                                        |                                                                                               |
    | `#retstr(0)#`                                          | ник игрока, который получил урон.                                                             |
    | `#retstr(1)#`                                          | название оружия.                                                                              |
    | `#retstr(2)#`                                          | часть тела.                                                                                   |
    | `#retval(0)#`                                          | ID того, кто нанес урон.                                                                      |
    | `#retval(1)#`                                          | ID того, кто получил урон.                                                                    |
    | `#retval(2)#`                                          | сумма нанесённого урона.                                                                      |
    | `#retval(3)#`                                          | ID оружия.                                                                                    |
    | `#retval(4)#`                                          | ID части тела.                                                                                |
    | `#retval(5)#`                                          | команда игрока, получившего урон.                                                             |
    | `#retval(6-9)#`                                        | N/A                                                                                           |
    | Получение урона                                        |                                                                                               |
    | `#retstr(0)#`                                          | ник игрока, который нанес урон.                                                               |
    | `#retstr(1)#`                                          | название оружия.                                                                              |
    | `#retstr(2)#`                                          | часть тела.                                                                                   |
    | `#retval(0)#`                                          | ID того, кто получил урон.                                                                    |
    | `#retval(1)#`                                          | ID того, кто нанес урон.                                                                      |
    | `#retval(2)#`                                          | сумма нанесённого урона.                                                                      |
    | `#retval(3)#`                                          | ID оружия.                                                                                    |
    | `#retval(4)#`                                          | ID части тела.                                                                                |
    | `#retval(5)#`                                          | команда игрока, нанёсшего урон.                                                               |
    | `#retval(6-9)#`                                        | N/A                                                                                           |
    | Выстрел                                                |                                                                                               |
    | `#retstr(0)#`                                          | название оружия.                                                                              |
    | `#retstr(1)#`                                          | во что выстрелил игрок (объект, машина, игрок).                                               |
    | `#retval(0)#`                                          | ID того, кто выстрелил.                                                                       |
    | `#retval(1)#`                                          | ID оружия.                                                                                    |
    | `#retval(2)#`                                          | тип выстрела.                                                                                 |
    | `#retval(3)#`                                          | уникальный ID выстрела.                                                                       |
    | `#retval(4)#`                                          | куда был произведён выстрел по оси X.                                                         |
    | `#retval(5)#`                                          | куда был произведён выстрел по оси Y.                                                         |
    | `#retval(6)#`                                          | куда был произведён выстрел по оси Z.                                                         |
    | `#retval(7-9)#`                                        | N/A                                                                                           |
    | Убийство                                               |                                                                                               |
    | `#retstr(0)#`                                          | ник убитого игрока.                                                                           |
    | `#retstr(1)#`                                          | название оружия.                                                                              |
    | `#retval(0)#`                                          | ID игрока, который убил.                                                                      |
    | `#retval(1)#`                                          | ID игрока, которого убили.                                                                    |
    | `#retval(2)#`                                          | ID оружия.                                                                                    |
    | `#retval(3)#`                                          | команда убитого игрока.                                                                       |
    | `#retval(4-9)#`                                        | N/A                                                                                           |
    | Смерть                                                 |                                                                                               |
    | `#retstr(0)#`                                          | ник игрока, который умер.                                                                     |
    | `#retstr(1)#`                                          | название оружия.                                                                              |
    | `#retval(0)#`                                          | ID игрока, который умер.                                                                      |
    | `#retval(1)#`                                          | ID игрока, который убил.                                                                      |
    | `#retval(2)#`                                          | ID оружия.                                                                                    |
    | `#retval(3)#`                                          | команда игрока, который убил.                                                                 |
    | `#retval(4-9)#`                                        | N/A                                                                                           |
    | Сесть в транспорт                                      |                                                                                               |
    | `#retstr(0)#`                                          | название транспорта.                                                                          |
    | `#retval(0)#`                                          | ID игрока, который сел в транспорт.                                                           |
    | `#retval(1)#`                                          | номер места, на которое сел игрок. * https://wiki.sa-mp.com/wiki/state                        |
    | `#retval(2)#`                                          | ID транспорта.                                                                                |
    | `#retval(3)#`                                          | модель транспорта.                                                                            |
    | `#retval(4)#`                                          | ID владельца транспорта.                                                                      |
    | `#retval(5)#`                                          | координата x транспорта.                                                                      |
    | `#retval(6)#`                                          | координата y транспорта.                                                                      |
    | `#retval(7)#`                                          | координата z транспорта.                                                                      |
    | `#retval(8-9)#`                                        | N/A                                                                                           |
    | Выйти из транспорта                                    |                                                                                               |
    | `#retstr(0)#`                                          | название транспорта.                                                                          |
    | `#retval(0)#`                                          | ID игрока, который вышел из транспорта.                                                       |
    | `#retval(1)#`                                          | новое состояние персонажа * https://wiki.sa-mp.com/wiki/state                                 |
    | `#retval(2)#`                                          | ID транспорта.                                                                                |
    | `#retval(3)#`                                          | модель транспорта.                                                                            |
    | `#retval(4)#`                                          | ID владельца транспорта.                                                                      |
    | `#retval(5)#`                                          | координаты транспорта x.                                                                      |
    | `#retval(6)#`                                          | координаты транспорта y.                                                                      |
    | `#retval(7)#`                                          | координаты транспорта z.                                                                      |
    | `#retval(8-9)#`                                        | N/A                                                                                           |
    | Взять гоночный чекпоинт / Выйти из гоночного чекпоинта |                                                                                               |
    | `#retval(0)#`                                          | ID игрока, который взял чекпоинт.                                                             |
    | `#retval(1)#`                                          | ID транспорта.                                                                                |
    | `#retval(2)#`                                          | модель транспорта.                                                                            |
    | `#retval(3)#`                                          | владелец транспорта.                                                                          |
    | `#retval(4)#`                                          | координаты транспорта x.                                                                      |
    | `#retval(5)#`                                          | координаты транспорта y.                                                                      |
    | `#retval(6)#`                                          | координаты транспорта z.                                                                      |
    | `#retval(7)#`                                          | скорость транспорта.                                                                          |
    | `#retval(8-9)#`                                        | N/A                                                                                           |
    | Выстрелить по объекту                                  |                                                                                               |
    | `#retstr(0)#`                                          | название оружия.                                                                              |
    | `#retval(0)#`                                          | ID игрока который выстрелил по объекту.                                                       |
    | `#retval(1)#`                                          | ID оружия.                                                                                    |
    | `#retval(2)#`                                          | ID объекта.                                                                                   |
    | `#retval(3)#`                                          | модель объекта.                                                                               |
    | `#retval(4)#`                                          | координаты выстрела x.                                                                        |
    | `#retval(5)#`                                          | координаты выстрела y.                                                                        |
    | `#retval(6)#`                                          | координаты выстрела z.                                                                        |
    | `#retval(7)#`                                          | координаты объекта x.                                                                         |
    | `#retval(8)#`                                          | координаты объекта y.                                                                         |
    | `#retval(9)#`                                          | координаты объекта z.                                                                         |
    | Ввод диалога                                           |                                                                                               |
    | `#retstr(0-9)#`                                        | введенный текст игрока в диалог по 24 символа.                                                |
    | `#retval(0)#`                                          | ID игрока который активировал диалог.                                                         |
    | `#retval(1)#`                                          | выбранная строка игроком.                                                                     |
    | `#retval(2)#`                                          | цифровой параметр введенный игроком.                                                          |
    | `#retval(3)#`                                          | цифровой параметр введенный игроком.                                                          |
    | `#retval(4)#`                                          | цифровой параметр введенный игроком.                                                          |
    | `#retval(5)#`                                          | ID вызываемого блока.                                                                         |
    | `#retval(6)#`                                          | кнопка диалога выбранная игроком. y - 1. x - 0.                                               |
    | `#retval(7-9)#`                                        | N/A.                                                                                          |
    | Вызов блока                                            |                                                                                               |
    | `#retstr(0)#`                                          | имя игрока который вызвал блок.                                                               |
    | `#retval(0)#`                                          | ID игрока который вызывал блок.                                                               |
    | `#retval(1)#`                                          | цифровой параметр введенный игроком.                                                          |
    | `#retval(2)#`                                          | цифровой параметр введенный игроком.                                                          |
    | `#retval(3)#`                                          | цифровой параметр введенный игроком.                                                          |
    | `#retval(4-9)#`                                        | N/A.                                                                                          |
    | Создание чего-либо через кб                            |                                                                                               |
    | `#retval(0)#`                                          | возвращает ID созданого чего-либо.                                                            |
    | `#retval(1-9)#`                                        | N/A                                                                                           |
    | Завести двигатель/заглушить двигатель                  |                                                                                               |
    | `#retval(0)#`                                          | ID игрока                                                                                     |
    | `#retval(1)#`                                          | ID транспорта                                                                                 |
    | `#retval(2)#`                                          | hp транспорта                                                                                 |
    | `#retval(3)#`                                          | ID аккаунта владельца транспорта                                                              |
    | `#retval(4)#`                                          | номер команды, которая имеет доступ к транспорту (настраивается в /vmenu \*vehID)             |
    | Попытка сесть в транспорт                              |                                                                                               |
    | `#retval(0)#`                                          | ID игрока                                                                                     |
    | `#retval(1)#`                                          | возвращает 0/1 если транспорт открыт/закрыт (срабатывает только при воспроизведении анимации) |
    | `#retval(2)#`                                          | порядковый ID транспорта в мире (указан на номерах)                                           |
    | `#retval(3)#`                                          | модель транспорта                                                                             |
    | `#retval(4)#`                                          | ID аккаунта владельца транспорта                                                              |
    | Нажатие клавиши                                        |                                                                                               |
    | `#retval(1)#`                                          | виртуальный ID клавиши                                                                        |


**Коллбэки** - значения, которые передаются командному блоку при срабатывании триггера.
Примеры использования коллбэков:
```title='Получить ID игрока который вызвал блок при условии "Вызов блока"'
#retval(0)#
```



## Интересные системы для практики с КБ

- [Запрос авиаудара от Vol3k](https://forum.training-server.com/d/17583)

- [Дрифт система от Cheater_80_LVL](https://forum.training-server.com/d/16934)

- [TRAINING PIXEL от xWivar](https://forum.training-server.com/d/14283)
