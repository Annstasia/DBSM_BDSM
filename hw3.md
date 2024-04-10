Отчет о выполнении ДЗ3
1. Неприятное путешествие в windows.
   
   Открыла файл дз, попыталась скачать html. Выяснила, что в libre office и google docs не кликается ссылка. Решила, что час параллельно стоящей винды настал. Попыталась открыть в винде, спустя n кликов справилась. Решила переслать файл через телегу себе. Антивирус запретил. Отключила антивирус, вернулась в линукс. (Картиночек не будет, потому что автор не продумал отчет заранее, а повторять его не хочет)
2. https://pouchdb.com/guides/index.html - отсуда читала про couch и pouch db
   Отсюда можно понять:
   1. Есть couchdb, couchbase и cloudant. Последние две возникли из couchdb. Есть pouchdb - написанная на javascript БД c api аналогичным couchdb. Есть couchdb sync protocol, через который базы обмениваются данными. pouchdb, couchdb, couchbase и cloudant работают с ним, поэтому можно соединять любые из этих 4 баз
  
   2. Применительно к нашей задаче: pouchdb - база данных внутри клиентского браузера. Подключается js-скриптом. couchdb (или аналоги, как описано выше - не важно) - серверная бд. Они синхронизируются. Так пользователь при работе в оффлайн, изменения сохраняются в pouchdb, при появлении сети - отправляются в couchdb
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/53692820-f5cc-422b-8af0-3add9b792c1b)

    3. couchdb - nosql, работает с json-документами

3. В гайде из п.2 показан пример запуска установленного на устройство couchdb, я же запускаю через docker, как было в других домашках
   
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/3224ffb9-b484-4c1e-a2c0-1095a35bd1ee)

4. Создала базу данных 

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/be4ca3c7-ab46-4432-ab22-c84d6e3a48be)
   
5. Добавила документ со своей фамилией
   
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/4b75ba71-c89d-43b9-a0c6-d05effdfac78)
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/e1e579e9-d39e-4956-9e20-e960c7c88b44)

6. Настроила доступ к couch для всех доменов
 
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/922f2900-94af-468c-8b48-001263bd8478)
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/7af2e0a5-d105-46f8-afa4-db2b91543363)

7. Заменила в html-файле строку подключения к удаленной бд (25 строка) (к localhost добавлены логин и пароль из параметров docker run, имя бд заменено на нужное)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/1e381769-f473-4183-b9cf-2e3410183f40)

8. Открыла html в браузере:
    
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/451946b4-6d79-4590-b730-4805f1c36b96)

9. Остановила couchdb

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/603de8f4-7ae7-47c7-91d8-9c257a2620ff)

10. Обновила html. Сначала все пропало

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/5de7d8b9-b102-40ab-8f54-4cc9cdc1542a)
    
    После sync - вернулось
    
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/0675358b-5484-484e-9a61-309395377c81)

11. Не поднимая couchdb, понажимала на add, потом подняла couchdb. Изменения появились в couchdb
    
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/61c6d728-c4d1-4ddd-aa29-e40187609054)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/9875a119-0378-44fc-95d5-13464c306ab6)


Итого: pouchdb позволяет работать без подключения к couchdb. При подключении произойдет синхронизация данных

https://github.com/Annstasia/DBSM_BDSM/blob/main/PouchDB1.html - тут файлик после 10 пункта

