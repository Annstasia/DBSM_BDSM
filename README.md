Классификация СУБД
1. DragonFly - CA (<link>https://www.dragonflydb.io</link>)

 Dragonfly is architected to deliver the scalability that modern data workloads require. Say goodbye to complex multi-node environments with endless configuration options and infinite points of failure. Dragonfly can effortlessly scale up to handle over 1TB of data and 4 million QPS on a single node, with a simple primary-replica pattern for high availability - один узел, высокая доступность и консистентность, но нет partition-tolerance
 
2. ScyllaDB - PA - написано на официальном сайте <link>https://www.scylladb.com/glossary/cap-theorem/</link>
   ![image](https://github.com/Annstasia/DBSM_BDSM/assets/45208486/52b2dd07-d38a-41d2-b53e-76f462d2b565)

3. ArenadataDB - CP
Consistency: "The system is fully ACID-compliant, i.e. the same tables can be used for reading and writing, with no risk of data loss."
<link>https://docs.arenadata.io/en/ADB/current/concept/data-model/tables/partitioning.html</link>
