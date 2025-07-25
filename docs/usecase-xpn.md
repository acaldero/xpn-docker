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



## Example of using Expand with native API, with LD_PRELOAD (bypass), and with FUSE

   <br>
   <html>
   <table>
   <tr>
   <td>
   Expand (FUSE)
   </td>
   <td>
   Expand (LD_PRELOAD)
   </td>
   <td>
   Expand (native)
   </td>
   </tr>
   <tr>
   <td>
   </html>
     
   ```bash
 : Step 1. 
 ./xpn_docker.sh start 3
 ./xpn_docker.sh status

 : Step 2. 
 ./xpn_docker.sh bash 1
 cd ./test
 ./xpn-mpi-fuse.sh
 exit

 : Step 3. 
 ./xpn_docker.sh stop
   ```

  <html>
  </td>
  <td>
  </html>

  ```bash
 : Step 1. 
 ./xpn_docker.sh start 3
 ./xpn_docker.sh status

 : Step 2. 
 ./xpn_docker.sh bash 1
 cd ./test
 ./xpn-mpi-bypass.sh
 exit

 : Step 3. 
 ./xpn_docker.sh stop
  ```

  <html>
  </td>
  <td>
  </html>

  ```bash
 : Step 1. 
 ./xpn_docker.sh start 3
 ./xpn_docker.sh status

 : Step 2. 
 ./xpn_docker.sh bash 1
 cd ./test
 ./xpn-mpi-native.sh
 exit

 : Step 3. 
 ./xpn_docker.sh stop
  ```

  <html>
  </td>
  </tr>
  </table>
  </html>


  Then, the general steps are:
   1. Starting 3 containers
   2. Then, do some work from container 1
      * Bash on container 1
      * Execute example with Expand native access or access by using FUSE or by using LD_PRELOAD
      * Exit from container 1
   4. Stopping all containers


