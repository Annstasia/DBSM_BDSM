<h1>Relational H2</h1>
<h2>История развития СУБД</h2>
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

<h3>Распределение файлов БД по разным носителям?</h3>
1. Самое частое применение H2 в качестве in-memory. Носители не нужны
2. Можно использовать как файловую




