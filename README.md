# OIB-PRACTICA
### [Перемотка к практической №3 (КЛИКАБЕЛЬНО)](https://github.com/Kozachok-Nikolay/OIB-PRACTICA/blob/master/README.md#практическая-3)
### [Перемотка к практической №4 (КЛИКАБЕЛЬНО)](https://github.com/Kozachok-Nikolay/OIB-PRACTICA/blob/master/README.md#практиеческая-4)
### [Перемотка к практической №5 (КЛИКАБЕЛЬНО)](https://github.com/Kozachok-Nikolay/OIB-PRACTICA/blob/master/README.md#практическая-5) 
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








