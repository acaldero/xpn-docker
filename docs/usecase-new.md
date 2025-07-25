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



## How to add a new use case

  1. Add the software to install for the new use case into the ```install-src``` directory/folder:

      ```bash
      cp install.sh install-src/100-new.sh
      ```

  2. Add the scripts to use the new use case to the ```lab-home``` directory/folder:

      ```bash
      mkdir -p lab-home/new
      cp -a execute*.sh lab-home/new/
      ```

  3. Build the image with the new added usecase:

      ```bash
      ./xpn_docker.sh clean-build
      ```

