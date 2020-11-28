# OIB-PRACTICA
### [Перемотка к практической №3 (КЛИКАБЕЛЬНО)](https://github.com/Kozachok-Nikolay/OIB-PRACTICA/blob/master/README.md#практическая-3)
### [Перемотка к практической №4 (КЛИКАБЕЛЬНО)](https://github.com/Kozachok-Nikolay/OIB-PRACTICA/blob/master/README.md#практиеческая-4)
### [Перемотка к практической №5 (КЛИКАБЕЛЬНО)](https://github.com/Kozachok-Nikolay/OIB-PRACTICA/blob/master/README.md#практическая-5) 
### [Перемотка к практической №6 (КЛИКАБЕЛЬНО)](https://github.com/Kozachok-Nikolay/OIB-PRACTICA/blob/master/README.md#практическая-6)
### [Перемотка к практической №7 (КЛИКАБЕЛЬНО)](https://github.com/Kozachok-Nikolay/OIB-PRACTICA/blob/master/README.md#практическая-7)

# Практическая №1
Компания ООО «Umbrella». Управление компании использует телефонную связь и защищенное интернет соединение. Бухгалтерия использует телефонную связь и защищенное интернет соединение.
Штат – 100 сотрудников. 
10 – руководство.
10 – отдел безопасности. 
25 – ученые.
5 – бухгалтерия.
50 – вооруженная охрана.
Руководство получает уведомление по поводу проведения секретных экспериментов в лаборатории, используя телефонную связь (передача шифрованной речи осуществляется по каналам CSD 9600 бит/с) и уведомление о передаче этапов работы на компьютер. Передача этапов работы происходит через защищенное интернет соединение. Вся документация защищена паролем. Имеет полный доступ ко всем помещениям организации.
Отдел безопасности занимается организацией и обеспечением защиты любой информации, полученной на территории организации. Обеспечивают руководство физическим вводом ключа при получении. Использует любую связь, исключительно скрытую. Имеет доступ к местам хранения информации организации.
Ученые получают указания от руководства по проведению экспериментов. Результаты сохраняются на сервер организации. Имеют доступ к помещениям для проведения экспериментов.
Бухгалтерия занимается учетом финансов и подтверждением документов на те или иные ресурсы, требующиеся для экспериментов. Используют телефонную связь. Имеет доступ к помещению бухгалтерии.
Вооруженная охрана находится на территории всей организации. На выходе из организации установлен пункт досмотра. Каждый входящий и выходящий из организации обязан пройти досмотр на присутствие запрещенных предметов. Имеет доступ к местам перемещения по организации, могут запросить доступ к другим помещениям по необходимости.
Технический регламент для отдела безопасности:
-Постоянный анализ информационного пространства с целью выявления уязвимостей.
-Своевременное обнаружение проблем, потенциально способных повлиять на информационную безопасность, корректировка моделей угроз и нарушителя.
-Исключать возможность доступа третьих лиц к документам, содержащим конфиденциальную информацию.
-Контролировать состояние рабочего места, сообщать руководству обо всех ситуациях, имеющих характер инцидентов информационной безопасности.
-Регулярно выявлять основные пути и способы попадания зараженной вирусом информации в систему организации.
Инструкция для специалиста по безопасности:
Специалист должен знать:
-Основы трудового законодательства.
-Законодательство о безопасности, о защите информации, об оперативно-розыскной деятельности и др.
-Устав организации, правила внутреннего порядка.
-Характеристики технических средств защиты объектов, информации от несанкционированного доступа к ним.
-Тактику защиты объектов, информации, персонала предприятия от преступных посягательств.
-Характеристику технических средств (системы сигнализации, связи, защиты информации, пр.).
# Практическая №2
Для работы был взят сайт: loyalty-world.ru
***
чтобы узнать ip - адрес пользуемся командами ping и nslookup в консоли.
![Screenshot_1](https://user-images.githubusercontent.com/70717332/94065559-feaf4100-fdf3-11ea-9e68-337481259934.png)
***
ip - адрес сайта: 185.165.123.206
***
далее изучение nslookup, начнем с команды -query=mx
![Screenshot_2](https://user-images.githubusercontent.com/70717332/94066618-64e89380-fdf5-11ea-9872-4518bad7c674.png)
Это значит, что у данного домена серверная почта: mail-s19.1gb.ru
***
затем идем к -query=soa
![Screenshot_3](https://user-images.githubusercontent.com/70717332/94066960-dd4f5480-fdf5-11ea-854f-c4c9f4f74fcf.png)
если перевести с английского, отсюда получаем информацию о:
первичное название сервера, почту администратора сервера домена, серийный номер, период времени (в секундах), через который вторичный DNS-сервер отправит запрос первичному, чтобы проверить, поменялся ли серийный номер. Интервал для повторного соединения с первичным DNS-сервером, если он по каким-то причинам не смог ответить на запрос. И так далее...
***
далее назначение работы команды -query=nx я так и не понял
***
последней командой стала:-type=any, мне выдало следующее:
![Screenshot_4](https://user-images.githubusercontent.com/70717332/94068151-7cc11700-fdf7-11ea-9584-74705bf4976c.png)
информации нет, а значит и суда нет
***
изучение трафика сайт можно произвести с помощью wireshark и фильтра ip.src == 185.165.123.206(ip сайта)
![Screenshot_5](https://user-images.githubusercontent.com/70717332/94069209-dc6bf200-fdf8-11ea-8619-4b49852dd221.png)
***
ip.dst отвечает за трафик отправленый на ip
![Screenshot_6](https://user-images.githubusercontent.com/70717332/94069519-6916b000-fdf9-11ea-8643-f4b3d9f5aa3f.png)
***
теперь мы знаем, что подключение к сайту происходит через порт 80, а робтает через протокол HTTP и TCP
***
ip.addr отвечает за фильтрацию трафика, в котором упоминается этот ip
![Screenshot_7](https://user-images.githubusercontent.com/70717332/94069869-fb1eb880-fdf9-11ea-8bdf-22387f9b57a3.png)
***
udp.src - не работает 
![Screenshot_8](https://user-images.githubusercontent.com/70717332/94069947-1c7fa480-fdfa-11ea-8406-01d818046369.png)
***
arp.src.hw_mac используется для фильтрации по ARP протокола по mac - адресу
![Screenshot_9](https://user-images.githubusercontent.com/70717332/94070232-81d39580-fdfa-11ea-959e-c63dc254169d.png)
***
eth.dst - фильтр трафика по mac - адресу получателя
![Screenshot_10](https://user-images.githubusercontent.com/70717332/94070459-e5f65980-fdfa-11ea-9de2-000726628ab7.png)
***
eth.src - фильтр трафика по mac - адресу отправителя
![Screenshot_11](https://user-images.githubusercontent.com/70717332/94070851-949a9a00-fdfb-11ea-8f58-16f00c23a95a.png)

---

# Практическая №3

### Анализ метаданных:

Для анализа я взял случайную фотографию с компьютера своей мамы:


![Screenshot_1](https://user-images.githubusercontent.com/70717332/94712767-965fe280-0352-11eb-86fc-723f2b400942.png)


С помощью утилиты ExifViewer можно узнать следующую информацию:

дату создания снимка: 15.06.2017, почту копирайта: firatdemirr@gmail.com, модель камеры: Nikon D700, и софт обработки фотографии: Adobe photoshop cs 3



### Sql Server и FOCA:

Сервер работает, фока тоже, значит пришло время красть метаданные с сайтов.

Для проверки я взял сайт www.nalog.ru

После поиска, для скачивания было доступно 1500+ документов, я выбрал несколько случайных для анализа и изучения метаданных.


![Screenshot_12](https://user-images.githubusercontent.com/70717332/94720978-d6789280-035d-11eb-82ef-0bf3475475cd.png)


Посмотрим метаданные нескольких файлов: 

![Screenshot_13](https://user-images.githubusercontent.com/70717332/94721993-52bfa580-035f-11eb-83f6-c1769f8a04ef.png)



![Screenshot_14](https://user-images.githubusercontent.com/70717332/94721996-53583c00-035f-11eb-87d3-d2c6e93284e2.png)



![Screenshot_15](https://user-images.githubusercontent.com/70717332/94721998-53f0d280-035f-11eb-9575-167a9a37be7c.png)



![Screenshot_16](https://user-images.githubusercontent.com/70717332/94721999-53f0d280-035f-11eb-9654-ced873eecff9.png)


По данным метаданным можно понять:

Автор документа: Кузьмина Ирина Витальевна

Дата создания файла: 04.12.2014

Софт для создания: Microsoft office

Операционная система автора: Windows XP


Сам документ не очень интересный:


![Screenshot_17](https://user-images.githubusercontent.com/70717332/94722333-d5e0fb80-035f-11eb-9350-43cf95987c16.png)


Из общего анализа фоки можно узнать:


![Screenshot_21](https://user-images.githubusercontent.com/70717332/94722660-4851db80-0360-11eb-83f6-fa800c72c2f5.png)



![Screenshot_18](https://user-images.githubusercontent.com/70717332/94722663-48ea7200-0360-11eb-908b-85026d6044a5.png)



![Screenshot_19](https://user-images.githubusercontent.com/70717332/94722664-49830880-0360-11eb-86b1-d7c9deb98448.png)



![Screenshot_20](https://user-images.githubusercontent.com/70717332/94722667-49830880-0360-11eb-8702-769c715d6197.png)


![Screenshot_21](https://user-images.githubusercontent.com/70717332/94726787-67ec0280-0366-11eb-9bbd-63e10fbcf07e.png)


Имена всех пользователей, ОСи (у кого-то даже Windows 98), Софты для использования и т.д.

### Ccleaner:

С данным ПО я знаком, поэтому сходу создаем дубликат файлов чтобы проверить работоспособность поиска дубликатов:


![Screenshot_22](https://user-images.githubusercontent.com/70717332/94726702-4854da00-0366-11eb-9721-5056804e82f0.png)

Оригиналы я оставил на рабочем столе, а их копии поместил в папку. К сожалению, программе не удалось найти их, как бы я не старался :(



![Screenshot_23](https://user-images.githubusercontent.com/70717332/94726708-49860700-0366-11eb-8a59-0103e3e7c196.png)



Далее я решил удалить компилятор с помощью Ccleaner:



![Screenshot_24](https://user-images.githubusercontent.com/70717332/94726710-49860700-0366-11eb-9660-2d5124080aaf.png)



![Screenshot_25](https://user-images.githubusercontent.com/70717332/94726711-4a1e9d80-0366-11eb-98a4-b9d66856aa18.png)


Удаление прошло успешно!



Следом проводим сканирование системы:



![Screenshot_26](https://user-images.githubusercontent.com/70717332/94726712-4a1e9d80-0366-11eb-989b-8e7f0c3e3e8d.png)



В итоге программа нашла приличное количество мусора (464 МБ)

### RStudio:

Запустив программу, я решил просканировать съемный носитель, потому что сканирование основного диска длилось бы очень долго



![Screenshot_28](https://user-images.githubusercontent.com/70717332/94729984-34f83d80-036b-11eb-90bd-a0a824360ea0.png)

После сканирования было показано множество удаленных файлов, я решил поставить сортировку по датам:



![Screenshot_29](https://user-images.githubusercontent.com/70717332/94730494-fa42d500-036b-11eb-961a-0145f1034231.png)

Теперь переходим к эксперементальной части

Создаем текстовый файл на флешке и удаляем:



![Screenshot_30](https://user-images.githubusercontent.com/70717332/94730822-7b9a6780-036c-11eb-9395-f7a10e8f5833.png)



Проводоим повтороное сканирование: 



![Screenshot_31](https://user-images.githubusercontent.com/70717332/94731000-c5834d80-036c-11eb-968a-e745b20ab1d3.png)



Искомый файл найден: 



![Screenshot_32](https://user-images.githubusercontent.com/70717332/94731719-eac48b80-036d-11eb-882c-e7e7088d5a9c.png)


Восстанавливем на рабочий стол: 



![Screenshot_33](https://user-images.githubusercontent.com/70717332/94731886-2a8b7300-036e-11eb-81ba-6df191e7e4b4.png)



Файл был успешно восстановлен:



![Screenshot_34](https://user-images.githubusercontent.com/70717332/94731956-43942400-036e-11eb-918f-a994cbeadec2.png)


Повторяем процедурю создания и удаления текстовика, пробуем почистить все Ccleaner'ом:



![Screenshot_35](https://user-images.githubusercontent.com/70717332/94732350-d634c300-036e-11eb-938d-1edd56a677c2.png)



Ждем:



![Screenshot_36](https://user-images.githubusercontent.com/70717332/94732352-d6cd5980-036e-11eb-8e94-293ddbce01e9.png)



После долгих 30ти минут вылезло окошко с успешным завершением стирания диска, но я забыл сделать скрин :(

Возвращаемся к восстанавлению...



![Screenshot_37](https://user-images.githubusercontent.com/70717332/94735422-683eca80-0373-11eb-910b-f7d18d81c892.png)



После восстановления я увидел следующее: 



![Screenshot_38](https://user-images.githubusercontent.com/70717332/94736242-98d33400-0374-11eb-80d7-50baa01004d8.png)



Сначала я подумал, что Cclenaer никак не подействовал, но.... после восстановления, я увидел внутренности текстовика:



![Screenshot_39](https://user-images.githubusercontent.com/70717332/94736353-c7e9a580-0374-11eb-8fa3-1df1f5def96a.png)



Внутри ничего не было, и название тоже почему-то изменилось, значит Ccleaner просто сделал битый текстовик

---
# Практиеческая №4

### Шифрование в windows. EFS

Создаем папку с текстовым документом для эксперимента:



![Screenshot_2](https://user-images.githubusercontent.com/70717332/95769728-01010e80-0cc1-11eb-9672-7ef9c9c6234e.png)



![Screenshot_3](https://user-images.githubusercontent.com/70717332/95770034-740a8500-0cc1-11eb-82c3-36b593ee3875.png)



Шифруем папку:



![Screenshot_4](https://user-images.githubusercontent.com/70717332/95770035-74a31b80-0cc1-11eb-8d66-c79e55c980da.png)



Успешно:



![Screenshot_5](https://user-images.githubusercontent.com/70717332/95770036-74a31b80-0cc1-11eb-85a4-97cbd92c8008.png)



Создаем вторую учетную запись для теста:



![Screenshot_6](https://user-images.githubusercontent.com/70717332/95770037-753bb200-0cc1-11eb-84f2-8ff132684df9.png)



Заходим под второй учеткой и пробуем открыть зашифрованную папку:



![Screenshot_8](https://user-images.githubusercontent.com/70717332/95770459-17f43080-0cc2-11eb-9af0-cdb0fb415746.png)



Как мы видим, безуспешно :)

Теперь займемся экспортом сертификата:



![Screenshot_9](https://user-images.githubusercontent.com/70717332/95770041-75d44880-0cc1-11eb-8d7c-baf5dc7cbff4.png)



Заходим в реестр:



![Screenshot_10](https://user-images.githubusercontent.com/70717332/95770042-75d44880-0cc1-11eb-8781-a8f231e7e51d.png)



Сохраняем\экспортируем:



![Screenshot_11](https://user-images.githubusercontent.com/70717332/95770047-766cdf00-0cc1-11eb-9037-bf0e3f867e0b.png)




![Screenshot_12](https://user-images.githubusercontent.com/70717332/95770048-77057580-0cc1-11eb-8507-036676cc7951.png)



![Screenshot_13](https://user-images.githubusercontent.com/70717332/95770033-7371ee80-0cc1-11eb-864a-0612483b4119.png)



Успешно :)

---

### Cipher

Создаем новые файлы для теста:



![Screenshot_14](https://user-images.githubusercontent.com/70717332/95772208-0bbda280-0cc5-11eb-8058-06ba3055fafd.png)



Шифруем их с помощью команды cipher /e /s:E:\shifr :



![Screenshot_15](https://user-images.githubusercontent.com/70717332/95772210-0bbda280-0cc5-11eb-80eb-09bed2713485.png)



Проверяем статус шифровки командой cipher /s:E:\shifr :



![Screenshot_16](https://user-images.githubusercontent.com/70717332/95772212-0c563900-0cc5-11eb-9e7c-de952d7a20f9.png)



Посмотрим подробные сведения командой cipher /c /s:E:\shifr :



![Screenshot_17](https://user-images.githubusercontent.com/70717332/95772216-0ceecf80-0cc5-11eb-9f66-8d4ba21c662c.png)



Теперь, командой cipher /X сохраним резервную копию сертификата EFS: 



![Screenshot_18](https://user-images.githubusercontent.com/70717332/95772218-0ceecf80-0cc5-11eb-9520-6a13c49579ff.png)



Успешно:



![Screenshot_19](https://user-images.githubusercontent.com/70717332/95772207-0b250c00-0cc5-11eb-886f-4a37decc5d3a.png)



Заходим с другого пользователя и открываем файл, который только что сохранили:



![Screenshot_20](https://user-images.githubusercontent.com/70717332/95773945-1fb6d380-0cc8-11eb-998b-1a46962dcff6.png)



Теперь идем к зашифрованному файлу и пробуем открыть:



![Screenshot_21](https://user-images.githubusercontent.com/70717332/95773942-1d547980-0cc8-11eb-89b7-492709887461.png)



Успешно! :)

---

### BitLocker

Вставляем влешку и создаем файл для теста: 



![Screenshot_22](https://user-images.githubusercontent.com/70717332/95775411-0e22fb00-0ccb-11eb-9920-ace65418165f.png)



Включаем БитЛокер:



![Screenshot_23](https://user-images.githubusercontent.com/70717332/95775415-0ebb9180-0ccb-11eb-96a0-d1db0d5131f1.png)



Шифруем:



![Screenshot_24](https://user-images.githubusercontent.com/70717332/95775418-0f542800-0ccb-11eb-89a6-9d19e566e33f.png)



![Screenshot_25](https://user-images.githubusercontent.com/70717332/95775419-0f542800-0ccb-11eb-87a4-982a655af135.png)



![Screenshot_26](https://user-images.githubusercontent.com/70717332/95775422-0fecbe80-0ccb-11eb-91d7-c31c7aa29192.png)



![Screenshot_27](https://user-images.githubusercontent.com/70717332/95775423-10855500-0ccb-11eb-9537-952cae348021.png)



![Screenshot_28](https://user-images.githubusercontent.com/70717332/95775424-111deb80-0ccb-11eb-8b0d-70e2c2b0f760.png)



Вытаскиваем влешку и вставляем обратно:



![Screenshot_29](https://user-images.githubusercontent.com/70717332/95775425-111deb80-0ccb-11eb-9e60-d5be2a0d120e.png)



Как мы видим, шифрование флешки прошло успешно

При открытии просит ввести пароль:



![Screenshot_30](https://user-images.githubusercontent.com/70717332/95775427-11b68200-0ccb-11eb-8029-d31dbac25097.png)



Вводим пароль, заходим и создаем текстовик с фамилией и именем (так написано в задании):



![Screenshot_31](https://user-images.githubusercontent.com/70717332/95775428-11b68200-0ccb-11eb-9efc-b4b3e675e9a4.png)

---
### VeraCrypt

Создаем в очередной раз папку с текстовиком для теста и шифруем:



![Screenshot_32](https://user-images.githubusercontent.com/70717332/95779354-9062ed80-0cd2-11eb-9a0c-a35f4b8852f2.png)



Используем шифрование AES: 



![Screenshot_33](https://user-images.githubusercontent.com/70717332/95779358-91941a80-0cd2-11eb-9611-a65fec7572af.png)



Выбираем размер и пароль:



![Screenshot_34](https://user-images.githubusercontent.com/70717332/95779361-922cb100-0cd2-11eb-898f-fe614751a92e.png)



![Screenshot_35](https://user-images.githubusercontent.com/70717332/95779363-92c54780-0cd2-11eb-8a9a-aaf65f4300fc.png)



Фиксируем процесс и разъяренно двигаем мышкой:



![Screenshot_36](https://user-images.githubusercontent.com/70717332/95779366-948f0b00-0cd2-11eb-8ff9-b8b3deb0b698.png)



Готово:



![Screenshot_37](https://user-images.githubusercontent.com/70717332/95779368-9527a180-0cd2-11eb-8680-3e508df06381.png)



![Screenshot_38](https://user-images.githubusercontent.com/70717332/95779369-9658ce80-0cd2-11eb-9943-503a5db0121a.png)



Смонтируем том:



![Screenshot_39](https://user-images.githubusercontent.com/70717332/95779346-8e992a00-0cd2-11eb-88be-bab2da725136.png)



Ждемс:



![Screenshot_40](https://user-images.githubusercontent.com/70717332/95779352-9062ed80-0cd2-11eb-8050-9ec66db05b9a.png)



Успешно смонтировали:



![Screenshot_41](https://user-images.githubusercontent.com/70717332/95780228-2b0ffc00-0cd4-11eb-94cc-ff6174992270.png)



Файл в репозиторий добавил, пароль 12345

---
# Практическая №5
---
## 1.7 Определение типа hash

Устанавливаем утилиту:



![Screenshot_1](https://user-images.githubusercontent.com/70717332/97482129-cb1d8480-1966-11eb-831d-fa428ed72213.png)



Заходим в шадоу:


![Screenshot_2](https://user-images.githubusercontent.com/70717332/97482257-fef8aa00-1966-11eb-8c8a-a581c9cb9d07.png)



Мотаем вниз и копируем hash. Узнаем тип:



![Screenshot_3](https://user-images.githubusercontent.com/70717332/97483227-3f0c5c80-1968-11eb-997d-b1c3772dc7a6.png)

## 1.8 Создание hash в Linux

Добавляем нового пользователя:



![Screenshot_4](https://user-images.githubusercontent.com/70717332/97483267-49c6f180-1968-11eb-83e5-43cd3fc4080e.png)



Заменяем хэш в новом юзере и обновляем пароль:
---
![Screenshot_5](https://user-images.githubusercontent.com/70717332/97483415-74b14580-1968-11eb-880c-d4a2113f341b.png)



После добавления нового пользователя были небольшие проблемы с правами:
---
![Screenshot_6](https://user-images.githubusercontent.com/70717332/97483775-ef7a6080-1968-11eb-9d02-2bd1b6b7ab8a.png)



Но я справился и добрался до хэша(после танцев с бубном :D):
---
![Screenshot_7](https://user-images.githubusercontent.com/70717332/97483839-028d3080-1969-11eb-9bd9-a0fd610b9dcd.png)



Рассчитываем хэшированный пароль:
---
![Screenshot_8](https://user-images.githubusercontent.com/70717332/97483904-1a64b480-1969-11eb-8d23-b44b180f7eb5.png)



## 1.9 Проверка контрольных сумм
---
Копируем "Group" в домашнюю папку:
---
![Screenshot_9](https://user-images.githubusercontent.com/70717332/97485104-bb07a400-196a-11eb-9760-797fd3bb8851.png)



Подсчитаем и сохрним котрольную сумму:
---
![Screenshot_10](https://user-images.githubusercontent.com/70717332/97485136-c9ee5680-196a-11eb-8184-eaa0ed8d3ff8.png)



![Screenshot_11](https://user-images.githubusercontent.com/70717332/97485138-ca86ed00-196a-11eb-9c70-84237d43f712.png)



Удалим первую строку и проверим:
---
![Screenshot_12](https://user-images.githubusercontent.com/70717332/97485142-ca86ed00-196a-11eb-8ec8-af7e0928fc15.png)



![Screenshot_13](https://user-images.githubusercontent.com/70717332/97485145-ca86ed00-196a-11eb-80ec-c0fda4b45fc1.png)



![Screenshot_14](https://user-images.githubusercontent.com/70717332/97485147-cb1f8380-196a-11eb-9992-a7673f23da89.png)



Как мы видим, файл поврежден.

Поменяем название и сравним еще раз:
---
![Screenshot_15](https://user-images.githubusercontent.com/70717332/97485132-c955c000-196a-11eb-86de-a95a22f78a87.png)



Значение не поменялось.
## 2.1 Шифрование с помощью пароля
Создаем и шифруем файл:
---
![Screenshot_16](https://user-images.githubusercontent.com/70717332/97487621-2737d700-196e-11eb-935a-2b88bf4a9e06.png)



Не знаю, похоже ли это на расшифорвку:
---
![Screenshot_17](https://user-images.githubusercontent.com/70717332/97487613-269f4080-196e-11eb-9bd5-1f2b58f9046a.png)



## 2.1.2 Шифрование с использованием ключей

Создаем файл и ключ к нему
---



![Screenshot_18](https://user-images.githubusercontent.com/70717332/97491242-ee4e3100-1972-11eb-83c5-b6471d9aeeea.png)



![Screenshot_19](https://user-images.githubusercontent.com/70717332/97491243-eee6c780-1972-11eb-9b41-976e8ddb3b1c.png)



![Screenshot_20](https://user-images.githubusercontent.com/70717332/97491245-eee6c780-1972-11eb-9bd7-153c22abd37f.png)



![Screenshot_21](https://user-images.githubusercontent.com/70717332/97491246-ef7f5e00-1972-11eb-8cb9-4982cdacd6a4.png)



Смотрим доступные:
---
![Screenshot_22](https://user-images.githubusercontent.com/70717332/97491249-ef7f5e00-1972-11eb-8837-4fa4360bf973.png)



Экспортируем:
---
![Screenshot_23](https://user-images.githubusercontent.com/70717332/97491250-f017f480-1972-11eb-9674-26c64d88a7a1.png)



Импортируем:
---
![Screenshot_24](https://user-images.githubusercontent.com/70717332/97491251-f017f480-1972-11eb-848a-1545f83c05c9.png)



Редактируем ключ:
---
![Screenshot_25](https://user-images.githubusercontent.com/70717332/97491253-f017f480-1972-11eb-9756-b8e392164db8.png)



Устанавливаем уровень доверия (trust):
---
![Screenshot_26](https://user-images.githubusercontent.com/70717332/97491255-f0b08b00-1972-11eb-9fb2-e77deb71c6c2.png)



## 2.1.3 Подписи и шифрование
Создаем текстовик и далем подпись для него:
---
![Screenshot_27](https://user-images.githubusercontent.com/70717332/97491256-f0b08b00-1972-11eb-8a2f-11fe1ee796b3.png)



До изменения: 
---
![Screenshot_28](https://user-images.githubusercontent.com/70717332/97491257-f1492180-1972-11eb-8bfe-c5f4a9cc04de.png)



Меняем файл:
---
![Screenshot_29](https://user-images.githubusercontent.com/70717332/97492183-40dc1d00-1974-11eb-9c2b-4868de9d9a27.png)



После:
---
![Screenshot_30](https://user-images.githubusercontent.com/70717332/97492186-4174b380-1974-11eb-8e40-336840d97c0a.png)

## Отправка письма
Скачиваем весь софт

Добавляем ключ:
---
![Screenshot_31](https://user-images.githubusercontent.com/70717332/97497673-ee9efa00-197b-11eb-8408-c9c87c95c73e.png)



Делаем все по инструкции:
---
![Screenshot_32](https://user-images.githubusercontent.com/70717332/97497674-ef379080-197b-11eb-83b0-032e97367072.png)



Экспортируем ключ:
---
![Screenshot_33](https://user-images.githubusercontent.com/70717332/97497675-efd02700-197b-11eb-9e0a-80ca15e7784a.png)



Заходим на сайт:
---
![Screenshot_34](https://user-images.githubusercontent.com/70717332/97497676-efd02700-197b-11eb-8d12-43b1be00b0c7.png)



Заливаем ключ:
---
![Screenshot_35](https://user-images.githubusercontent.com/70717332/97497677-f068bd80-197b-11eb-89ef-ee2f26e39456.png)



Успешно:
---
![Screenshot_36](https://user-images.githubusercontent.com/70717332/97497681-f1015400-197b-11eb-9cb8-0ee2f9d15c0d.png)



Находим его здесь же:
---
![Screenshot_37](https://user-images.githubusercontent.com/70717332/97497682-f1015400-197b-11eb-91fb-ecd84e4a11e1.png)



Успешно:
---
![Screenshot_38](https://user-images.githubusercontent.com/70717332/97497684-f199ea80-197b-11eb-8e9c-c6798232dce4.png)



Пишем, проверяем, отправляем:
---
![Screenshot_39](https://user-images.githubusercontent.com/70717332/97497685-f199ea80-197b-11eb-809a-b159e333d6c5.png)



![Screenshot_40](https://user-images.githubusercontent.com/70717332/97497686-f2328100-197b-11eb-982f-abbb9e89f431.png)



Что мне пришло на почту (windows\телефон):
---
![Screenshot_41](https://user-images.githubusercontent.com/70717332/97497690-f2328100-197b-11eb-88bc-f5aa154b208f.png)



Что будет, если открыть на линуксе:
---
![Screenshot_42](https://user-images.githubusercontent.com/70717332/97497691-f2cb1780-197b-11eb-916f-d0143f40f813.png)

Доработка: Письмо на эмэил mobil.mirea@gmail.com отправил

---
# Практическая №6
---
### TeamViewer

Установили, автозагрузочку поставили, регистрацию прошли, к работе все готово:



![Screenshot_1](https://user-images.githubusercontent.com/70717332/98712871-ee4d2880-2397-11eb-836a-9c77c9a6f1be.png)



Скачиваем на телефон, логинимся: 



![Ubtsma9zEYw](https://user-images.githubusercontent.com/70717332/98714805-6583bc00-239a-11eb-942b-c4be3acda4a7.jpg)



Подключаемся к компу по логину (Удаленное управление): 



![PAQ2od3bmiE](https://user-images.githubusercontent.com/70717332/98714995-9cf26880-239a-11eb-97b3-0a76e8d7b74e.jpg)



Вау ого: 



![3QQv5u88iwI](https://user-images.githubusercontent.com/70717332/98715120-c57a6280-239a-11eb-9ef4-53c67bf7d0bc.jpg)



Могу играть в игры прям на учебе:



![T6-ROrxeQf0](https://user-images.githubusercontent.com/70717332/98715167-d5924200-239a-11eb-9469-018a6f125857.jpg)



Теперь попробуем подключиться для передачи файлов, для этого создадим на компе папочку для теста: 



![Screenshot_2](https://user-images.githubusercontent.com/70717332/98715272-f65a9780-239a-11eb-9a52-973bc32f4c0a.png)



После того как подключились с телефона, находим эту папочку:



![LbfdMi6Lo1g](https://user-images.githubusercontent.com/70717332/98715401-24d87280-239b-11eb-9999-a29d11660c45.jpg)



![RJNEnosqpvw](https://user-images.githubusercontent.com/70717332/98715352-12f6cf80-239b-11eb-9931-103e6b376f04.jpg)



Перекидываем фотки (фотку): 



![rRLQAEqvizg](https://user-images.githubusercontent.com/70717332/98715492-4b96a900-239b-11eb-8095-a1ac9c0abb32.jpg)



![1t1RHfmQKqc](https://user-images.githubusercontent.com/70717332/98715636-7bde4780-239b-11eb-90d3-36be7607ef33.jpg)



Тем временем на пк висит данное оповещение: 



![Screenshot_3](https://user-images.githubusercontent.com/70717332/98715526-56e9d480-239b-11eb-9c6b-27dad0cbd2f9.png)



Успех:



![Screenshot_4](https://user-images.githubusercontent.com/70717332/98715669-8862a000-239b-11eb-9d10-cb71238c24c6.png)



оу еа ![Screenshot_5](https://user-images.githubusercontent.com/70717332/98715718-97495280-239b-11eb-955c-d63e5f773079.png)



### RDP



Что ж, я скачал RDP на телефон, поставил ползунок на пк чтобы все работало, добавляем пользователя по имени: 



![10](https://user-images.githubusercontent.com/70717332/98717870-b1d0fb00-239e-11eb-9daa-874993d883f4.jpg)



Логинимся при подключении: 



![11](https://user-images.githubusercontent.com/70717332/98717955-d036f680-239e-11eb-8494-6ac2aacc8eef.jpg)



Успешный успех:



![9](https://user-images.githubusercontent.com/70717332/98718005-e2b13000-239e-11eb-838c-4f9f7b6b5973.jpg)



Честно, даже не знал что в винде уже есть встроенный сервис для удаленного доступа, это стало для меня открытием.



### SSH Linux

Погружаемся в кали линух

Вроде запустил: 


![Screenshot_6](https://user-images.githubusercontent.com/70717332/98719153-72a3a980-23a0-11eb-9c7e-c0c15eec7b37.png)



Точно запустил:



![Screenshot_7](https://user-images.githubusercontent.com/70717332/98719346-af6fa080-23a0-11eb-8ba4-bc21502a9f22.png)



Копируем, защищаем от записи:



![Screenshot_8](https://user-images.githubusercontent.com/70717332/98719825-49374d80-23a1-11eb-98ba-7c0104fb74c9.png)


Меняем порт на 2222:



![Screenshot_9](https://user-images.githubusercontent.com/70717332/98722428-29545980-23a2-11eb-88e3-11356ce7824c.png)



Убираем рут права:



![Screenshot_10](https://user-images.githubusercontent.com/70717332/98722746-7c2e1100-23a2-11eb-919d-2e493596f65b.png)



Баннер и приветствие я оставил дефолтные.

Пробуем подключить локального юзера:



![Screenshot_11](https://user-images.githubusercontent.com/70717332/98723898-05921300-23a4-11eb-8df0-06e9e5462e44.png)



Порт 2222 почему-то не нашелся, подключился к 22, надеюсь не страшно.

Ищем свой inet:



![Screenshot_12](https://user-images.githubusercontent.com/70717332/98723997-26f2ff00-23a4-11eb-94f4-edbc2053a5a1.png)



Подключаемся уже сами:



![Screenshot_13](https://user-images.githubusercontent.com/70717332/98724212-746f6c00-23a4-11eb-82c7-90d7c3c5d2ba.png)



### SSH Windows

Скачиваем и запускаем PuTTY, вводим адрес и порт:



![Screenshot_14](https://user-images.githubusercontent.com/70717332/98724964-8bfb2480-23a5-11eb-8c62-117839bf4ce4.png)



Как я понимаю, успешно подключился:



![Screenshot_15](https://user-images.githubusercontent.com/70717332/98725262-f613c980-23a5-11eb-8f3c-058f739f33c1.png)



С помощью Bitvise все ок:



![Screenshot_18](https://user-images.githubusercontent.com/70717332/98726798-06c53f00-23a8-11eb-801c-06b387e21a31.png)



### Генерация ключа на Linux

Генерируем ключ:



![Screenshot_19](https://user-images.githubusercontent.com/70717332/98727052-63285e80-23a8-11eb-82af-eec035ca7d4c.png)



### Генерация на Windows

Генерируем в PuTTY:



![Screenshot_20](https://user-images.githubusercontent.com/70717332/98727645-4c363c00-23a9-11eb-8a01-519f3d142589.png)



Ключи сохранил:



![Screenshot_21](https://user-images.githubusercontent.com/70717332/98728035-f1511480-23a9-11eb-8c6f-1bc27c263c99.png)



### Копия публичного ключа на сервер Linux

Копируем собственно говоря:



![Screenshot_22](https://user-images.githubusercontent.com/70717332/98730713-bf41b180-23ad-11eb-8448-17cab4eaf719.png)



### Аутентификация с помощью ключа на Linux

Собственно говоря, входим используя ключ:



![Screenshot_23](https://user-images.githubusercontent.com/70717332/98731161-5d357c00-23ae-11eb-89c8-8ca95b56870f.png)



### Аутентификация с помощью ключа на Windows

К серверу подключился, ключ уже стоял:



![Screenshot_24](https://user-images.githubusercontent.com/70717332/98731633-109e7080-23af-11eb-9d20-b9e8095efffd.png)



Путь к ключу указал:



![Screenshot_25](https://user-images.githubusercontent.com/70717332/98732178-db465280-23af-11eb-9a05-7d3641f00557.png)



:( Но почему-то в доступе было отказано:



![Screenshot_26](https://user-images.githubusercontent.com/70717332/98732181-dc777f80-23af-11eb-84aa-b6a84948c2a3.png)



### UPD:

Сначала не увидел задание по поводу порта, баннера и текста приветствия, все поменял:



![Screenshot_31](https://user-images.githubusercontent.com/70717332/98738633-126d3180-23b9-11eb-8ebd-8a10459dff15.png)



в принципе, все действия, которые я проводил, не поменялись, только вместо порта 22 мне приходилось бы использовать 20012

### Получаем VPS (VDS) сервер от Google

Развернул сервер:



![Screenshot_27](https://user-images.githubusercontent.com/70717332/98734807-8dcbe480-23b3-11eb-9500-e34a2f5d5087.png)



Ключ поменял:



![Screenshot_33](https://user-images.githubusercontent.com/70717332/98742165-fd939c80-23be-11eb-9dc5-0640ec4c9571.png)



Настройку провел:



![Screenshot_32](https://user-images.githubusercontent.com/70717332/98739453-6e848580-23ba-11eb-937e-3ffc6c7f4ca6.png)

# Практическая №7

### Мобильная сеть

Скачиваем программу чтобы ловить вышки и запускаем

Ловим вышку:



![oEAEYTK9M-c](https://user-images.githubusercontent.com/70717332/100363293-93f5ce00-300d-11eb-96ac-dbc1e3ff966d.jpg)



Находим ее на сайте:



![Screenshot_1](https://user-images.githubusercontent.com/70717332/100363633-141c3380-300e-11eb-84da-75262e6edc6e.png)



Успех

### Linux

Сканируем сеть:



![Screenshot_2](https://user-images.githubusercontent.com/70717332/100367508-5eec7a00-3013-11eb-8700-7798b9f191a2.png)



Чекаем мак адресы:



![Screenshot_3](https://user-images.githubusercontent.com/70717332/100368475-afb0a280-3014-11eb-9b03-a7308128bc0a.png)



Меняем:



![Screenshot_4](https://user-images.githubusercontent.com/70717332/100368663-ec7c9980-3014-11eb-915a-aeed588e241d.png)



Идем далее

Смотрим свой айпи на 2ip.ru:



![Screenshot_5](https://user-images.githubusercontent.com/70717332/100369389-e0dda280-3015-11eb-8fa3-6449a383396e.png)



Смотрим на линухе:



![Screenshot_7](https://user-images.githubusercontent.com/70717332/100371960-a37b1400-3019-11eb-94ca-ab23a89e4ac3.png)



Находим, ставим прокси:



![Screenshot_8](https://user-images.githubusercontent.com/70717332/100374478-6ca6fd00-301d-11eb-9746-8588d1f4be77.png)



Успешно сменилось:



![Screenshot_9](https://user-images.githubusercontent.com/70717332/100374468-67e24900-301d-11eb-9f27-f4559c1420d2.png)



Ставим на линух:



![Screenshot_10](https://user-images.githubusercontent.com/70717332/100375465-e2f82f00-301e-11eb-8169-364b0bf37510.png)



Проверяем:



![Screenshot_11](https://user-images.githubusercontent.com/70717332/100375502-f0adb480-301e-11eb-9540-5ede1b7485f9.png)



Не получилось, скорее всего из-за самого прокси, нужно просто поискать другой и методом подбора находить, но это очень долго

Идем дальше

### TOR

Скачиваем

Добавляем ссылки репозитория:



![Screenshot_12](https://user-images.githubusercontent.com/70717332/100376596-e2609800-3020-11eb-8004-a76b45764300.png)



Проводим манипуляции с ключем за кадром Ы

Проверили подключение, статус, все работает:


![Screenshot_13](https://user-images.githubusercontent.com/70717332/100380994-0b852680-3029-11eb-81cb-d2d71145288a.png)



Ставим Веб-сервер:



![Screenshot_14](https://user-images.githubusercontent.com/70717332/100380996-0c1dbd00-3029-11eb-875c-f08a10b7d75c.png)



Успешно:



![Screenshot_15](https://user-images.githubusercontent.com/70717332/100380999-0cb65380-3029-11eb-98b8-98c0be956104.png)




Рекомментируем и модифицируем следующие строчки:



![Screenshot_16](https://user-images.githubusercontent.com/70717332/100381466-168c8680-302a-11eb-8f28-0e5e193fce2d.png)



Проверяем работоспособность:



![Screenshot_17](https://user-images.githubusercontent.com/70717332/100381470-17251d00-302a-11eb-9db7-5edcb3518d20.png)



Вроде работает

Генерация ссылки .onion:



![Screenshot_18](https://user-images.githubusercontent.com/70717332/100381471-17251d00-302a-11eb-9938-c1b47f93e62e.png)




Берем ее из hostname, пробуем:



![Screenshot_19](https://user-images.githubusercontent.com/70717332/100383503-ca901080-302e-11eb-801d-ddfc0e44c898.png)



Антиуспех :(



Пробуем стартануть все это дело с помощью SSH сервера

Ставим свой порт

Пробуем:



![Screenshot_22](https://user-images.githubusercontent.com/70717332/100386451-67a27780-3036-11eb-84c5-81e21aa4413c.png)



Антиуспех (2) :(

Честно не знаю почему, пробовал и так и сяк, не получается :(

### I2P

Устанавливаем, запускаем:



![Screenshot_23](https://user-images.githubusercontent.com/70717332/100386820-88b79800-3037-11eb-9aab-c0981e57905c.png)



Проводим настройку:



![Screenshot_24](https://user-images.githubusercontent.com/70717332/100386822-89502e80-3037-11eb-851f-f24724eceef0.png)



Настраиваем браузер:



![Screenshot_25](https://user-images.githubusercontent.com/70717332/100386939-d207e780-3037-11eb-9f32-bca6eaa20e0c.png)



Регестрируемся, настриваем все как надо:



![Screenshot_26](https://user-images.githubusercontent.com/70717332/100388020-8571db80-303a-11eb-87cf-f750580dbb89.png)



Отправляем письмо:



![Screenshot_27](https://user-images.githubusercontent.com/70717332/100388021-860a7200-303a-11eb-95dd-56bac3ded56f.png)



Успешно:



![Screenshot_28](https://user-images.githubusercontent.com/70717332/100388173-e9949f80-303a-11eb-9f60-739b703550be.png)



Теперь пробуем поставить сайт

Скачиваем шаблон, меняем под себя:



![Screenshot_29](https://user-images.githubusercontent.com/70717332/100388961-1fd31e80-303d-11eb-9f05-bfa5bfbf9697.png)



Пробуем запустить, поставил порт 20012:



![Screenshot_30](https://user-images.githubusercontent.com/70717332/100389922-db954d80-303f-11eb-961a-df9655e291eb.png)



Теперь настройка сервера:



![Screenshot_31](https://user-images.githubusercontent.com/70717332/100389925-dcc67a80-303f-11eb-82de-031e6f1bee1e.png)



Настроили, запускаем:



![Screenshot_32](https://user-images.githubusercontent.com/70717332/100394358-f2db3780-304d-11eb-8c95-944730fc6b80.png)



Так как у меня яблоко, просим одногруппника помочь с проверкой

Он, конечно же, успешно соглашается:



![wsohNn33ngk](https://user-images.githubusercontent.com/70717332/100394425-2ae27a80-304e-11eb-8ee2-c8c19ee5b4dc.jpg)



Успех?

### Доработка

Переделал:



![123131313123123123](https://user-images.githubusercontent.com/70717332/100523648-0d82ed00-31c3-11eb-8b2b-aa2fe50b573c.jpg)
























