# Expand Docker


## Contents

 * [1. Summary of using xpn-docker](/doc/summary.md)
 * [2. Build the container image](/doc/image.md)
 * 3. Some xpn-docker use cases:
   * [3.1 Examples using XPN Ad-Hoc](/doc/usecase-xpn.md)
   * [3.2 Examples of benchmarks with XPN Ad-Hoc](/doc/usecase-benchmarks.md)
   * [3.3 Examples of Apache Spark and Ad-Hoc XPN](/doc/usecase-spark.md)
 * [4. Multiple containers on multiple nodes](/doc/swarm.md)
 * [Authors](/doc/authors.md)


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


