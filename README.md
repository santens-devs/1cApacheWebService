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
Для публикации используются файлы формата VDR. Данные файлы служат для настройки веб-клиента, использования интернет-сервисов и находятся в каталоге виртуального приложения.

### Формат VDR
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
