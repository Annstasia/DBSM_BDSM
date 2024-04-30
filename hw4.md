<h1>Relational H2</h1>
<h2>История развития СУБД</h2>
https://h2database.github.io/html/history.html
Томас Мюллер разработал БД Java Hypersonic SQL. В 2001 году проект был остановлен, была создана группа HSQLDB (в которую также входил Мюллер) 
для продолжения работы над кодом Hypersonic SQL. В мае 2004 года началась разработка H2, в декабре 2005 H2 была опубликованаю.
Название H2 получилось как Hypersonic 2, хотя БД была написана с нуля
Сейчас активно используется в java в качестве in-memory БД\
<h2>Инструменты для взаимодействия с СУБД</h2>
Так как основная область применения БД - Java приложения, то можно взаимодействовать через spring boot. Подключить maven/gradle dependency, настроить application properties, использовать jpa или jdbc

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/e0af2ff9-7b87-4a63-aa2a-ec61b9ebeb2d)

Конфиги. Задно дадим доступ к консоли

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/6106eaae-302f-431b-845a-f8456db3d024)


Любимый JPA

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/a3d7a1c7-e793-4efb-89b9-5af916fb1123)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/4249a2c3-35e4-49b1-8889-50e5205d5447)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/9c2536cc-47de-42a7-ac65-7bf1051c9cc6)

Зайдем в консоль (пароль для входа в application.properties):

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/8d5c194e-4b13-42c6-ab47-a32a050fa1f3)


Также можно скачать jar с официального сайта:
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/3e01fa03-f7de-4cd8-95e5-0fdd2cefe75c)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/488a6dfa-ed25-4b83-b040-51bda99b5f01)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/56d050ca-5b84-4a72-9cc5-903d06ada369)


<h2>Какой database engine используется в вашей СУБД?</h2>
Использует H2 database engine

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/09a8cc1a-2c85-430c-a528-b7cabc617b2a)

<h2>Как устроен язык запросов в вашей СУБД? Разверните БД с данными и выполните ряд запросов. </h2>
Использует язык запросов sql

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/c76a8605-662b-497d-95c9-bf00f9c5704b)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/c6702284-3326-414d-a7d0-98b3cfd2693e)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/4587353d-9d28-40f3-8da5-34014ebf8d38)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/423b61ab-0880-4f6a-ba7f-161fef9c0f8c)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/539ac1f9-3684-4a6a-8166-e67b74ea7af9)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/d0b6b1e8-e94b-4e6e-abf7-7f9df0dace57)

<h2>Распределение файлов БД по разным носителям?</h2>
1. Самое частое применение H2 в качестве in-memory, особенно часто - как заглушку на бд в тестах для облегчаения. 
Распределенность не нужна


2. Тем не менее, БД поддерживает кластеризацию (https://h2database.github.io/html/features.html)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/0301b069-62e1-4084-8186-434c969e3d67)

<h2>На каком языке/ах программирования написана СУБД?</h2>
Java Java Java ....

Какой main feature? Written in Java

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/d694f89c-7ac2-47aa-8e72-932639c0796f)

<h2>Какие типы индексов поддерживаются в БД? Приведите пример создания индексов.</h2>
https://h2database.github.io/html/features.html
Multiple index types (b-tree, tree, hash)
Support for multi-dimensional indexes

<h2>Как строится процесс выполнения запросов в вашей СУБД?</h2>
Как обычный sql. Выборка результатов, сортировка, группировка

<h2>Есть ли для вашей СУБД понятие «план запросов»? Если да, объясните, как работает данный этап.</h2>
План есть

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/4825e00b-b267-4880-9702-04a5944c6467)

Как работает план одном оптимизатору известно. H2 использует фзык sql, т. е. мы никак не указываем как выполять запрос. Оптимизатор смотрит различные возможные планы, выбирает оптимальный (не факк, что правильно, но в большинстве случаев). Через EXPLAIN можкм посмотреть какой план выбрал

<h2>Поддерживаются ли транзакции в вашей СУБД? Если да, то расскажите о нем. Если нет, то существует ли альтернатива?</h2>
Релационная БД. Поддерживается ACID, транзакции - тем более

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/1dc07249-ac06-4e7c-a20a-f175c73442d5)

<h2>Какие методы восстановления поддерживаются в вашей СУБД. Расскажите о них.</h2>
Изменения в бд логгируются в журнале транзакций (исключение - in memory объекты). При перебое питания изменения, не сохранившиеся из-за сбоя применятся повторно при следующим открытии БД

Если все совсем плохо, то есть Recover Tool, который может вытаскивать содержимое поврежденной БД

<h2>Расскажите про шардинг в вашей конкретной СУБД. Какие типы используются? Принцип работы.</h2>

Нет шардинга

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/6faa188c-7f36-4547-ae3b-2954b0389196)

<h2>Возможно ли применить термины Data Mining, Data Warehousing и OLAP в вашей СУБД?</h2>
Нет. H2 - легковесная реляционная БД

<h2>Какие методы защиты поддерживаются вашей СУБД? Шифрование трафика, модели авторизации и т.п.</h2>
1. Высшая степень защиты - разработчиков просят не довать доступ к серверы ненадежным соединениям

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/0b41eba1-f532-4456-9132-f15c5010ef65)

2. Encrypted storage. Защита есть, но слабая

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/eecdd5bb-ddb9-48b8-ad34-05203eaf4b4d)

3. Доступ к консоли по логину и паролю


<h2>Какие сообщества развивают данную СУБД? Кто в проекте имеет права на коммит и создание дистрибутива версий? Расскажите об этих людей и/или компаниях.</h2>
https://h2database.github.io/html/history.html

HSQLDB developer group развивает, но вообще проект open source https://github.com/h2database/h2database. 

Среди активных участников проектов:

Evgenij Ryazanov https://github.com/katzyn - часто коммитит и отвечает на stackoverflow, мерджит, создает дистрибутивы

Andrei Tokar - часто коммитит и мерджит

В целом pull request можно создавать всем. Неожиданно: pull-request (3 штуки) от мантикоры https://github.com/manticore-projects

<h2>Где найти документацию и пройти обучение? Как быть в курсе происходящего?</h2>

https://github.com/h2database/h2database

https://h2database.github.io/html/main.html

Можно следить за github, можно следить за https://groups.google.com/g/h2-database

