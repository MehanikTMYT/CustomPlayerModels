Требуется дополнение: [CPM OSC compat на CurseForge](https://www.curseforge.com/minecraft/mc-mods/cpmoscc), [CPM OSC compat на Modrinth](https://modrinth.com/mod/cpmoscc)  


<a name="setting-up-osc-triggered-animations-with-cpm"/>

## Настройка анимаций CPM, запускаемых через OSC
Настройте OSC в `Edit/Tools/OSC Settings`.  
Для создания анимаций, запускаемых через OSC, используйте `Edit/Tools/OSC Animation Wizard`.  
Анимации должны иметь тип `Command Activated Animation`.  
Для сопоставления значений OSC с анимациями CPM используйте тип анимации `Value Layer`.  
Переключаемые слои срабатывают при значении выше 0.5 (после преобразования)  
Преобразование значений:  
CPM требует нормализованные значения (0-1); задайте минимум и максимум в мастере анимаций.  
`mapped_value = (osc_value - minimum_value) / (maximum_value - minimum_value)`  

CPM совместим со значениями OSC/VMC.


<a name="scripting"/>

## Скрипты
Для запуска скриптов Lua, реагирующих на команды OSC, можно использовать [TouchOSC](https://hexler.net/touchosc#get). [Примеры скриптов TouchOSC](https://hexler.net/touchosc/manual/script-examples)  
Библиотека Python для OSC: [python-osc](https://github.com/attwad/python-osc)  


<a name="other-applications"/>

## Другие приложения
Отслеживание лица: [VSeeFace](https://www.vseeface.icu/)  
Подойдёт большинство приложений для отправки OSC, работающих с VRChat. [Ресурсы по OSC для VRChat](https://docs.vrchat.com/docs/osc-resources)  
