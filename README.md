# M4M Frontend Lite Installer
Наш фронтенд состоит из 2 частей: сервер (nginx) и приложение (в виде статических файлов).

### Данные с сенсоров
Данные с сенсоров должны храниться в файле `/usr/api/sensor` (без расширения) в формате, как показано в [примере](sensor.example). Последние значения с сенсора должны быть записаны в поле `last_value` строкой. Предыдущие (по времени) показания сенсоров сохраняться в файле не должны (т.е. после при обновлении показаний файл перезаписывается).

### Установка/обновление сервера
Запускать с рабочего компьютера при первой установке, либо при обновлении nginx конфига.

```bash
./update-server-remotely.sh <controller IP>
``` 

Оно установит nginx и его конфигурацию на контроллер.

### Установка/обновление приложения
Перед этим необходимо установить [nodejs & npm](https://nodejs.org) на рабочий компьютер!

Запускать с рабочего компьютера при первой установке, либо при обновлении [фронтенда](https://github.com/m4mcontroller/frontend).

```bash
./update-app-remotely <controller IP>
```

Оно скачает, соберёт и отправит на контроллер фронтенд M4M.

### Запуск
При успешной установке сайт доступен на стандартном 80 порту (http://<controller IP> в браузере).
