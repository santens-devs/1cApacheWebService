# Конфигурация web-сервера apache2, для размещения сервисов 1С:Предприятие


## Общая схема конфигурации
![image](https://user-images.githubusercontent.com/1051804/142091877-03d3b4e0-f5ae-4e61-a07b-1cb7bda6328d.png)

## Доступ в хранилище конфигураций 1С по HTTP
![image](https://user-images.githubusercontent.com/1051804/142206963-eeee9871-cad2-4d86-a90a-c80b9e1e8615.png)

Данная конфигурация реализует возможность подключения к crs по http. Файлы настроек подключений хранятся в каталоге [crs-files](./crs-files).

Конфигурационный файл Web-сервиса для работы с удаленным хранилищем может иметь произвольное имя (*.1ccr), формат XML и содержит единственный узел с произвольным именем и атрибутом connectString ‑ в этом атрибуте указывается адрес сервера хранилища в схеме TCP.

Например, такой конфигурационный файл может иметь имя repository.1ccr и следующее содержание:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<repository connectString="tcp://192.168.0.1"/>
```
## Публикация web-сервисов 1С
Для публикации используются файлы формата [VDR][1]. Данные файлы служат для настройки веб-клиента, использования интернет-сервисов и находятся в каталоге виртуального приложения.

### [Описание формата VDR][1]
Корневым элементом конфигурационного файла является `<point>`, который определяет настройки виртуального ресурса. Он может содержать по одному элементу `<zones>`, `<ws>`, `<pool>`, `<debug>`, `<openid>`, `<openidconnect>`, `<exitURL>`, `<standardOData>`, `<analytics>` и `<progressiveWebApplication>`. При этом в элементе `<ws>` допустимо несколько вложенных элементов `<point>`, а для элемента `<zones>` допустимо несколько вложенных элементов `<zone>`:
```xml
<point...>
    <ws...>
        <point>...</point>
            <zones>
                <zone>...</zone>
                <zone>...</zone>
            </zones>
        <point>...</point>
    </ws>
    <httpServices>
        <service>...<service/>
    </httpServices>
    <pool.../>
    <debug.../>
    <openid>
        <rely... />
        <provider>
            <lifetime>...</lifetime>
        </provider>
    </openid>
    <openidconnect.../>
    <exitURL>
        ...
    </exitURL>
    <standardOData.../>
    <analytics.../>
    <progressiveWebApplication.../>
</point>
```

# Процесс обновления платформы 1С
Для размещения нового дистрибутива платформы нужно создать каталог новой версии дистрибутива в каталоге дистрибутивов конфигурации web-сервера:
![image](https://user-images.githubusercontent.com/1051804/142213817-b93916f6-0ad7-4fa5-a731-d7e658efef2c.png)

В каталоге версии дистрибутива необходимо разместить deb-пакеты:
- 1c-enterprise83-common_`version`_amd64.deb
- 1c-enterprise83-server_`version`_amd64.deb
- 1c-enterprise83-ws_`version`_amd64.deb

Далее нужно распаковать данные deb-пакеты в каталог версии дистрибутива. Находясь в каталоге версии дистрибутива нужно выполнить комманды:
```sh
dpkg-deb --extract 1c-enterprise83-common_`version`_amd64.deb .
dpkg-deb --extract 1c-enterprise83-server_`version`_amd64.deb .
dpkg-deb --extract 1c-enterprise83-ws_`version`_amd64.deb .
```

Долшна получиться следующая структура подкаталогов:
![image](https://user-images.githubusercontent.com/1051804/142215379-360ee412-b59a-44e0-a191-021114ae578b.png)



[1]: https://github.com/santens-devs/1cApacheWebService/files/7555017/vrd.pdf "VRD"
