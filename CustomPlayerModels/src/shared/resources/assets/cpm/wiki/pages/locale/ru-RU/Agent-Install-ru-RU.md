
<a name="java-agent-installation"/>

## Установка Java-агента
Версия CPM для Minecraft 1.2.5 представляет собой Java-агент.  
1. Скопируйте JAR-файл CPM в папку `.minecraft`.  
2. Затем добавьте следующий аргумент JVM:  
`-javaagent:CustomPlayerModels-1.2.5-<version>.jar`
Замените `<version>` на установленную версию.  

При обновлении CPM необходимо обновлять и аргумент JVM.

Требуется Minecraft Forge 1.2.5

В эту версию CPM включён мод, похожий на «Single Player Commands».  
Для включения добавьте аргумент JVM `-Dcpmcore.spc=true`.  
Поддерживаемые команды:  
gamemode, tp, time, give, toggledownfall, cpm, cpmclient
