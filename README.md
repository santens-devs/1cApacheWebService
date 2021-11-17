![Схема настроек apache2 для 1С](https://user-images.githubusercontent.com/1051804/142282525-1a19f989-e3f1-4b6f-8543-b0f312dda6c3.png)
___
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
Для публикации используются файлы формата [VRD][1]. Данные файлы служат для настройки веб-клиента, использования интернет-сервисов и находятся в каталоге виртуального приложения.

### [Описание формата VRD][1]
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
```bash
dpkg-deb --extract 1c-enterprise83-common_`version`_amd64.deb .
dpkg-deb --extract 1c-enterprise83-server_`version`_amd64.deb .
dpkg-deb --extract 1c-enterprise83-ws_`version`_amd64.deb .
```

Должна получиться следующая структура подкаталогов:
![image](https://user-images.githubusercontent.com/1051804/142215379-360ee412-b59a-44e0-a191-021114ae578b.png)

Далее необходимо обновить ссылку на текущую конфигурацию платформы 1с, используемую web-сервером при загрузке модуля `wsap24.so`.
Для этого, находясь в корневом каталоге конфигурации веб сервиса,
![image](https://user-images.githubusercontent.com/1051804/142216518-16915c73-b2bc-48df-8d43-2d48c5928f84.png)

нужно выполнить команду создания ссылки на дистрибутив платформы 1С.
```bash
unlink ./platform
ln -s ./distrib/`version`/opt/1C/v8.3/x86_64 ./platform
```

После чего можно перезагружать либо службу `sudo systemctl restart apache2.service` либо ОС целиком `sudo reboot`.

Если apach2 не стартует можно проверить ошибки командой `journalctl -xe`

# Обновление данного репозитория
После изменения настроек и если все работает и проверено необходимо обновлять данный репозиторий для обеспечения сохранности конфигурации.
Для этого используем `git`. Выполняем в корне репозитория:
```sh
git add .
git commit -a -m "Коментарий измменений"
```

`git status` не должен показывать незафиксированных изменений. Если все хорошо, заливаем в репозиторий `git push`

[1]: https://github.com/santens-devs/1cApacheWebService/files/7555017/vrd.pdf "VRD"
