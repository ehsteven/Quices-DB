# Quiz 9 Esteven Fernández 31/05/2023

1. Suponiendo que un sistema de bases de datos relacional que presenta un read-heavy
workload y los queries son muy diferentes, explique detalladamente ¿porque el uso
de caches puede afectar el rendimiento del sistema de forma negativa?

    Cuando se realizan sistemas de Read-heavy los cachés se utilizan para el almacenamiento de resultado frecuentes que utilizan los usuarios para un mejor rendimiento por lo que si se hacen muchas lecturas de consultas variadas poco frecuentes el sistema no se beneficiaría del cache y haría que se hagan las consultas desde la base de datos y provoque fallos en el rendimiento.
    
    Ahora bien, si se realiza una actualización de los datos que se encuentran a la par esto podría provocar que los datos que se obtengan de la cache sean inconsistentes o incorrectos y esto haría que la cache quede innecesaria por lo que se deberán consultar desde la base de datos y provocar una sobrecarga y afectar de gran manera el rendimiento.
    
    
2. El particionamiento de tablas en bases de datos relacionales es un concepto muy
parecido al de shards en bases de datos NoSQL, explique detalladamente ¿Cómo
afecta el particionamiento y el sharding en el rendimiento de bases de datos SQL y
NoSQL?

* Para el rendimiento con particionamiento en las bases de datos relacionales se tiene
   *  Mejora la distribución de carga en las tablas de la base de datos relacional, los datos se distribuyen en diferentes particiones o fragmentos que permiten aligerar la carga entre los múltiples servidores y esto ayuda a mejorar el rendimiento del procesamiento de las consultas. 
   * Ayuda con la eficiencia entre las operaciones de mantenimiento, el particionamiento facilita operaciones de mantenimiento como la recuperación de datos, seguridad, por la forma en la que se dividen los datos en fragmentos más pequeños

* Para el rendimiento de sharding en bases de datos NoSQL 
   * Mejora la carga y escalabilidad horizontal ya que realizar el sharding implica dividir los datos en shards o fragmentos y distribuirlos entre los servidores o los nodos presentes en la base de dato y esto ayuda a que se distribuya la carga de trabajo y claramente en la escalabilidad horizontalmente si se agregan más servidores. 
   * Mayor disponibilidad en cuanto los datos se distribuyen en diferentes shards se logra que la disponibilidad de los datos aumente, esto implica si alguno de los servidores o nodos falla los demás shards estarán disponibles sin comprometer la disponibilidad total de la base de datos.

3. En un sistema de bases de datos con Strong Consistency cuyo workload es de
read-heavy y write-heavy, ¿Cómo afectan los exclusive locks el rendimiento de las
bases de datos NoSQL?
* Pueden bloquear las lecturas y las escrituras cuando un recurso está bloqueado por alguna escritura en curso, por lo que cualquier lectura o escritura deberá esperar que el recurso sea libera para poder operar sobre la misma.
* Los tiempos de esperar pueden resultar más prolongados de lo normal, esto se debe si alguna de las escrituras dura más de lo debido por algún tipo de complejidad en sus datos el exclusive lock lo mantendrá en estado bloqueado durante ese tiempo.
* También puede generar conflictos a la hora de generar los locks, pues si los bloqueos se prolongan por demasiado tiempo las demás operaciones quedaran sin ejecutarse por mucho tiempo, además que es muy probable que se generen bloqueos mutuos y esto conlleva a realizar rollback o reintentos a la hora de realizar las operaciones, por lo que esto genera una deficiencia en el rendimiento.

4. Explique detalladamente, ¿Cómo afecta la selección de discos físicos el rendimiento
de una base de datos SQL y NoSQL?
* El rendimiento se ve afectado por la velocidad de acceso en el caso de los discos HDD son más lentos en comparación a los SDD y la velocidad de acceso si es un elemento de suma importancia para el rendimiento de la base de datos, entonces para la hora de acceder a la memoria de alguno de los dos discos sin duda se escogería un SDD.
* También a la hora de transferir datos donde de igual manera los discos SDD son más rápidos en la transferencia de datos que los discos HDD afectando así el rendimiento de transferencia de la base de datos.
