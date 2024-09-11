# Samokat_Yandex

Яндекс Самокат — позволяет пользователям заранее зазазать на домой самокаты на определенное время и место. 
Пользователи получают гарантированную доступность, уведомления, и могут гибко управлять заказами через веб-приложение.

![image](https://github.com/user-attachments/assets/3ae0424c-341e-4561-be96-473860b46472)



<details>
  <summary>Задание 1</summary> 

# Веб-приложение Яндекс.Самокат

Обрати внимание на техническую информацию при запуске приложения — в ней описаны
все доступы к серверу, БД и адреса API.
Составь чек-лист по требованиям к экрану «Статус заказа».
Для экрана «Сделать заказ» составь проверки на валидацию полей. Заполни их в виде таблицы по шаблону.
Проведи тестирование всей функциональности не только по получившимся чек-листам/таблицам, но и по 
остальным макетам и требованиям. Проверять главную страницу (лендинг) не нужно.
</details>

<details>
  <summary>Требования</summary> 

# Требования к веб приложению

## Поддерживаемые окружения 

 Приложение поддерживает эти браузеры: Яндекс.Браузер не ниже версии 
20.0.1, Chrome не ниже версии 85. Будет поддерживаться разрешение экрана 
1280x720 и 1920x1080.

## Лендинг

 Есть заголовок и чертёж самоката. При скролле происходит анимация: 
чертёж сменяется фотографией, появляется таблица с описанием самоката.

В шапке лендинга есть две кнопки: «Заказать», «Статус заказа».
 
Появляется запрос на согласие использовать куки. 

Если доскроллить до третьего блока, появляется информация: «Как это 
работает», «Вопросы о важном».

## Экран «Сделать заказ»
Чтобы сделать заказ, нужно заполнить две формы: «Для кого самокат», «Про 
аренду».

### Для кого самокат
Поля: «Имя», «Фамилия», «Адрес: куда привезти самокат», «Станция метро», 
«Телефон: на него позвонит курьер».

Все поля обязательные. Если они не заполнены корректно, нельзя перейти на 
следующую страницу.

Внизу кнопка «Дальше»: она переводит на форму «Про аренду». 

### Про аренду

Поля: «Когда привезти самокат», «Срок аренды», «Цвет», «Комментарий». 
«Когда привезти самокат», «Срок аренды» — обязательные поля.
«Цвет», «Комментарий» — необязательные.

### Кнопка «Назад». 
 При нажатии пользователь переходит на страницу «Для 
кого самокат».  При переключении между страницами введённая 
информация сохраняется.

### Кнопка «Заказать».
 Если все поля заполнены корректно, при клике по 
кнопке «Заказать» заказ будет оформлен. Появится всплывающее окно с 
текстом «Номер заказа NNNNN. Запишите его: пригодится, чтобы 
отслеживать статус» и кнопкой «Посмотреть статус». Кнопка «Посмотреть 
статус» ведёт на экран «Статус заказа»: в нём уже заполнено поле «Номер 
заказа».

 Если не все обязательные поля заполнены корректно, при нажатии на кнопку 
«Заказать» появится ошибка «Введите корректный <имя поля>». 
Пользователь может сделать несколько заказов один за другим.

## Экран «Статус заказа»

 Если нажать на «Статус заказа» в шапке лендинга, появляется поле ввода 
«Номер заказа». Нужно ввести значение и нажать Enter. Если номер заказа 
введён корректно, появляется информация:

- Данные заказа пользователя: имя, фамилия, адрес и остальные. Для всех 
полей действует правило: если текст не умещается в одной строке, он 
переносится на вторую.

- Цепочка статусов заказа. Текущий статус выделен чёрным, остальные — 
серые. Если статус пройден, цифра перед ним сменяется на галочку.

Если номер заказа введён некорректно, появляется сообщение об ошибке: 
«Такого заказа нет. Точно верный номер?».

 На экране статуса заказа четыре статуса. Активным может быть только один 
из них — он показывает, на какой стадии находится заказ:

### «Самокат на складе».
Становится активным, когда пользователь сделал 
заказ.

### «Курьер едет к вам».
Становится активным, когда курьер подтвердил у 
себя в приложении, что принял заказ. Когда статус активен, в подписи 
появляется имя курьера: «Курьер Фродо едет к вам». Если имя курьера 
слишком длинное и подпись не умещается в одну строчку, текст 
переносится на вторую строчку.

### «Курьер на месте».
Становится активным, когда курьер нажал кнопку «Завершить» у себя в приложении.

### «Ну всё, теперь кататься».
Становится активным, когда курьер подтвердил завершение заказа. 
Под заголовком статуса подпись «Аренда закончится...».
Показываемое время рассчитывается от момента, когда самокат передали
пользователю с учётом количества дней. Когда время аренды заканчивается, 
статус меняется на «Время аренды кончилось» с подписью «Скоро курьер заберёт самокат».

 Пользователь может ввести номер другого заказа и посмотреть его статус.
 
### Отмена заказа
 Есть кнопка «Отменить заказ». Если кликнуть по ней, появится всплывающее 
окно с текстом «Хотите отменить заказ?» На всплывающем окне две кнопки: 
«Отменить», «Назад». 

Если кликнуть по «Назад», пользователь вернётся на страницу статуса 
заказа.

Если кликнуть по «Отменить», появится всплывающее окно с текстом «Заказ 
отменён. Возвращайтесь, мы всегда вас ждём :)» и кнопкой «Хорошо». 
Кнопка «Хорошо» ведёт на главную страницу лендинга.

 Пользователь может отменить заказ, пока курьер не взял его в работу. Когда 
заказ уже у курьера, кнопка «Отменить заказ» будет некликабельной.
 Отменённый заказ удаляется из системы. Пользователь не может его 
посмотреть.

### Просроченный заказ

 Заказ считается просроченным, если курьер не успел выполнить его 
вовремя. Например, пользователь заказал самокат на 1 января. Если 1 января 
самокат не доставлен до 2359, этот заказ — просроченный.

 Если заказ просрочен, его статус меняется на «Курьер задерживается», а 
подпись — на «Не успеем привезти самокат вовремя. Чтобы уточнить статус
заказа, позвоните в поддержку: 0101». Статус и подпись подсвечиваются 
красным.

 Если пользователю доставили просроченный заказ, отсчёт времени до конца 
аренды начинается с момента получения заказа.

## Доработка фронтенда
 В цепочку статусов добавлен пятый статус: «Время аренды кончилось». Это 
фича, которую реализовали только во фронтенде, и бэкенд ещё не готов. 
Раньше этот текст появлялся на месте четвёртого статуса — в момент, когда 
время аренды заканчивалось. Теперь текст в четвёртом статусе не меняется: 
он просто становится серым, как и остальные статусы.


 Пример ответа описан в документации к API в блоке Orders — Получить заказ 
по его номеру.

 Номер нового статуса в запросе  3.

 
## Ограничения полей
![image](https://github.com/user-attachments/assets/976c0736-d552-4dd1-b6c0-c4075bfc279a)

![image](https://github.com/user-attachments/assets/0b5f37bc-2773-40ba-b379-4f8786faa8fb)

![image](https://github.com/user-attachments/assets/3e23acc7-260f-4463-bbdf-8013e6cb5e9f)



 ## FAQ
 
 **Сколько это стоит? И как оплатить?**
 
 Сутки  400 рублей. Оплата курьеру — наличными или картой.
 
 **Вы привозите зарядку вместе с самокатом?**
 
 Самокат приезжает к вам с полной зарядкой. Этого хватит на восемь суток — 
даже если будете кататься без передышек и во сне. Зарядка не понадобится.

 **Сможете привезти самокат прямо сегодня?**
 
 Только начиная с завтрашнего дня. Но скоро станем расторопнее.
 
 **Хочу сразу несколько самокатов! Так можно?**
 
 Пока что так: один заказ — один самокат. Если хотите покататься с друзьями,
можете просто сделать несколько заказов.

 **Можно ли продлить заказ или вернуть самокат раньше?**
 
 Пока что нет! Если что-то срочное — всегда можно позвонить в поддержку 
по номеру 0101.

 **Можно ли отменить заказ?**

 Да, отменить можно, пока курьер не выдвинулся к вам с самокатом. Штрафа 
не будет, объяснительной записки не попросим.

 **Как рассчитывается время аренды?**
 Допустим, вы оформляете заказ на 8 мая. Мы привозим самокат в эту дату до 
конца дня. Отсчёт времени аренды начинается с момента, когда вы оплатите 
заказ курьеру. Если мы привезли самокат 8 мая в 2030, суточная аренда 
закончится 9 мая в 20:30.

 **Я живу за МКАДом, привезёте?**
 
 Да, обязательно. Всем самокатов! И Москве, и Московской области.

</details>

<details>
  <summary>Макеты(Figma)</summary> 

  [макеты](https://www.figma.com/design/vHgTVzFac8zyxhMZ2o4b2m/web)

![image](https://github.com/user-attachments/assets/4fc61ec0-61c3-4ece-9d78-5d79d2fe1785)

</details>


<details>>
  <summary>Чек-лист</summary> 
https://docs.google.com/spreadsheets/d/1P0-mUWO0AT1GBVZkK4_u9wQC-xYcEtGymEvTNFhk8cY/edit?gid=943703744
[UploЧек-лист по требованиям к экрану «Статус заказа»					
					
№	|Описание проверки|	|Windows Chrome 126.0 1280x720|	|Windows Yandex 24.6 1920x1080|	
				
|t-1	В левом верхнем углу  расположен логотип "Яндекс Самокат" и надпись"Учебный тренажер"	PASSED	PASSED|		
|t-2	Логотип "Яндекс Самокат" расположен слева от надписи "Учебный тренажер"	PASSED	PASSED|		
|t-3	Слово Яндекс в логотипе цвет черный, шрифт жирный 	PASSED	PASSED|		
t-4	Слово Самокат в логотипе цвет черный, шрифт обычный 	PASSED	PASSED		
t-5	Надпись "Учебный тренажер" справа от логотипа выравнивание по верху логотипа "Яндекс Самокат"	PASSED	PASSED		
t-6	Надпись "Учебный тренажер" цвет серый шрифт обычный 	PASSED	PASSED		
t-7	В правом верхнем углу надпись "Статус заказа" цвет черный шрифт обычный 	PASSED	PASSED		
t-8	При нажатие на "Статус заказа" появляется поле ввода «Номер заказа»	PASSED	PASSED		
t-9	Поле «Номер заказа» появляется в правом верхнем углу окна "Статус заказа" выравнивание по правому краю	FAILED	FAILED	bug-87	
t-10	Поле «Номер заказа» имеет фон белый, контурная линия черного цвета, углы скруглены	PASSED	PASSED		
t-11	Поле имеет плейсхолдер "Номер заказа" серого цвета выравнивание по левому краю	FAILED	FAILED	bug-87	
t-12	Слева от надписи "Статус заказа" кнопка "Заказать"	PASSED	PASSED		
t-13	При появление поле ввода "Номер заказа" кнопка "Заказать скрывается	PASSED	PASSED		
t-14	Кнопка  "Заказать" цвет черный углы скруглены 	PASSED	PASSED		
t-15	На кнопке "Заказать" надпись Заказать цвет белый выравнивание по центру 	PASSED	PASSED		
t-16	При наведении курсора  на кнопку "Заказать" фон кнопки светлеет 	PASSED	PASSED		
t-17	При нажатие на кнопку заказать открывается окно "Для кого самокат"	PASSED	PASSED		
	Поле ввода "Номер заказа"  				
t-18	Под шапкой окна расположено поле ввода и кнопка "Посмотреть"	PASSED	PASSED		
t-19	Слева расположено поле ввода "Номер заказа"	PASSED	PASSED		
t-20	У поля ввода номера заказа границы черного цвета	FAILED	PASSED	bug-98	
t-21	При заполнение поля границы "Номер заказа" подсвечиваются синим	FAILED	FAILED	bug-88	
t-22	При вводе значений цвет введенных данных  черного цвета	PASSED	PASSED		
t-23	Ввод значение в поле "Номер заказа" начинается с левого края 	PASSED	PASSED		
	Кнопка "Посмотреть"				
t-24	С право от поле ввода "Номер заказа" разположена кнопка "Посмотреть"	PASSED	PASSED		
t-25	Кнопка "Посмотреть" цвет черный углы скруглены 	PASSED	PASSED		
t-26	Надпись на кнопке Просмотреть белого цвета выравнивание по центру	PASSED	PASSED		
t-27	При наведении курсора на кнопку фон кнопки становится светлее	PASSED	PASSED		
t-28	При вводе существующего номер заказа и при клике кнопки "Посмотреть" раскрывает данные заказа	PASSED	PASSED		
t-29	При вводе существующего номер заказа и при нажатии на Enter раскрывает данные заказа	FAILED	FAILED	bug-89	
t-30	При ввод несуществующего номера заказа и при клике кнопки "Посмотреть" открывается окно «Такого заказа нет. Точно верный номер?»	PASSED	PASSED		
t-31	При ввод несуществующего ноомера заказа и при нажатии на Enter открывается окно «Такого заказа нет. Точно верный номер?»	FAILED	FAILED	bug-89	
t-32	При пустом поле ввода  при клике кнопки "Посмотреть" открывается окно «Такого заказа нет. Точно верный номер?»	PASSED	PASSED		
t-33	При пустом поле ввода нажатие на Enter открывается окно «Такого заказа нет. Точно верный номер?»	FAILED	FAILED	bug-89	
	Окно «Такого заказа нет. Точно верный номер?»				
t-34	Окно «Такого заказа нет. Точно верный номер?» имеет  белый фон, черную контурную линию, углы скруглены	PASSED	PASSED		
t-35	Заголовок «Такого заказа нет.» расположен в верхней части окна выравнивание по центру 	PASSED	PASSED		
t-36	Цвет заголовка «Такого заказа нет.» черный шрифт обычный 	PASSED	PASSED		
t-37	Комментарии «Точно верный номер?» расположение под заголовкам «Такого заказа нет.» выравнивание по центру	PASSED	PASSED		
t-38	Цвет комментарии чёрный, шрифт меньше чем у заголовка	PASSED	PASSED		
t-39	Под заголовкам и комментариями в окне есть картинка 	FAILED	FAILED	bug-90	
t-40	Окно "Такого заказа нет" закроется если ввести существующий номер заказа	PASSED	PASSED		
	Блок с данными заказа и пользователя				
t-41	Блок с данными пользователя и заказа расположен по левому краю окна под полем "Номер заказа"	PASSED	PASSED		
t-42	В блоке есть три раздела 1.данные пользователя, 2. Когда привезем, срок аренды 3. цвет, комментарии 	PASSED	PASSED		
t-43	Каждый раздел состоит из строк	PASSED	PASSED		
t-44	В блоке между разделами есть две разделительные линии на всю ширину блока цвет серый	PASSED	PASSED		
t-45	Блок с данными не кликабелен и нельзя редактировать 	PASSED	PASSED		
	Первый раздел Данные пользователя				
t-46	Первый раздел блока информация о пользователе "Имя", "Фамилия", "Адрес", "Станция метро", "телефон"	PASSED	PASSED		
t-47	Каждая значение на отдельной строке всего пять строк	PASSED	PASSED		
t-48	Название строк выравнивание по левому краю, цвет серый, шрифт обычный	PASSED	PASSED		
t-49	Введенные данные пользователя выравнивание по правому краю блока, цвет черный, шрифт обычный	PASSED	PASSED		
t-50	Первоя строка "Имя" входные данные соответствуют данным которые ввел пользователь	PASSED	PASSED		
t-51	я	PASSED	PASSED		
t-52	Вторая строка "Фамилия" входные данные соответствуют данным которые ввел пользователь	PASSED	PASSED		
t-53	Если входные данные в строке "Фамилия" ползователя не помещаются в одной строке, то она переносится на вторую строку	FAILED	FAILED	bug-91	
t-54	Третая строка "Адрес" входные данные соответствуют данным которые ввел пользователь	PASSED	PASSED		
t-55	Если входные данные в строке "Адрес" ползователя не помещаются в одной строке, то он переносится на вторую строку	PASSED	PASSED		
t-56	Четвертая строка "Станция метро2 входные данные соответствуют данным которые ввел пользователь	FAILED	FAILED	bug-92	
t-57	Пятая строка "Телефон" входные данные соответствуют данным которые ввел пользователь	PASSED	PASSED		
t-58	Перед названием выбранной пользователям станций метро есть цветной маркер в соответствии со станцией	PASSED	PASSED		
	Второй раздел дата доставки и срок аренды				
t-59	Второй раздел блока состоит из двух строк 	PASSED	PASSED		
t-60	Первая строка название "Когда привезем" выравнивание по левому краю цвет серый шрифт обычный 	FAILED	FAILED	bug-93	
t-61	По правому краю строки, указана дата доставки, которую указал пользователь 	FAILED	FAILED	bug-94	
t-62	День доставки указано цифрами, месяц буквами цвет черный шрифт обычный	PASSED	PASSED		
t-63	Вторая строка название "Срок аренды" выравнивание по левому краю цвет серый шрифт обычный	PASSED	PASSED		
t-64	По правому краю строки, указан срок который выбрал пользователь цвет черный шрифт обычный	PASSED	PASSED		
t-65	Срок аренды написано буквами 	PASSED	PASSED		
	Третий раздел цвет самоката и комментарии пользователя 				
t-65	Третий раздел блока состоит из двух строк 1. Цвет, 2.Комментарий	PASSED	PASSED		
t-66	Первая строка название "Цвет" выравнивание по левому краю цвет серый шрифт обычный 	PASSED	PASSED		
t-67	По правому краю строки указан один из цветов, если выбран один цвет черный жемчуг/серая безысходность цвет шрифта черный	PASSED	PASSED		
t-68	Если пользователь указал два цвета то в значение цвет указан значение "Любой"	FAILED	FAILED	bug-95	
t-69	Если пользователь не указал цвета то в значение цвет указан "Любой"	PASSED	PASSED		
t-70	Вторая строка раздела название "Комментарий" выравнивание по левому краю цвет серый шрифт обычный	PASSED	PASSED		
t-71	Если пользователь оставил комментарий они по правому краю строки цвет черный шрифт обычный	PASSED	PASSED		
t-72	Если введенный текст ползователя в строке "Комментарии" не помещаются в одной строке, то он переносится на вторую строку	FAILED	FAILED	bug-91	
t-73	Если пользователь не оставил комментариев строка "Комментарий" отсутствует	PASSED	PASSED		
	Кнопка "Отменить заказ"				
t-74	Под блокам с данными расположена кнопка "Отменить заказ" выравнивание по левому краю блока 	PASSED	PASSED		
t-75	Кнопка имеет черную контурную линию, углы скруглены, цвет кнопки белый	PASSED	PASSED		
t-76	Надпись на кнопке "Отменит заказ" черного цвета выравнивание по центру кнопки	PASSED	PASSED		
t-77	При наведении курсора кнопка меняет цвет 	PASSED	PASSED		
t-78	При нажатие на кнопку появится всплывающее окно с текстом «Хотите отменить заказ?» 	PASSED	PASSED		
t-79	Кнопка "Отменить" становится неактивной, если статус "Самокат на складе" изменился на "Курьер едет к вам"	PASSED	PASSED		
	Окно «Хотите отменить заказ?» 				
t-80	Окно «Хотите отменить заказ?» имеет белый фон черную контурную линию с круглыми углами	PASSED	PASSED		
t-81	Окно имеет заголовок  «Хотите отменить заказ?» и две кнопки "Назад" и "Отменить"	PASSED	PASSED		
t-82	Загаловак  «Хотите отменить заказ?» расположен в верхней части окна выравнивание по центру	PASSED	PASSED		
t-83	Цвет заголовка черный шрифт обычный	PASSED	PASSED		
t-84	Кнопки "Назад" и "Отменить" расположены под заголовком "Хотите отменить заказ?"	PASSED	PASSED		
t-85	Кнопка "Назад" расположена в левой стороне имеет черный фон скругленные углы	PASSED	PASSED		
t-86	Надпись на кнопке назад белого цвета выравнивание по центру кнопки	PASSED	PASSED		
t-87	При наведении курсора на кнопку "Назад" фон меняется	PASSED	PASSED		
t-88	Нажатие на кнопку назад возвращает на страницу "Статус заказа"	PASSED	PASSED		
t-89	Кнопка "Отменить" расположена в правой стороне имеет белый фон черную контурную линию углы скруглены	PASSED	PASSED		
t-90	Надпись на кнопке отменит черного цвета выранивание по центру кнопки	PASSED	PASSED		
t-91	При наведении курсора на кнопку "Отменить" фон меняется	PASSED	PASSED		
t-92	При нажатие на кнопку "Изменить" открывается окно "Заказ отменен"	PASSED	PASSED		
	Окно "Заказ отменен"				
t-93	Окно заказ отменен имеет белый фон черную контурную линию углы скруглены 	FAILED	PASSED	bug-99	
t-94	В верхней части окна заголовок "Заказ отменен" выравнивание по центру окно цвет черный шрифт обычный	PASSED	PASSED		
t-95	Под заголовкам "Заказ отменен"  комментарии  "Возвращайтесь мы всегда вас ждем :)" 	PASSED	PASSED		
t-96	Цвет коментарии черный выравнивание по центру окна	PASSED	PASSED		
t-97	Под комментариями с правой стороны в нижней части окна, кнопка "Хорошо"	FAILED	FAILED	bug-96	
t-98	Кнопка "Хорошо" имеет черный фон круглые углы 	PASSED	PASSED		
t-99	Надпись на кнопке "Хорошо" белого цвета выравнивание по центру кнопки	PASSED	PASSED		
t-100	Нажатие на кнопку «Хорошо» ведёт на главную страницу лендинга.	PASSED	PASSED		
t-101	Отменённый заказ удаляется из системы (БД)	FAILED	FAILED	bug-155	
t-102	Отменённый заказ Пользователь не может  посмотреть отменённый заказ	FAILED	FAILED	bug-97	
	Цепочка статусов заказа				
t-103	На правой стороне от данных пользователя и кнопки "Отменить" расположена цепочка со статусами заказа	PASSED	FAILED	bug-100	
t-104	Заголовки статусов и описание выровнены по левому краю	PASSED	FAILED	bug-100	
t-105	По левой стороне статусов расположена вертикальная цепочка с числами от 1 до 4	PASSED	PASSED		
t-106	Статус состоит из заголовка и описания, заголовок шрифт крупный, у описание мелкий 	PASSED	PASSED		
t-107	В начальном состоянии статус серого цвета	PASSED	PASSED		
t-108	В активном состоянии статус черного цвета 	PASSED	PASSED		
t-109	После того как этап пройден статус снова становится серым 	PASSED	PASSED		
t-110	Активным может быть только один статус заказа	PASSED	PASSED		
t-111	Цифра в цепочке меняется на галочку, если статус пройден	FAILED	FAILED	bug-101	bug-153
	Первый статус				
t-112	Первый статус "Самокат на складе" и описание  "Скоро курьер заберет его"	PASSED	PASSED		
t-113	Статус становится активным, когда пользователь сделал заказ	PASSED	PASSED		
	Второй статус 				
t-114	Второй статус "Курьер едет к вам" описание  "Номер для связи: 0101"	PASSED	PASSED		
t-115	Статус становится активным, когда курьер подтвердил у себя в приложении, что принял заказ	PASSED	PASSED		
t-116	Когда статус активен, в подписи появляется имя курьера «Курьер "Имя" едет к вам»	PASSED	PASSED		
t-117	Если имя курьера слишком длинное и подпись не умещается в одну строку, текст переносится на вторую строчку	FAILED	FAILED	bug-104	
t-118	Если курьер не успел выполнить доставку вовремя статус  "Курьер едет к вам" меняется на «Курьер задерживается»	FAILED	FAILED	bug-105	
t-119	Описание "Номер для связи 0101" меняется на «Не успеем привезти самокат вовремя. Чтобы уточнить статус заказа, позвоните в поддержку: 0101»	SKIPPED	SKIPPED	bug-105	
t-120	Статус «Курьер задерживается» подпись и цепочка статуса подсвечиваются красным 	SKIPPED	SKIPPED	bug-105	
	Третий статус				
t-121	Третий статус "Курьер на месте" описание "Заберите самокат и оплатите аренду"	PASSED	PASSED		
t-122	Статус становится активным, когда курьер нажал кнопку «Завершить» у себя в приложении	FAILED	FAILED	bug-106	
	Четвертый статус				
t-123	Четвертый статус "Ну всё, теперь кататься" описание "Пока не закончится аренда"	PASSED	PASSED		
t-124	Статус становится активным, когда курьер подтвердил завершение заказа	SKIPPED	SKIPPED		
t-125	После подтверждения курьера о доставке самоката описание под заголовком "Пока не закончится аренда" меняется на «Аренда закончится » и дата (Дата доставки + срок аренды)	PASSED	PASSED		
t-126	Если пользователю доставили просроченный заказ, отсчёт времени до конца аренды начинается с момента получения заказа	PASSED	PASSED		
t-127	В описание  «Аренда закончится » дата пишется в формате ( 9 июня в 20:30)	FAILED	FAILED	bug-102	
t-128	Дата оканчание аренды пишется правилно с учетом  (Дата доставки + срок аренды)	PASSED	PASSED		
	Пятый статус (доработки фронтенда)				
t-129	 Вертикальная цепочка статусов с числами от 1 до 5	PASSED	PASSED		
t-130	Пятый статус "Время аренды кончилось" описание "Скоро курьер заберет самокат"	FAILED	FAILED	bug-103	
t-131	Статус «Время аренды кончилось» становится активным, когда время аренды заканчилось	PASSED	PASSED		ading Арабаджян Карлен — диплом_Инженер по тестированию  - Задание 1_ чек-лист.tsv…]()



</details>
<details>
  <summary>Задание 2</summary> 
  
# Мобильное приложение Яндекс.Самокат

Обрати внимание на техническую информацию при запуске приложения.
Спроектируй тест-кейсы и протестируй функциональность. Не забудь написать кейсы и на вёрстку по макетам к этой функциональности.
 </details>
<details>
  <summary>Требования</summary> 
  
# Требования к мобильному приложению

 ## Экран «Вход»
 
1. При первом входе в приложение появляется экран авторизации с 
логином и паролем.

3. Если курьер уже авторизовался, он видит экран списка заказов по 
умолчанию.

3.На экране два поля ввода: под логин и пароль. Есть кнопка «Войти».

5. Если тапнуть по «Не помню пароль», появится уведомление с текстом 
«Свяжитесь с менеджером: 0101» и кнопка «Ок».

7. Пользователь может выйти из приложения с любого экрана. Тогда при 
входе он снова попадёт на экран авторизации.

## Экран «Список заказов»
 На экране две вкладки: «Все», «Мои». 
 
На вкладке «Все» курьеры видят один и тот же список заказов: это заказы 
без исполнителей. 

Как только один из курьеров принимает заказ, он перемещается во вкладку 
«Мои». Остальные курьеры перестают его видеть.

 Внутри вкладки «Мои» курьер видит заказы, которые он принял. 
 
Чтобы список обновился, нужно потянуть за экран вниз (англ. pull-to-refresh).
 При pull-to-refresh:
 
1. Для вкладки «Все»: заказы, которые принял другой курьер, пропадают из 
списка. 

2. Для вкладки «Все»: заказы, которые отменил пользователь, удаляются.
   
3. Для вкладок «Все» и «Мои»: карточки сортируются по дате доставки, 
которую указал пользователь. Просроченные заказы — сверху.

### При каких действиях список заказов обновляется:

1. При pull-to-refresh.
 
2. Если перейти во вкладку «Мои» на главном экране, а потом вернуться 
назад во вкладку «Все».

3.Если применить фильтр по станции метро.

### При каких действиях список заказов не обновляется:

1. Если принять заказ, он перемещается в «Мои», но остальной список не 
обновляется.

### Функциональность экрана «Список заказов»:
1.Когда нет заказов, отображается экран «Заказов нет». Чтобы обновить 
экран, нужно сделать pull-to-refresh.

2. Когда пользователь делает заказ, появляется короткая версия карточки 
заказа.

3. Список заказов сортируется по приоритетности доставки: 
просроченные — сверху. Просроченным считается заказ, который не 
доставлен клиенту до 2359 в нужный день. Рамка и дата просроченной 
карточки подсвечивается красным цветом, жирность текста — Medium. 
Условие работает для списков заказов «Все» и «Мои».

4. Внутри вкладки «Все» есть фильтр по выбору метро. С его помощью 
курьер может настроить, заказы на каких станциях он хочет видеть. По 
тапу на фильтр открывается список: он формируется из тех станций, на 
которые уже есть заказы. Если есть два и более заказа с одинаковым 
метро, в фильтре появляется только одно наименование: одинаковые 
станции не дублируются.

5. Карточка фильтра увеличивается по мере добавления станций метро. В 
карточку вмещается максимум 8 станций: начиная с девятой появляется 
скролл.

6. Карточка заказа может быть в краткой или полной версии. 
- Поля для краткой версии: «Адрес», «Дата доставки», выбранная 
  станция метро.
- Поля для полной версии: «Адрес», «Дата доставки», выбранная 
  станция метро. Добавляется «Имя», «Фамилия», «Телефон», «Цвет», 
  «Комментарий». Если пользователь не заполнил поле «Цвет», 
  пишется «любой».

7. Переключить версию карточки можно через тап по карточке. Это 
работает для вкладок «Все» и «Мои».

8. При переходе в полный режим карточки кнопка «Принять» остаётся на 
месте. Карточки, которые идут следом, сдвигаются вниз.

9. Чтобы принять заказ, нужно тапнуть по кнопке «Принять». Это работает 
и для краткой, и для полной версий карточки.

10. При тапе по кнопке появляется уведомление с текстом «Хотите принять 
заказ?» и две кнопки «Да» и «Нет». Тап по «Нет» возвращает обратно на 
список заказов, кнопка «Принять» остаётся активной. Тап по «Да» 
подтверждает принятие заказа.

11. Чужой или отменённый заказ принять нельзя. Появляется сообщение: 
«Ты не можешь принять заказ. Его взял уже другой курьер или 
пользователь отменил его».

12. Когда заказ принят, карточка уезжает из списка «Все» — с анимацией 
движения вверх. У вкладки «Мои» появляется синяя точка — она 
обозначает, что во вкладке появился новый принятый заказ.
 
13. Логика работы синей точки: появляется, если есть непросмотренные 
карточки во вкладке «Мои». Автоматическое переключение на вкладку 
«Мои» не происходит.

14. Карточка, которую принял курьер, помещается во вкладку «Мои». 
Кнопка меняется на «Завершить». Завершить заказ можно тапом по 
кнопке «Завершить» — как в коротком, так и в полном виде карточки.

15. Если нажать на «Завершить», появляется уведомление «Вы завершили 
заказ?» и две кнопки — «Да» и «Нет». Тап по «Нет» возвращает обратно 
на список заказов, кнопка «Завершить» остаётся активной. Тап по «Да» 
подтверждает завершение заказа.

16. Когда заказ завершён, карточка заказа перемещается в самый низ 
списка. Если заказ был просрочен, но потом выполнен, карточка не
подсвечивается красным.

17. Завершённые заказы сортируются по времени выполнения: чем раньше 
завершён заказ, тем он ниже.


## Нотификация
1.  Уведомление приходит, когда осталось 2 часа, чтобы выполнить заказ. 
Заказ нужно доставить в день, который указал пользователь, до 2359. 
Например, заказ на 8 мая. Если в 2159 8 мая курьер ещё не доставил 
самокат, ему приходит пуш-уведомление.

2. Уведомление содержит такой текст: «2 часа до конца заказа. Заказ «ул 
Комнатная 1214» нужно выполнить до времени N . Если не успеваете, 
предупредите поддержку: 0101»

3. Переход по нотификации ведёт в приложение на вкладку «Мои».
   
## Отсутствие интернет-соединения

1. Если нет интернет-соединения, отображается всплывающее окно 
«Отсутствует интернет-соединение». Оно появляется, если тапнуть по 
любой активной кнопке на любом экране. Пропадает только по тапу по 
кнопке «Ок».
 
2. Когда пользователь тапнул по кнопке «Ок», всплывающее уведомление 
закрывается. Если интернета всё ещё нет, процесс повторяется: тап по 
любой активной зоне ведёт на всплывающее уведомление 
«Отсутствует интернет-соединение».

## Ориентация
 Приложение только в портретной ориентации.
 
### Ограничение полей

![image](https://github.com/user-attachments/assets/872e0cb0-e9c0-4de0-9982-5f88526fd85e)


![image](https://github.com/user-attachments/assets/738caecb-866b-49be-8405-0a7d235c1cb7)


 </details>

 <details>
  <summary>Макеты(Figma)</summary> 
   
  [макеты](https://www.figma.com/design/kqLqPvSvjLVLomkdadkAnk/mobile)
   
  ![image](https://github.com/user-attachments/assets/89d62f90-c61e-4236-8c41-14baf5c45c63)

</details>

<details>
  <summary>Тест-кейсы</summary> 

  https://docs.google.com/spreadsheets/d/1P0-mUWO0AT1GBVZkK4_u9wQC-xYcEtGymEvTNFhk8cY/edit?gid=424948590#gid=424948590

  </details>
<details>
  <summary>Задание 3</summary> 
  
  # API приложения Яндекс.Самокат

  Обрати внимание на техническую информацию при запуске приложения.
Изучи требования к бэкенду и документацию к API.
Разработай чек-лист и протестируй API по требованиям, которые выделены жирным шрифтом.
</details>

<details>
  <summary>Требования к бэкенду</summary> 

# Требования к бэкенду приложения

## Технологии
 
 Язык приложения — JavaScript. 
 Выполняется в среде Node.js v12.17.0.
 Доступ к приложению по протоколу HTTP 1.1. 
 
## Общие требования

 Приложение использует базу данных. БД — PostgreSQL. Приложение 
 взаимодействует с БД через npm-пакет sequelize поверх пакета 
 pg.sequelize — ORM для работы с различными БД в node.js.

 Запросы логируются через модуль winston. Документация к приложению 
 осуществляется с помощью модуля apidoc.

 Приложение должно отвечать требованиям REST.
 
 В приложении должен быть глобальный обработчик ошибок. При 
возникновении исключений они должны быть обработаны, а приложение 
должно продолжить работу.

 Ошибки приложения (неуспешно обработанные 
 запросы, исключения; ответы, отличные от 2XX) должны логироваться в 
отдельный файл error.log

## Требования к URL
### Вспомогательные URL

- Должен присутствовать URL, через который можно проверить, что бэкенд 
запущен и принимает запросы. При успешном ответе должен вернуться 
статус 200 OK .

- Должен присутствовать URL, через который работает поиск станций 
метро. В случае успешного поиска должны вернуться номер станции, её 
цвет и название. Если станций несколько, для каждой должны 
возвращаться номер, цвет и название. Если станция не найдена, должен 
вернуться пустой список.

## URL для курьеров
- Должен присутствовать URL: при обращении к нему курьер может 
зарегистрироваться в приложении. URL должен принимать 
логин, пароль и имя курьера. Логин, хэш пароля и имя курьера 
должны записываться в поля login , 
passwordHash и firstName таблицы Couriers. В поле passwordHash хранится 
хэш пароля, генерируется стандартными функциями, поэтому 
соответствие хэш-пароль проверить можно через авторизацию.

- Поле login должно быть уникальным. При успешной регистрации 
соответствующая запись должна появиться в базе. При неуспешной 
должна вернуться ошибка. Подробнее об ошибках в 
документации /docs/#api-Courier-CreateCourier

- Должен присутствовать URL для входа в учётную запись курьером. На вход 
должны отправляться логин и пароль курьера. При успешном входе должен 
вернуться id курьера. Если войти не удалось, должна вернуться ошибка.

- Должен присутствовать URL для удаления учётной записи курьера. На 
вход должен подаваться id курьера в таблице Couriers. При удалении 
связанные заказы в таблице Orders должны быть стёрты.


## URL для заказов

 Каждый раз, когда какой-нибудь из URL возвращает полные данные о 
заказе, ответ должен  содержать и статус каждого заказа. В статусе должны 
быть такие значения:

 0 — заказ создан, больше ничего с ним не происходило;
 
 1 — заказ принят курьером;
 
 2 — заказ завершён;-1 — заказ отменён.
 
 Статус должен вычисляться относительно значений полей в БД в 
таблице Orders (см. пункт «Описание содержимого базы данных»). Поля 
указаны в порядке приоритетности:

- finished = true -> status = 2
  
- cancelled = true -> status = -1

- inDelivery = true -> status = 1

- Остальные случаи -> status = 0

Должен присутствовать URL для создания заказа. При создании заказа 
указываются следующие параметры:
- имя;
- фамилия;
- адрес;
- ближайшая станция метро;
- телефон;
- количество дней аренды;
- дата доставки;
- комментарий;
- список подходящих цветов.
- 
При создании заказа ему должен быть присвоен индивидуальный номер для 
отслеживания.

Переданные параметры записываются в таблицу 
Orders следующим образом:
- имя: firstName
- фамилия: lastName
- адрес: address
- ближайшая станция метро: metroStation 
- телефон: phone
- количество дней аренды: rentTime 
- дата доставки: deliveryDate
- комментарий: comment
- список подходящих цветов: color
- номер отслеживания: track
- 
 Если заказ создан успешно, должен вернуться его номер отслеживания. В 
противном случае должна вернуться ошибка. Подробнее об ошибках в 
документации: /docs/#api-Orders-CreateOrder

- Должен присутствовать URL для получения данных о заказе по его 
номеру отслеживания. На вход должен подаваться номер. Если 
соответствующий заказ найден, должны вернуться данные о 
нём. Иначе должна вернуться ошибка.

- Должен присутствовать URL для принятия заказа курьером. URL принимает 
номер отслеживания заказа и id курьера. Если при принятии заказа 
возникли проблемы, должна вернуться ошибка.

- Должен присутствовать URL для отмены заказа. URL принимает номер для 
отслеживания заказа. В случае неуспешной отмены должна вернуться 
ошибка.

- Должен присутствовать URL для завершения заказа. На вход подаётся 
номер заказа. В случае неуспешного завершения должна вернуться 
ошибка.

- Должен присутствовать URL для получения всех заказов, которые 
соответствуют заданным параметрам. Параметры поиска — ближайшая 
станция метро и id курьера. Также должны быть переданы ограничения по 
количеству выводимых записей на странице и номер страницы. Подробнее 
об ошибках и кейсах применения в документации: /docs/#api-Orders
GetOrdersPageByPage

- Должен присутствовать URL для получения количества выполненных 
заказов курьера. На вход должен подаваться id курьера. Подробнее об 
ошибках и кейсах использования в документации: /docs/#api-Couriers-
GetOrdersCountByCourierId

### Ограничение полей

![image](https://github.com/user-attachments/assets/bb0077da-9195-4954-85e2-922e733a1039)

## Описание содержимого базы данных

 БД состоит из двух таблиц: Couriers и Orders. Первая таблица содержит данные 
о курьерах, вторая — данные о заказах.

### Couriers

![image](https://github.com/user-attachments/assets/4a52150a-e448-4fc2-8b7e-333d22fa3992)

### Orders

![image](https://github.com/user-attachments/assets/45832409-c62c-4cc2-a0e3-c1e20f140b67)

</details>

<details>
  <summary>Чек-лист</summary> 
https://docs.google.com/spreadsheets/d/1P0-mUWO0AT1GBVZkK4_u9wQC-xYcEtGymEvTNFhk8cY/edit?gid=336872680#gid=336872680
</details>
<details>
  <summary>Баг-репорты</summary> 

  [баг-репорты](https://karlen.youtrack.cloud/issues?q=%D1%82%D0%B5%D0%B3:%20Diploma)

</details>

  
  
 

  





  








  
