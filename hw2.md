# ДЗ по Redis
1. Запускаем redis
![Screenshot from 2024-04-05 00-44-38](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/3f9e072f-ee09-47bb-8438-04c936a95ec3)
docker compose -f RedisDocker.yml up -d

2. Генерируем json и заполняем redis через
   Размер получившегося json 40мб:
    ![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/0e3a5b51-9d14-41af-bb46-b7dbcd046c8f)
   
При вставке после генерации 1000000 котиков столкнулась с тем, что redis отказывается вставлять его за 1 раз. Погуглив выяснила, что ограничение 100000. Поэтому генерируем 10 раз по 100000 котиков

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/708e72d2-4810-4703-ace2-1afb2db9948d)

Подключаемся к redis:
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/687525c3-afda-4c07-b41b-b2c32c4812a3)

Вставка:

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/c2bc4327-9b37-464e-8720-826d6a187968)
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/5d9dc43a-a1d3-4fb1-a462-3a050d0001f7)
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/1b40f62f-a0fa-4dc8-8c35-d62c101e42e1)

Замеряем количество обрабатываемых запросов в секунду:

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/d75bed42-2331-4067-a225-1191e9723c42)


Теперь рассмотрим на тех же данных работу кластера. python-часть полностью совпадает, при условии что мастер-нода на том же порте

 docker compose -f RedisDocker.yml down

 docker compose -f RedisCluster.yml up 
RedisCluster.yml:
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/1f8cac7e-daf6-4160-9cdb-a5da7b8cff53)
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/6e9c3795-48c7-4b8b-ba02-d842f3d9f55d)

Перезапускаем все ячейки в ноутбуке и проверяем время:
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/1ebc74bb-352f-4af1-8ac6-98c697067f7f)

Вывод 1: запросы выполняются очень быстро

Вывод 2: при репликации скорость замедляется (логично, но когда я только посмотрела benchmark-и, поразилась магии редиса, выполняющего работу с репликами "быстрее". Потом дошло/прочитала, что измерения ведутся в requests per second)
 


