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



## Build the container image

The first time xpn-docker is deployed or when the ```docker/dockerfile``` is updated we need to build the container image.

  * To build the container image for a single node:
       ```bash
       ./xpn-docker.sh clean-build
       ```

  * To build and distribute the container image to multiple nodes:
    * Build and save the image to the ```xpn_docker.tgz``` file by using:
        ```bash
       ./xpn-docker.sh clean-build
        ./xpn-docker.sh image-save
        ```
    2. Copy ```xpn_docker.tgz``` to other nodes, and load this file:
        ```bash
        scp xpn_docker.tgz  node-x
        ssh node-x ./xpn-docker.sh image-load
        ```

