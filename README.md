# ОИБ-ПРАКТИКА
### [Ссылка на Практическую №3](https://github.com/ViktorovLeonid/OIB-PRACTICA#практическая-3)
### [Ссылка на Практическую №4](https://github.com/ViktorovLeonid/OIB-PRACTICA#практическая-4)
### [Ссылка на Практическую №5](https://github.com/ViktorovLeonid/OIB-PRACTICA#практическая-5)
# Практическая №1

Компания ОАО(Банк) «СбереженияНам». Штат — 38 сотрудников. 4 руководство, 4
бухгалтерия, 5 — IT-отдел, 20 — менеджеры по работе с клиентами, 5 — отдел
безопасности. 

Управление компании использует телефонную связь, MS Office, 1С: Предприятие и т.д.
Бухгалтерия использует телефонную связь, MS Office, 1С: Бухгалтерию.
IT-отдел обеспечивает функционирование внутренней сети организации, а также сайта компании и личных кабинетов клиентов.
Менеджеры по работе с
клиентами осуществляют работу с ними посредством Интернет и телефонной связи.

Технический регламент информационной безопасности направлен на защиту информационных активов от угроз, исходящих от противоправных действий злоумышленников, уменьшение рисков и снижение потенциального вреда от аварий, непреднамеренных ошибочных действий персонала, технических сбоев, неправильных технологических и организационных решений в процессах обработки, передачи и хранения информации и обеспечение нормального функционирования технологических процессов.

К основополагающим нормативным документам относятся: Доктрина информационной безопасности Российской Федерации (утверждена Президентом РФ от 5 декабря 2016 г. № Пр-646).

Инструкция для работников IT-отдела:

•	исключать возможность доступа третьих лиц к документам, содержащим конфиденциальную информацию;

•	не использовать чужие средства идентификации и не передавать никому свои, не входить в систему под чужим логином;

•	соблюдать установленные уровни допуска к информации;

•	не переписывать на съемные носители конфиденциальные данные без санкции руководителя, не передавать их по любым каналам связи, не раскрывать лицам, не имеющим соответствующего уровня доступа; 

•	соблюдать требования и правила по работе со средствами технической защиты, в том числе со средствами криптографической защиты;

•	контролировать состояние автоматизированного рабочего места, сообщать СБ обо всех ситуациях, имеющих характер инцидентов информационной безопасности, а именно: нарушении целостности пломб, свидетельствующем о попытке проникнуть в охраняемую зону, некорректном срабатывании антивирусной защиты, нарушениях в работе программного обеспечения, выявленных изменениях файлов, выходе из строя периферийных устройств;

•	обеспечивать отсутствие на своем АРМ самостоятельно установленных программ;

•	исключать копирование любых файлов или текстовой информации в любых целях без получения санкции руководителя.

---

# Практическая №2
1. Для того, чтобы узнать ip - адрес воспользуемся командами ping, nslookup и tracert в консоли.

![image](https://user-images.githubusercontent.com/70852092/95662585-a640a900-0b40-11eb-819d-4e3f5a3b90fb.png)

ip – адрес mirea.ru : [193.41.140.35]

Используя intitle:"forum" inurl:http after:2019, в качестве сайта для работы был взят сайт: loyalty-world.ru 

2. Далее были изучены команды nslookup -query=mx, soa, nx; type=any, с помощью которых я получил данные о сервере, почте администратора, серийном номере, периоде времени, через который вторичный DNS-сервер отправит запрос первичному, чтобы проверить, поменялся ли серийный номер. Интервал для повторного соединения с первичным DNS-сервером.
У данного домена серверная почта: mail-s19.1gb.ru

![image](https://user-images.githubusercontent.com/70852092/95662616-d0926680-0b40-11eb-94e6-174ee339f74a.png)

3. C помощью приложения Wireshark будем перехватывать и изучать трафик c сайта :
a) ip.src="ip сайта", данная команда осуществляет перехват трафика с сайта, который отравляет запрос на наш ip

![image](https://user-images.githubusercontent.com/70852092/95663085-beb2c280-0b44-11eb-80e0-66e49974576b.png)

б) ip.dst=="ip", данная же команда осуществляет перехват трафика с нашего устройства к сайту

![image](https://user-images.githubusercontent.com/70852092/95663087-c5d9d080-0b44-11eb-87c1-0a13f7b21629.png)

подключение к сайту происходит через порт 80, а робтает через протокол HTTP и TCP

в) ip.addr='ip' комбинирует команды выше и показывает как трафик с сайта, так и с нашего устройства

![image](https://user-images.githubusercontent.com/70852092/95663089-d1c59280-0b44-11eb-8ed6-4d20fc5ecbce.png)

г) udp.port отображает UDP порт получателя или отправителя

![image](https://user-images.githubusercontent.com/70852092/95663094-d8eca080-0b44-11eb-8f01-8f878f0b2a62.png)
![image](https://user-images.githubusercontent.com/70852092/95663099-e144db80-0b44-11eb-8f9f-b934f327561a.png)

д) arp.src.hw_mac используется для фильтрации по протоколу ARP, показывает нам MAC адресс получателя

![image](https://user-images.githubusercontent.com/70852092/95663103-ea35ad00-0b44-11eb-91ad-2e9f60c524c2.png)

е) eth.src/dst фильтрует пакету по подуровню MA

eth.dst - фильтр трафика по MAC - адресу получателя

![image](https://user-images.githubusercontent.com/70852092/95663104-f1f55180-0b44-11eb-83ac-abf450329f90.png)

eth.src - фильтр трафика по MAC - адресу отправителя

![image](https://user-images.githubusercontent.com/70852092/95663105-f91c5f80-0b44-11eb-916c-c55c6711f1e7.png)

---

# Практическая №3

### Анализ метаданных:

![image](https://user-images.githubusercontent.com/70852092/95773529-517b6a80-0cc7-11eb-950a-279125852bbf.png)

![image](https://user-images.githubusercontent.com/70852092/95773550-59d3a580-0cc7-11eb-8dc1-66cc2676442a.png)

С помощью утилиты ExifViewer узнал следующую информацию: дату создания фото, размеры, модель устройства и софт обработки фото.

На телефоне в Галерее в сведениях о фото также можно увидеть дату создания фото, размеры, модель устройства, географические координаты местоположения, диафрагму, фокусное расстояние, режим экспозиции, баланс белого, значение яркости, значение ISO, выдержку, схему сжатия, теги.


# Sql Server и FOCA:

![image](https://user-images.githubusercontent.com/70852092/95773744-ba62e280-0cc7-11eb-9e33-72d936bbf44b.png)

Для проверки был взял сайт:  CogPrints.org- электронный архив для самостоятельного архивирования документов в любой области психологии, неврологии и лингвистики, а также многих областях информатики, философии, биологии, а также любых других частях математики.

После поиска, для скачивания было доступно 380+ документов, я выбрал несколько случайных для анализа и изучения метаданных.


Откроем документ word:

![image](https://user-images.githubusercontent.com/70852092/95773834-e8482700-0cc7-11eb-88ce-3e77b868217f.png)

Pdf:

![image](https://user-images.githubusercontent.com/70852092/95773903-0877e600-0cc8-11eb-8d77-7ae67b74cc43.png)


Посмотрим метаданные файлов:

![image](https://user-images.githubusercontent.com/70852092/95773953-247b8780-0cc8-11eb-9c57-94d83a337ef4.png)


По метаданным видим:

Автор документа: Padam gulvani

Дата создания файла: 15.03.2012

Количество страниц, слов и пр. : 7; 3395; ...

Софт для создания: Microsoft Office

Операционная система автора: Windows XP



Метаданные другого документа:

![image](https://user-images.githubusercontent.com/70852092/95774025-4b39be00-0cc8-11eb-992f-f969e4ab347a.png)


Произведя загрузку всех файлов с FOCA, производится автоматический анализ собранных файлов на наличие владельцев файлов, пользуемых ОС и софтах, устройствах, почтах, паролей и т.д.

![image](https://user-images.githubusercontent.com/70852092/95774085-6c021380-0cc8-11eb-8c85-280772bbbb78.png)

![image](https://user-images.githubusercontent.com/70852092/95774140-81773d80-0cc8-11eb-9df6-a19f35bde2dc.png)

![image](https://user-images.githubusercontent.com/70852092/95774174-918f1d00-0cc8-11eb-987c-38ea4eecba6b.png)

![image](https://user-images.githubusercontent.com/70852092/95774216-a370c000-0cc8-11eb-8c79-b3703f9269ba.png)

![image](https://user-images.githubusercontent.com/70852092/95774246-b2f00900-0cc8-11eb-8f89-bf1459d72069.png)

![image](https://user-images.githubusercontent.com/70852092/95774282-c4391580-0cc8-11eb-862d-00d55a7c383c.png)


# Ccleaner:

Создадим дубликат файлов, чтобы проверить работоспособность поиска дубликатов:

![image](https://user-images.githubusercontent.com/70852092/95774347-ecc10f80-0cc8-11eb-8a02-04c3eb1ccf96.png)

![image](https://user-images.githubusercontent.com/70852092/95774407-08c4b100-0cc9-11eb-9460-8dcfaf580bb7.png)


Файлы на рабочем столе не находит, если создать папку-тоже нет, я долго пытался как-нибудь это сделать 

![image](https://user-images.githubusercontent.com/70852092/95774468-26921600-0cc9-11eb-82f2-73b6f2affab9.png)


Диск сканирует, находит дубликаты-инструмент работает:

![image](https://user-images.githubusercontent.com/70852092/95774542-4590a800-0cc9-11eb-9842-8655dd438105.png)


Удалим EXIFViewer с помощью Ccleaner (потом скачаю обратно, если понадобится):

![image](https://user-images.githubusercontent.com/70852092/95774622-6ce77500-0cc9-11eb-8495-91bcbae25146.png)

![image](https://user-images.githubusercontent.com/70852092/95774673-81c40880-0cc9-11eb-8f6d-fffc16bf7d19.png)

Как правило, удаление любого программного обеспечения проходит успешно.


Проведем сканирование системы:

![image](https://user-images.githubusercontent.com/70852092/95774736-a4eeb800-0cc9-11eb-8a23-1bbf53f598d0.png)

В ходе анализа программа нашла то, что можно смело удалить (456 МБ)


# RStudio:

Запустив сканирование основного диска, я вскоре отменил процедуру, потому что она длилась бы очень долго, поэтому решил просканировать съемный носитель

![image](https://user-images.githubusercontent.com/70852092/95912593-adb7ba80-0dab-11eb-9a99-240d4afa58a9.png)


Создадим текстовый файл на флешке и удалим:

![image](https://user-images.githubusercontent.com/70852092/95912362-69c4b580-0dab-11eb-83f7-60621f458936.png)

Проведем повторное сканирование:

![image](https://user-images.githubusercontent.com/70852092/95912422-82cd6680-0dab-11eb-8aed-ea8d26ec5532.png)

После сканирования было показано множество удаленных файлов, я выбрал сортировку по датам:

![image](https://user-images.githubusercontent.com/70852092/95912771-f1122900-0dab-11eb-9f66-e9d445d64a2b.png)

Искомый файл найден:

![image](https://user-images.githubusercontent.com/70852092/95912838-0ab37080-0dac-11eb-95ae-2f07d7e74bf1.png)

Восстанавливаем документ на рабочий стол в созданную папку:

![image](https://user-images.githubusercontent.com/70852092/95912919-26b71200-0dac-11eb-84cc-1d5a9a20e8af.png)


Файл был успешно восстановлен.


Повторяем процедуру создания и удаления текстовика, далее почистим свободное место Ccleaner'ом:

![image](https://user-images.githubusercontent.com/70852092/95913067-5e25be80-0dac-11eb-9ba5-18d58254bf4d.png)

![image](https://user-images.githubusercontent.com/70852092/95913126-739ae880-0dac-11eb-962c-046a2b27d1d8.png)

![image](https://user-images.githubusercontent.com/70852092/95913183-86152200-0dac-11eb-9f42-678c1e9ba976.png)

![image](https://user-images.githubusercontent.com/70852092/95913236-9a591f00-0dac-11eb-9fe0-0235104d18a6.png)

Возвращаемся к восстановлению...

![image](https://user-images.githubusercontent.com/70852092/95913322-b8bf1a80-0dac-11eb-983a-3b3066ff1da9.png)

![image](https://user-images.githubusercontent.com/70852092/95913385-cb395400-0dac-11eb-9b68-83dc9432a633.png)

![image](https://user-images.githubusercontent.com/70852092/95913458-ed32d680-0dac-11eb-9232-b0ab8461fe76.png)

После восстановления я увидел следующее:

![image](https://user-images.githubusercontent.com/70852092/95913511-063b8780-0dad-11eb-94d4-aa36394b9e5e.png)

![image](https://user-images.githubusercontent.com/70852092/95913577-1eaba200-0dad-11eb-99a6-8334e62a552f.png)


Внутри ничего не было, и название тоже изменилось, значит Ccleaner просто сделал битый текстовый документ.

---

# Практическая №4

### Шифрование в windows. EFS

Создадим папку с текстовым документом для эксперимента:



![image](https://user-images.githubusercontent.com/70852092/98444378-627e9680-2122-11eb-8092-b15643b3a1c2.png)



Шифруем папку:



![image](https://user-images.githubusercontent.com/70852092/98444399-804bfb80-2122-11eb-9105-253c196d8d51.png)



Успешно:



![image](https://user-images.githubusercontent.com/70852092/98444418-a2de1480-2122-11eb-8ffc-656ebff6c103.png)




Создадим вторую учетную запись по заданию:

![image](https://user-images.githubusercontent.com/70852092/98444437-b5584e00-2122-11eb-967f-232836bab32d.png)

Заходим под второй учетной записью и пробуем открыть зашифрованную папку:

![image](https://user-images.githubusercontent.com/70852092/98444462-dcaf1b00-2122-11eb-850a-7eb2d7a07f6c.png)

Произвел попытку открытия зашифрованного файла - разумеется, не удалось.

Дальше займемся экспортом сертификата:

![image](https://user-images.githubusercontent.com/70852092/98444475-ee90be00-2122-11eb-8f2d-4cc4f4e409b7.png)



Заходим в реестр:

![image](https://user-images.githubusercontent.com/70852092/98444487-08320580-2123-11eb-9cd5-d1d1d3340576.png)



Экспортируем:

![image](https://user-images.githubusercontent.com/70852092/98444511-28fa5b00-2123-11eb-878a-70d6702c6e34.png)

![image](https://user-images.githubusercontent.com/70852092/98444521-37e10d80-2123-11eb-81e4-f155ad18f68b.png)

![image](https://user-images.githubusercontent.com/70852092/98444534-47605680-2123-11eb-8008-99b6782b5e5a.png)

![image](https://user-images.githubusercontent.com/70852092/98444547-5b0bbd00-2123-11eb-88c2-5ce0b3e2f795.png)

Успешно.



# Cipher

Создаем новые файлы для теста:

![image](https://user-images.githubusercontent.com/70852092/98444586-8b535b80-2123-11eb-9417-ce3305916b42.png)

Шифруем их с помощью команды cipher /e /s:C:\shifr :

![image](https://user-images.githubusercontent.com/70852092/98444599-a2924900-2123-11eb-9744-31197eda2a50.png)

Проверяем статус шифровки командой cipher /s:E:\shifr :

![image](https://user-images.githubusercontent.com/70852092/98444621-c0f84480-2123-11eb-861e-07fd550ca249.png)

Посмотрим подробные сведения о зашифрованном файле командой cipher /c /s:E:\shifr :

![image](https://user-images.githubusercontent.com/70852092/98444642-dff6d680-2123-11eb-87e3-5b30cf3f32d1.png)

Теперь командой cipher /X создадим резервную копию сертификата EFS:

![image](https://user-images.githubusercontent.com/70852092/98444663-fdc43b80-2123-11eb-99b3-fa7483724e91.png)

Успешно:

![image](https://user-images.githubusercontent.com/70852092/98444690-22b8ae80-2124-11eb-9540-39b68fd506f7.png)

Заходим с другого пользователя и открываем файл, который только что сохранили:

![image](https://user-images.githubusercontent.com/70852092/98444714-3fed7d00-2124-11eb-83b9-763d2d088ef2.png)

Дальше пробуем открыть этот зашифрованный файл:

![image](https://user-images.githubusercontent.com/70852092/98444741-66131d00-2124-11eb-820a-b224afef8faa.png)

Успешно!



# BitLocker

Вставляем флешку и создаем файл для теста:

![image](https://user-images.githubusercontent.com/70852092/98444772-a1ade700-2124-11eb-9750-619d6ae3b744.png)

Включаем БитЛокер (который почему-то для любой флешки на моем ПК с windows 10 PRO никак не запускается, только для диска выдает, форматировал флешку по-разному):

![image](https://user-images.githubusercontent.com/70852092/98444809-da4dc080-2124-11eb-8409-895ef3e3dcb8.png)

![image](https://user-images.githubusercontent.com/70852092/98444814-ed609080-2124-11eb-86e9-87ecf5633961.png)

Мне дали зашифровать на другом ПК:

![image](https://user-images.githubusercontent.com/70852092/98444825-09643200-2125-11eb-9641-cfcce6f70a33.png)

![image](https://user-images.githubusercontent.com/70852092/98444837-20a31f80-2125-11eb-8ea6-dc46d572f26e.png)

![image](https://user-images.githubusercontent.com/70852092/98444847-30baff00-2125-11eb-9100-28ba66088ba9.png)

![image](https://user-images.githubusercontent.com/70852092/98444857-46302900-2125-11eb-91e4-2c23df1527f4.png)

Извлекаем флешку и вставляем ее обратно:

![image](https://user-images.githubusercontent.com/70852092/98445672-e9833d00-2129-11eb-9748-233abebc9eb3.png)

Шифрование флешки прошло успешно.

При открытии требуется ввести пароль:

![image](https://user-images.githubusercontent.com/70852092/98445685-04ee4800-212a-11eb-8c58-55d7b0bb2488.png)

Вводим пароль, надо создать текстовый файл с фамилией и именем по заданию:

![image](https://user-images.githubusercontent.com/70852092/98445698-1df6f900-212a-11eb-8202-c564c2bbd669.png)

Не получилось почему-то открыть флешку:

![image](https://user-images.githubusercontent.com/70852092/98445730-4ed72e00-212a-11eb-8987-15e1d3cf3e68.png)

![image](https://user-images.githubusercontent.com/70852092/98445740-5e567700-212a-11eb-9645-e9cb60a3587c.png)

Отформатировал флешку, пароль удалился и ладно.



# VeraCrypt

Создадим папку с текстовым файлом для теста и зашифруем:



![image](https://user-images.githubusercontent.com/70852092/98445796-aecdd480-212a-11eb-8fa9-2fea24132e30.png)



Используем шифрование AES:

![image](https://user-images.githubusercontent.com/70852092/98445835-df157300-212a-11eb-81f7-f87d050008fa.png)

Выбираем размер и пароль:

![image](https://user-images.githubusercontent.com/70852092/98445849-1126d500-212b-11eb-8c63-fcddf3d01b0c.png)

![image](https://user-images.githubusercontent.com/70852092/98446329-e38f5b00-212d-11eb-9cc9-6baaae892cb6.png)

Ждем окончания процесса и двигаем мышкой:

![image](https://user-images.githubusercontent.com/70852092/98445862-2b60b300-212b-11eb-9060-e8493b128141.png)

Готово:

![image](https://user-images.githubusercontent.com/70852092/98445889-4e8b6280-212b-11eb-8023-c74aef4e3a64.png)

Смонтируем том:

![image](https://user-images.githubusercontent.com/70852092/98445904-6531b980-212b-11eb-91ad-d374046f2e6a.png)

Успешно смонтировали:

![image](https://user-images.githubusercontent.com/70852092/98445919-7d093d80-212b-11eb-9271-a78b7ef97fdd.png)

Файл в репозиторий добавлен, пароль: 12345

---

# Практическая №5

### 1.7 Определение типа hash

Установим следующую утилиту

![image](https://user-images.githubusercontent.com/70852092/102690561-543e9280-4217-11eb-9ebe-3437da890ca4.png)

В файле /etc/shadow сохраняем пароль пользователя системы:

![image](https://user-images.githubusercontent.com/70852092/102690578-6f110700-4217-11eb-8797-128fe9e9dee4.png)

![image](https://user-images.githubusercontent.com/70852092/102690587-7fc17d00-4217-11eb-8ee9-90b4ec8dfe0e.png)

Скопировали значение hash пользователя и определили тип.

![image](https://user-images.githubusercontent.com/70852092/102690613-9d8ee200-4217-11eb-8257-fa88d52b1877.png)

### 1.8 Создание hash в Linux

Добавляем нового пользователя:

![image](https://user-images.githubusercontent.com/70852092/102690675-1e4dde00-4218-11eb-82a8-eba145529406.png)

Заменяем хэш в новом пользователе и обновляем пароль:

![image](https://user-images.githubusercontent.com/70852092/102690713-581ee480-4218-11eb-9e76-646fca3428ca.png)

![image](https://user-images.githubusercontent.com/70852092/102690724-65d46a00-4218-11eb-87a0-01fcab9a3b59.png)

Рассчитываем хешированный пароль:

![image](https://user-images.githubusercontent.com/70852092/102690736-7dabee00-4218-11eb-99a3-7d309ba932c7.png)

### 1.9 Проверка контрольных сумм

Копируем "group" в домашнюю папку, затем подсчитаем и сохраним контрольную сумму:

![image](https://user-images.githubusercontent.com/70852092/102690757-af24b980-4218-11eb-822d-3dbff6265696.png)

![image](https://user-images.githubusercontent.com/70852092/102690770-cb285b00-4218-11eb-8d3c-db012951fbdc.png)

###Удалим первую строку и проверим:

![image](https://user-images.githubusercontent.com/70852092/102690800-088ce880-4219-11eb-8b6c-10a8f7f6d654.png)

![image](https://user-images.githubusercontent.com/70852092/102690846-56a1ec00-4219-11eb-8c1e-9d6ddfe71498.png)

![image](https://user-images.githubusercontent.com/70852092/102690858-628dae00-4219-11eb-82f2-98d5b38dad4b.png)

Как видим, файл поврежден.

###Поменяем название и сравним еще раз:

![image](https://user-images.githubusercontent.com/70852092/102690958-04ad9600-421a-11eb-8f8c-dc1681944cd6.png)

Значение не поменялось.

###2.1 Шифрование с помощью пароля

Создадим и зашифруем файл:

![image](https://user-images.githubusercontent.com/70852092/102691129-4559df00-421b-11eb-9c89-84e954ef2ab7.png)

Расшифровка:

![image](https://user-images.githubusercontent.com/70852092/102691135-5571be80-421b-11eb-8681-9ba2ad26d0fb.png)

###2.1.2 Шифрование с использованием ключей

Создадим файл и ключ к нему:

![image](https://user-images.githubusercontent.com/70852092/102691146-7cc88b80-421b-11eb-9b0a-8bf44cf24a23.png)

![image](https://user-images.githubusercontent.com/70852092/102691154-881bb700-421b-11eb-93be-09ba4e814349.png)

Список доступных ключей:

![image](https://user-images.githubusercontent.com/70852092/102691170-a386c200-421b-11eb-9550-fb42e8a1e6e8.png)

Экспортируем публичный ключ:

![image](https://user-images.githubusercontent.com/70852092/102691201-c3b68100-421b-11eb-817b-ebf13af05b77.png)

Импортируем ключ:

![image](https://user-images.githubusercontent.com/70852092/102691221-e5176d00-421b-11eb-8bf9-246271a5039f.png)

Редактируем ключ:

![image](https://user-images.githubusercontent.com/70852092/102691236-fc565a80-421b-11eb-8ef3-b16c5f29e83a.png)

Устанавливаем уровень доверия (trust):

![image](https://user-images.githubusercontent.com/70852092/102691248-13954800-421c-11eb-9e1d-bddc3749418e.png)

###2.1.3 Подписи и шифрование

Создадим текстовый файл и далее подпись для него:

![image](https://user-images.githubusercontent.com/70852092/102691267-39bae800-421c-11eb-8e55-4bb8e85cd29f.png)

До изменения:

![image](https://user-images.githubusercontent.com/70852092/102691278-50613f00-421c-11eb-9dd1-c71e91769762.png)

Меняем файл:

![image](https://user-images.githubusercontent.com/70852092/102691317-9cac7f00-421c-11eb-9ec8-8c3c5baaefe6.png)

После:

![image](https://user-images.githubusercontent.com/70852092/102691325-a930d780-421c-11eb-8709-4fd05e548322.png)

###Отправка письма

Скачиваем нужные программы.

Добавляем ключ:

![image](https://user-images.githubusercontent.com/70852092/102691369-09c01480-421d-11eb-9129-c587e01cdf2a.png)

Экспортируем ключ:

![image](https://user-images.githubusercontent.com/70852092/102691380-20ff0200-421d-11eb-8677-005eae9f8e24.png)

Переходим на репозиторий открытых ключей и загружаем ключ:

![image](https://user-images.githubusercontent.com/70852092/102691408-560b5480-421d-11eb-913f-9d2ed0239338.png)

Подтверждаем с помощью перехода по ссылке.

![image](https://user-images.githubusercontent.com/70852092/102691415-6de2d880-421d-11eb-9c6f-9508ae8927cb.png)

![image](https://user-images.githubusercontent.com/70852092/102691418-789d6d80-421d-11eb-912c-439df14ce3c4.png)

Импортировали обнаруженный ключ(не тот наверное):

![image](https://user-images.githubusercontent.com/70852092/102691624-e26a4700-421e-11eb-9893-9e96b0063221.png)

![image](https://user-images.githubusercontent.com/70852092/102691771-fe221d00-421f-11eb-9aa0-9d2f820629ec.png)

![image](https://user-images.githubusercontent.com/70852092/102691780-16923780-4220-11eb-9e8e-be199229db0b.png)

---
