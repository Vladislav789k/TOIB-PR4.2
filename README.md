# TOIB-PR4.2-Kar
# Практическое задание на тему "Контроль целостности"
Выполнил студент группы: ББМО-02-23 Карпейкин Владислав Анатольевич
## Установка и запуск виртуальной машины с Astra linux
Для выполнения данного задания был скачан образ Astra Linux ( ссылка: https://1drv.ms/u/s!Ap1Ijs338IQ9gZFmLJ5hn45FgcVLoQ?e=mH7Jzg ) и установлена версия системы "Смоленск" с максимальным уровнем защиты

![1](https://github.com/Vladislav789k/TOIB-PR4.2/assets/71137501/59693178-19be-4b2c-9a66-acc28ebfa25e)


## Установка, настройка и проверка мандатного контроля целостности (МКЦ)
Для установки МКЦ в ОС Astra Linux выбираем указанные галочки в процессе установки ISO образа 

![Alt text](2.png)

Для измнения конфигурации МКЦ в Astra Linux необходимо запустить утилиту "Управление политикой безопасности"

![Alt text](3.png)

В меню "Режим эксперта" назначаем уровни целостности для директорий. В качестве проверки правила NWU обозначили 2 тестовые директории ("Музыка" и "Видео") с  правами:

![Alt text](4.png)

Проверяем настройку мандатного контроля зайдя в учетную запись с атрибутом целостности на уровне "Низкий".

Пример взаимодействия (записи) между тестовыми директориями:

![Alt text](5.png)

Здесь можно увидеть, что копирование файла с атрибутом ниже в папку с атрибутом выше не сработало - была получена ошибка доступа. В то же время "запись вниз" работает.
## Работа с режимом замкнутой программной среды (ЗПС)
Проверка работы режима ЗПС в утилите "Управлении политикой безопасности" посредством включения настроек:

![Alt text](6.png)


## Работа с утилитами контроля целостности и регламентного контроля целостности
### Использование `gostsum`
Утилита `gostsum` вычисляет хэш-сумму файлов в соответствии с ГОСТ Р 34.11-2012. Пример использования с .deb пакетом установки AnyDesk:

![Alt text](7.png)

### Использование `afick`
`afick` - утилита, предназначенная для контроля целостности файловой системы ОС. Для корректной работы утилиты сначала создаём БД утилиты:

![Alt text](8.png)

Далее изменяем часть системных файлов для получения ответа от утилиты, перед этим делаем "бэкап" файл:

![Alt text](9.png)

Получили результат от утилиты:

![Alt text](10.png)

![Alt text](11.png)
