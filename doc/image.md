# Expand Docker


## Contents

 * [1. Summary of using xpn-docker](https://github.com/xpn-arcos/xpn-docker/doc/summary.md)
 * [2. Build the container image](https://github.com/xpn-arcos/xpn-docker/doc/image.md)
 * 3. Some xpn-docker use cases:
   * [3.1 Examples using XPN Ad-Hoc](https://github.com/xpn-arcos/xpn-docker/doc/usecase-xpn.md)
   * [3.2 Examples of benchmarks with XPN Ad-Hoc](https://github.com/xpn-arcos/xpn-docker/usecase-benchmarks.md)
   * [3.3 Examples of Apache Spark and Ad-Hoc XPN](https://github.com/xpn-arcos/xpn-docker/usecase-spark.md)
 * [4. Multiple containers on multiple nodes](https://github.com/xpn-arcos/xpn-docker/swarm.md)
 * [Authors](https://github.com/xpn-arcos/xpn-docker/authors.md)


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

