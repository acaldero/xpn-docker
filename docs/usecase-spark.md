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



##  Examples of Ad-Hoc XPN with Apache Spark
      
   * Word count with Apache Spark <img width="650" height="1">

      ```bash
      : 1. To start 3 containers
      ./xpn_docker.sh start 3
      ./xpn_docker.sh sleep 5

      : 2. Work from container 1
      ./xpn_docker.sh exec 1 ./spark/quixote-local.sh
      ./xpn_docker.sh exec 1 ./spark/quixote-xpn.sh

      : 3. Stop all containers
      ./xpn_docker.sh stop
      ```
      

