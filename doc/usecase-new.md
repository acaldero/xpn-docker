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

