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



## Examples of benchmarks with XPN Ad-Hoc

   * IOR

      ```bash
      : 1. To start 3 containers,
      : 2. sleep 5 seconds,
      : 3. work from container 1,
      : 4. and stop all containers
      
      ./xpn_docker.sh \
          start 3 \
          sleep 5 \
          exec  1 "./benchmark/xpn-mpi-ior.sh" \
          stop
      ```
      
   * MDtest

      ```bash
      : 1. To start 3 containers,
      : 2. sleep 5 seconds,
      : 3. work from container 1,
      : 4. and stop all containers
      
      ./xpn_docker.sh \
          start 3 \
          sleep 5 \
          exec  1 "./benchmark/xpn-mpi-mdtest.sh" \
          stop
      ```


