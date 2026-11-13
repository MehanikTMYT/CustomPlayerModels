
<a name="paste-site-api"/>

# API сайта хранения текстов

<a name="endpoints"/>

## Конечные точки
* [Скачивание](#download)
* [Подключение](#connect)
* [Аутентификация](#authenticate)
* [Список](#list)
* [Загрузка](#upload)
* [Удаление](#delete)
* [Обновление](#update)
* [Вход через браузер](#browser-login)
* [Вход приложения](#app-login)
* [Проверка приложения](#app-check)
* [Запрос токена приложения](#app-token-request)
* [Сообщения об ошибках](#error-messages)

Адрес API: `https://paste.tom5454.com/`  
Полная реализация на Java: [PasteClient в CPM](https://github.com/tom5454/CustomPlayerModels/blob/master/CustomPlayerModels/src/shared/java/com/tom/cpm/shared/paste/PasteClient.java)  


<a name="download"/>

### Скачивание
URL: `raw/<paste_id>`


<a name="connect"/>

### Подключение
URL: `api/connect?name=<username>`  
Ответ: (JSON)  
 * id: идентификатор сеанса, необходимый в последующих запросах  
 * key: ключ Minecraft Join Server  

Вызовите API подключения к серверу Minecraft. 
Это та же аутентификация, которую Minecraft использует при подключении к серверу Minecraft.  
URL: `https://sessionserver.mojang.com/session/minecraft/join`  
Требуется POST-запрос  
Тело запроса: (объект JSON)
 * accessToken: токен доступа учётной записи Minecraft
 * selectedProfile: UUID учётной записи Minecraft в виде строки (без символов `-`)
 * serverId: идентификатор сервера, вычисленный с помощью `key`

Вычисление serverId:  
Хеш SHA-1:
`tom5454-paste`, `<session id>` и `<key>` в виде строки ASCII
затем преобразуйте результат в строку шестнадцатеричного числа с помощью toString.
Пример кода на Java:  
```java
	byte[] mojKey = Base64.getDecoder().decode(key);//key string from api
	//SHA-1 digest all of the data
	byte[] mojangKey = digestData("tom5454-paste".getBytes(), session.getBytes(), mojKey);
	String serverId = new BigInteger(mojangKey).toString(16);
```

Вызовите [аутентификацию](#authenticate), чтобы завершить настройку сеанса.


<a name="authenticate"/>

### Аутентификация
URL: `api/session`  
Заголовки HTTP:  
 * Session: <session id from connect>  

Ответ: (JSON)  
	Пустой JSON при успехе


<a name="list"/>

### Список
URL: `api/list`  
Заголовки HTTP:  
 * Session: <session id from connect>  

Требуется аутентификация  
Ответ: (JSON)  
 * files (массив объектов)  
   (каждый объект)  
   * id: идентификатор сохранённого текста  
   * name: имя сохранённого текста  
   * time: время загрузки в виде строки, в мс по UTC  
 * maxSize  
 * maxFiles  


<a name="upload"/>

### Загрузка
URL: `api/upload`  
Заголовки HTTP:  
 * Session: <session id from connect>  
 * Content-Length: длина файла  
 * File-Name: имя сохранённого текста  

Требуется аутентификация  
Требуется POST-запрос  
Тело запроса: содержимое текста  
Ответ: (JSON)  
 * id: новый случайный идентификатор сохраняемого текста


<a name="delete"/>

### Удаление
URL: `api/delete?file=<paste_id>`  
Заголовки HTTP:  
 * Session: <session id from connect>  

Требуется аутентификация  
Ответ: (JSON)  
	Пустой JSON при успехе 


<a name="update"/>

### Обновление
URL: `api/update?file=<paste_id>`  
Заголовки HTTP:  
 * Session: <session id from connect>  
 * Content-Length: длина файла  

Требуется аутентификация  
Требуется POST-запрос  
Тело запроса: содержимое текста  
Ответ: (JSON)  
	Пустой JSON при успехе
	

<a name="browser-login"/>

### Вход через браузер
URL: `api/browser_login`
Заголовки HTTP:  
 * Session: <session id from connect>  
 
Требуется аутентификация  
Ответ: (JSON)  
 * id: токен входа через браузер, действующий 5 минут; используется на странице `/login.html?id=<id>`


<a name="app-login"/>

### Вход приложения
URL: `api/app_login`
Заголовки HTTP:  
 * AppID: <application id>  
 
Ответ: (JSON)  
 * id: токен входа приложения, действующий 5 минут; используется на странице `/auth.html?id=<id>`
 

<a name="app-check"/>

### Проверка приложения
URL: `api/app_check`
Заголовки HTTP:  
 * AppID: <application id> 
 * Session: <id from app login>
 
Ответ: (JSON)  
 * id: токен приложения сайта хранения текстов
или
 * пустой JSON, если авторизация ещё не выполнена
 

<a name="app-token-request"/>

### Запрос токена приложения
URL: `api/app_token_req`
Заголовки HTTP:  
 * AppID: <application id> 
 * Session: <id from app login>
 
Ответ: (JSON)  
 * id: токен сеанса сайта хранения текстов для операций [списка](#list), [загрузки](#upload), [удаления](#delete), [обновления](#update)


<a name="error-messages"/>

### Сообщения об ошибках
Ответ: (JSON)  
 * error: понятное человеку сообщение об ошибке
 * errorMessage: ключ перевода сообщения об ошибке
