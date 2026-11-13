
<a name="the-cpm-command"/>

# Команда `/cpm`

> [!NOTE]
> Это серверная команда CPM; о клиентской команде `/cpmclient` см. [здесь](https://github.com/tom5454/CustomPlayerModels/wiki/The--cpmclient-command-ru-RU)


<a name="subcommands"/>

### Подкоманды:
* [setskin](#setskin)
* [safety](#safety)
* [kick](#kick)
* [scaling](#scaling)
* [animate](#animate)
* [effects](#effects)
* [detect](#detect)


<a name="setskin"/>

## setskin
Использование `/cpm setskin [-f|-t|-r] <target> <base64 model>`  
Флаги:
* -f: принудительно задать модель; игрок не сможет менять свою модель.
* -t: временная модель; заданная модель сбрасывается при выходе игрока.
* -r: сбросить модель, заданную сервером

Цель: игрок, которому нужно задать модель  
Модель Base64: модель, экспортированная в формате Base64.  
См.: [экспорт Base64](https://github.com/tom5454/CustomPlayerModels/wiki/Exporting-ru-RU#base64)


<a name="safety"/>

## safety
Подкоманды:
* [recommend](#safety-recommend)
* [set](#safety-set)


<a name="safety-recommend"/>

### safety recommend
Использование: `/cpm safety recommend <enable>`  
Включить отправку рекомендуемых настроек безопасности. Параметры задаются командой [set](#safety-set).


<a name="safety-set"/>

### safety set
Использование: `/cpm safety set <option> <value>`  
Задать рекомендуемые настройки безопасности


<a name="kick"/>

## kick
Управляет отключением от сервера игроков без мода.  
Подкоманды:
* [enable](#kick-enable)
* [disable](#kick-disable)
* [message](#kick-message)


<a name="kick-enable"/>

### kick enable
Использование: `/cpm kick enable <kick time>`
Отключать игроков без установленного мода по истечении заданного времени (в тиках).


<a name="kick-disable"/>

### kick disable
Использование: `/cpm kick disable`
Отключить эту функцию


<a name="kick-message"/>

### kick message
Использование: `/cpm kick message <message...>`
Задать сообщение об отключении от сервера


<a name="scaling"/>

## scaling
Использование: `/cpm scaling <scaling option>`  
Подкоманды:
* [limit](#scaling-limit)
* [enabled](#scaling-enabled)
* [method](#scaling-method)
* [reset](#scaling-reset)
* [debug](#scaling-debug)


<a name="scaling-limit"/>

### scaling limit
Использование: `/cpm scaling <scaling option> limit [player] <max>` или `/cpm scaling <scaling option> limit [player] <min> <max>`  
Задать предел масштабирования для `scaling option`. Через аргумент игрока можно задать настройку для отдельного игрока; оставьте его пустым для общей настройки.


<a name="scaling-enabled"/>

### scaling enabled
Использование: `/cpm scaling <scaling option> enabled [player] <enable>`  
Включить масштабирование для `scaling option`. Через аргумент игрока можно задать настройку для отдельного игрока; оставьте его пустым для общей настройки.


<a name="scaling-method"/>

### scaling method
Использование: `/cpm scaling <scaling option> method [player] <method>`  
Задать способ масштабирования для `scaling option`.  
Поддерживаемые варианты:
* `disable` — вести себя так, будто мод масштабирования не установлен.  
* `default` — выбрать серверный способ масштабирования по умолчанию.  
* `attribute` — использовать стандартные атрибуты
* `pehkui` — использовать [Pehkui](https://github.com/tom5454/CustomPlayerModels/wiki/Scaling-ru-RU#pehkui) для масштабирования (если установлен)
* Другие поддерживаемые моды перечислены на [странице масштабирования](https://github.com/tom5454/CustomPlayerModels/wiki/Scaling-ru-RU).


<a name="scaling-reset"/>

### scaling reset
Использование: `/cpm scaling reset <player>`  
Сбросить масштабирование для выбранного игрока.


<a name="scaling-debug"/>

### scaling debug
Использование: `/cpm scaling debug <player>`  
Вывести все настройки масштабирования игрока: запрошенный масштаб `Rq`, фактический масштаб `V`, пределы `Lim`, способ масштабирования `M`.  
Пример вывода:
```
Scaling debug for <player>:

- 'Entity Scaling' M: attribute, V: 1.5 (Rq: 1.5), Lim: 0.01 - 3.0
- 'Eye Height' M: Not Supported (Rq: 1.0)
- 'Jump Height' M: attribute, V: 1.0 (Rq: 1.0), Lim: 0.01 - 10.0
- 'Health' M: Scaling limited to normal value (Rq: 1.0)
```


<a name="animate"/>

## animate
Использование: `/cpm animate <target> <animation name> [value (0-255)]`  
Воспроизвести анимацию для выбранного игрока или игроков.  
Значение: 0: сбросить позу/жест, 1: воспроизвести позу/жест; для слоёв со значением: 0-255, для переключателя: 0-1; оставьте пустым для смены состояния.


<a name="effects"/>

## effects
Использование: `/cpm effects <effect> <options...>`  
Доступные эффекты:  
- `invisible_glow <true/false>`: включить отрисовку светящихся слоёв у невидимых игроков. По умолчанию включено. Вступает в силу только после повторного входа.  


<a name="detect"/>

## detect
Использование: `/cpm detect <target> <animation name> [value (0-255)]`  
Проверить, воспроизводится ли заданная анимация  
Если указан параметр `value`, команда проверяет, равно ли ему значение анимации  
