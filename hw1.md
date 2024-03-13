# Выполнение ДЗ1
1. Докер уже был
2. Pull Mongo, создание директории хранения файлов контейнера, запуск контейнера
![img](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/3f23410d-1533-4a99-82bb-d899144b5fa7)
3. Открыла консоль mongo
   ![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/d3bd853e-e402-4bb2-807a-b8a75b25ecfc)
4. Скачала первый датасет из предложенной статьи
     ![Screenshot from 2024-03-06 17-57-22](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/88172773-a6e6-48b5-a731-d84e2f7e595f)
5. Написала скрипт, который по датасету делает команду вставки
   ![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/f3c6f22e-2d9e-4889-8353-5d7bc10b7692)
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/6330f2bb-b4c3-4fc5-99bc-8c4941a3700a)
6. Выполнила несколько crud-команд
   
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/9ea3949d-4a8f-46f8-96d6-555fc3204425)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/b6ac360c-807d-4eb2-97ca-561afc50621e)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/48a13548-0b9b-4bf4-ac81-68691f1c0611)

Посмотрела на spending_score у мужчин и женщин:
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/617917ec-f6b5-4b08-b4d5-f3b072c01496)

![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/88c444ed-453b-4bd9-b902-e0e4f04e21cc)

Замер времени для поиска и сортировки по spending_score до создания индекса
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/891814ab-516e-4dca-bf8a-357669bc5318)


То же самое, но после создания индекса spending_score
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/9f02e24f-2085-49f8-bffb-9e5696e7ddd9)

Заметим, что фильтрация, в том числе с последующей сортировкой по возрастанию ускорилась, а просто вывод с сортировкой замедлился

Удаление всех, кроме людей с spending_score > 20 и возрастом от 20 до 25 (логичней было задать через lte, gte, но они уже использовались ранее):
![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/d6a60b23-7f42-4fab-896b-6f2843c711c8)

7. Вышла из mongosh дважды нажав Ctrl+C, из докера через exit
8. docker ps, чтобы узнать container_id. docker stop \<id\>, чтобы остановить
