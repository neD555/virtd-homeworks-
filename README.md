### Домашнее задание к занятию 4 «Оркестрация группой Docker контейнеров на примере Docker Compose»
### Инструкция к выполению:
### Для выполнения заданий обязательно ознакомьтесь с инструкцией по экономии облачных ресурсов. Это нужно, чтобы не расходовать средства, полученные в результате использования промокода.
### Практические задачи выполняйте на личной рабочей станции или созданной вами ранее ВМ в облаке.
### Своё решение к задачам оформите в вашем GitHub репозитории в формате markdown!!!
### В личном кабинете отправьте на проверку ссылку на .md-файл в вашем репозитории.
### Задача 1.
### Сценарий выполнения задачи:
### Установите docker и docker compose plugin на свою linux рабочую станцию или ВМ.
### Если dockerhub недоступен создайте файл /etc/docker/daemon.json с содержимым: {"registry-mirrors": ["https://mirror.gcr.io", "https://daocloud.io", "https://c.163.com/", "https://registry.docker-cn.com"]}
### Зарегистрируйтесь и создайте публичный репозиторий с именем "custom-nginx" на https://hub.docker.com (ТОЛЬКО ЕСЛИ У ВАС ЕСТЬ ДОСТУП);

скачайте образ nginx:1.21.1;

### Создайте Dockerfile и реализуйте в нем замену дефолтной индекс-страницы(/usr/share/nginx/html/index.html), на файл index.html с содержимым:

<img width="959" height="176" alt="png" src="https://github.com/user-attachments/assets/15391183-d2e4-460f-8ee5-caacf4fa6140" />

Соберите и отправьте созданный образ в свой dockerhub-репозитории c tag 1.0.0 (ТОЛЬКО ЕСЛИ ЕСТЬ ДОСТУП).

Предоставьте ответ в виде ссылки на https://hub.docker.com/<username_repo>/custom-nginx/general .

Решение 1.

https://hub.docker.com/repository/docker/deniszakhodyakin/custom-nginx/general

### Задача 2
### Запустите ваш образ custom-nginx:1.0.0 командой docker run в соответвии с требованиями:

имя контейнера "ФИО-custom-nginx-t2"

контейнер работает в фоне

контейнер опубликован на порту хост системы 127.0.0.1:8080
### Не удаляя, переименуйте контейнер в "custom-nginx-t2"
### Выполните команду date +"%d-%m-%Y %T.%N %Z" ; sleep 0.150 ; docker ps ; ss -tlpn | grep 127.0.0.1:8080  ; docker logs custom-nginx-t2 -n1 ; docker exec -it custom-nginx-t2 base64 /usr/share/nginx/html/index.html
### Убедитесь с помощью curl или веб браузера, что индекс-страница доступна.
### В качестве ответа приложите скриншоты консоли, где видно все введенные команды и их вывод.

Решение 2.

<img width="480" height="100" alt="Задание 2(1)" src="https://github.com/user-attachments/assets/ee5d7403-97c3-4140-afa4-7d69c8d6cc57" />

<img width="488" height="48" alt="Задание 2(2)" src="https://github.com/user-attachments/assets/7798fd00-5251-4ee8-bd07-b801091774af" />

<img width="490" height="206" alt="Задание 2(3)" src="https://github.com/user-attachments/assets/2cf9f8eb-1d64-4b0b-80bc-e6de371de9a0" />

<img width="430" height="353" alt="Задание 2(4)" src="https://github.com/user-attachments/assets/326985d5-7fd0-49d0-863e-cff466b5aab2" />

### Задача 3.
### 1.Воспользуйтесь docker help или google, чтобы узнать как подключиться к стандартному потоку ввода/вывода/ошибок контейнера "custom-nginx-t2".
### 2.Подключитесь к контейнеру и нажмите комбинацию Ctrl-C.
### 3.Выполните docker ps -a и объясните своими словами почему контейнер остановился.
### 4.Перезапустите контейнер
### 5.Зайдите в интерактивный терминал контейнера "custom-nginx-t2" с оболочкой bash.
### 6.Установите любимый текстовый редактор(vim, nano итд) с помощью apt-get.
### 7.Отредактируйте файл "/etc/nginx/conf.d/default.conf", заменив порт "listen 80" на "listen 81".
### 8.Запомните(!) и выполните команду nginx -s reload, а затем внутри контейнера curl http://127.0.0.1:80 ; curl http://127.0.0.1:81.
### 9.Выйдите из контейнера, набрав в консоли exit или Ctrl-D.
### 10.Проверьте вывод команд: ss -tlpn | grep 127.0.0.1:8080 , docker port custom-nginx-t2, curl http://127.0.0.1:8080. Кратко объясните суть возникшей проблемы.
### 11.Это дополнительное, необязательное задание. Попробуйте самостоятельно исправить конфигурацию контейнера, используя доступные источники в интернете. Не изменяйте конфигурацию nginx и не удаляйте контейнер. Останавливать контейнер можно. пример источника
### 12.Удалите запущенный контейнер "custom-nginx-t2", не останавливая его.(воспользуйтесь --help или google)
### В качестве ответа приложите скриншоты консоли, где видно все введенные команды и их вывод.

Решение 3.
<img width="482" height="125" alt="Задание 3(1)" src="https://github.com/user-attachments/assets/760ee281-3934-4ab9-b5eb-cbada46a5476" />

<img width="484" height="427" alt="Задание 3(2)" src="https://github.com/user-attachments/assets/6333eb97-9df0-4070-b74e-08969cc5c60e" />

<img width="489" height="52" alt="Задание 3(3)" src="https://github.com/user-attachments/assets/7d8e51a4-86c6-42ae-bcde-f3e0263aaad9" />

<img width="497" height="623" alt="Задание 3(4)" src="https://github.com/user-attachments/assets/21f9a7fa-2a27-4aa1-b213-2825b5ded8da" />

<img width="492" height="404" alt="Задание 3(5)" src="https://github.com/user-attachments/assets/3d584d07-441d-4189-ba38-1463d2e24930" />

<img width="497" height="75" alt="Задание 3(6)" src="https://github.com/user-attachments/assets/7707ac06-13d6-47ad-995f-92841b04ebbc" />

<img width="491" height="384" alt="Задание 3(7)" src="https://github.com/user-attachments/assets/22858fe7-326e-4d2a-8c99-476c67797d4b" />

<img width="498" height="416" alt="Задание 3(8)" src="https://github.com/user-attachments/assets/adf9ef46-06f0-4119-8026-4491093906e9" />

### Задача 4.
### Запустите первый контейнер из образа centos c любым тегом в фоновом режиме, подключив папку текущий рабочий каталог $(pwd) на хостовой машине в /data контейнера, используя ключ -v.
### Запустите второй контейнер из образа debian в фоновом режиме, подключив текущий рабочий каталог $(pwd) в /data контейнера.
### Подключитесь к первому контейнеру с помощью docker exec и создайте текстовый файл любого содержания в /data.
### Добавьте ещё один файл в текущий каталог $(pwd) на хостовой машине.
### Подключитесь во второй контейнер и отобразите листинг и содержание файлов в /data контейнера.
### В качестве ответа приложите скриншоты консоли, где видно все введенные команды и их вывод.

### Решение 4.

<img width="491" height="151" alt="Задание 4(1)" src="https://github.com/user-attachments/assets/36f9b011-61cd-452b-9bcc-3e90479216bb" />

<img width="495" height="143" alt="Задание 4(2)" src="https://github.com/user-attachments/assets/95aa6c1f-1bd8-4b9a-a2c8-c815754b1e48" />

<img width="503" height="144" alt="Задание 4(3)" src="https://github.com/user-attachments/assets/5bcf9f65-74d8-45c9-9269-5c3fce0b629a" />

<img width="493" height="89" alt="Задание 4(4)" src="https://github.com/user-attachments/assets/5b5b7e25-ffc6-4c0b-8ee3-0e60d2625ba4" />

<img width="509" height="385" alt="Задание 4(5)" src="https://github.com/user-attachments/assets/7d1a116a-0bfe-430b-b7f3-f943302c53b8" />

### Задача 5

### 1.Создайте отдельную директорию(например /tmp/netology/docker/task5) и 2 файла внутри него. "compose.yaml" с содержимым:

<img width="775" height="317" alt="33333333333333333333333333333333333333333333" src="https://github.com/user-attachments/assets/ebafa406-9c51-4ae7-8037-da15c104b769" />

### И выполните команду "docker compose up -d". Какой из файлов был запущен и почему? (подсказка: https://docs.docker.com/compose/compose-application-model/#the-compose-file )

### 2.Отредактируйте файл compose.yaml так, чтобы были запущенны оба файла. (подсказка: https://docs.docker.com/compose/compose-file/14-include/)

### 3.Выполните в консоли вашей хостовой ОС необходимые команды чтобы залить образ custom-nginx как custom-nginx:latest в запущенное вами, локальное registry. Дополнительная документация: https://distribution.github.io/distribution/about/deploying/

### 4.Откройте страницу "https://127.0.0.1:9000" и произведите начальную настройку portainer.(логин и пароль адмнистратора)

### 5.Откройте страницу "http://127.0.0.1:9000/#!/home", выберите ваше local окружение. Перейдите на вкладку "stacks" и в "web editor" задеплойте следующий компоуз:

<img width="773" height="126" alt="hhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhhh" src="https://github.com/user-attachments/assets/e143872f-e491-48d3-b238-a57ed169996c" />

### 6.Перейдите на страницу "http://127.0.0.1:9000/#!/2/docker/containers", выберите контейнер с nginx и нажмите на кнопку "inspect". В представлении <> Tree разверните поле "Config" и сделайте скриншот от поля "AppArmorProfile" до "Driver".

### 7.Удалите любой из манифестов компоуза(например compose.yaml). Выполните команду "docker compose up -d". Прочитайте warning, объясните суть предупреждения и выполните предложенное действие. Погасите compose-проект ОДНОЙ(обязательно!!) командой.

### В качестве ответа приложите скриншоты консоли, где видно все введенные команды и их вывод, файл compose.yaml , скриншот portainer c задеплоенным компоузом.

### Решение 5.















