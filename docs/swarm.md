# xpn-docker: Expand Docker

<details>

<summary><h2>Contents</h2></summary>

 1. [Summary of using xpn-docker](/docs/summary.md)
 2. [Build the container image](/docs/image.md)
 3. Some xpn-docker use cases:
    1. [Examples using XPN Ad-Hoc](/docs/usecase-xpn.md)
    2. [Examples of benchmarks with XPN Ad-Hoc](/docs/usecase-benchmarks.md)
    3. [Example  of Apache Spark and Ad-Hoc XPN](/docs/usecase-spark.md)
 4. [Multiple containers on multiple nodes](/docs/swarm.md)
 5. [Authors](/docs/authors.md)

</details>



## Multiple containers on multiple nodes

   The general steps are:
   ```bash
   : Step 1: Starting docker swarm
   ./xpn-docker.sh swarm-create machinefile

        : Step 2: Starting containers
        NC=$(wc machines | awk '{print $1}')
        ./xpn-docker.sh start $NC

             : Step 3: Doing execution
             ./xpn_docker.sh bash 1
             ./benchmark/xpn-mpi-native.sh
             exit
    
        : Step 4: Stopping containers (undoing 2)
        ./xpn-docker.sh stop

   : Step 5: Stopping docker swarm (undoing 1)
   ./xpn-docker.sh swarm-destroy
   ```


