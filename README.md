1. Remove the old database files from Neo4j:
    ```
    sudo rm -rf /var/lib/neo4j/data/databases/graph.db
2. Unzip the `graph.tgz` file and move it to the location that Neo4j (pre-installed on your VMs) expects using the following command: 
    ```
    tar -xvf graph.tgz && sudo mv graph.db /var/lib/neo4j/data/databases/
3. When using submitting a spark job or starting a pyspark notebook to run spark jobs on your local VM you cannot configure spark.driver.memory using SparkConf. Instead you must use the driver-memory command line parameter for spark-submit such as:
    ```
    pyspark --num-executors 5 --driver-memory 2g --executor-memory 2g
