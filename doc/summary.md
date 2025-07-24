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


## Summary of using xpn-docker


  <html>
  <table>
  <tr>
  <th colspan="2">Action</th>
  <th>Command</th>
  </tr>

  <tr>
  <td rowspan="3">
  Container image
  </td>
  <td colspan="1"> build image <br> IF((First time OR dockerfile updated)) </td>
  <td><code>./xpn_docker.sh build</code>
  </td>
  </tr>
  <tr>
  <td colspan="1"> Save image  </td>
  <td><code> ./xpn_docker.sh image-save</code>
  </td>
  </tr>
  <tr>
  <td colspan="1"> Load image  </td>
  <td><code> ./xpn_docker.sh image-load</code>
  </td>
  </tr>

  <tr>
  <td rowspan="3">
  Multiple nodes
  </td>
  <td>  
  Starting docker swarm
  </td>
  <td>
  <code>./xpn-docker.sh swarm-create machinefile</code>
  </td>
  </tr>
  <tr>
  <td colspan="2">
  [[ Work session ]]
  </td>
  </tr>
  <tr>
  <td>  
  Stopping docker swarm
  </td>
  <td>
  <code>./xpn-docker.sh swarm-destroy</code>
  </td>
  </tr>

  <tr>
  <td rowspan="4">
  Work session
  </td>
  <td colspan="1"> To spin up <b>3</b> containers </td>
  <td><code>./xpn_docker.sh start <b>3</b></code>
  </td>
  </tr>
  <tr>
  <td colspan="1"> To get into container <b>1</b>  </td>
  <td><code> ./xpn_docker.sh bash <b>1</b></code>
  </td>
  </tr>
  <tr>
  <td colspan="1"> To exit from container </td>
  <td><code>exit</code>  </td>
  </tr>
  <tr>
  <td colspan="1"> To spin down all containers </td>
  <td><code>./xpn_docker.sh stop</code>
  </td>
  </tr>

  <tr>
  <td rowspan="2">
  Get information
  </td>
  <td>  
  To check running containers
  </td>
  <td>
  <code>./xpn_docker.sh status</code>
  </td>
  </tr>
  <tr>
  <td>  
  To get the containers internal IP addresses
  </td>
  <td>
  <code>./xpn_docker.sh network</code>
  </td>
  </tr>

  </table>
  </html>

* **Please beware of**:
   * Any modification outside the "/work" directory will be discarded on container stopping.
   * Please make a backup of your work "frequently" (just in case).
   * You might need to use "sudo" before ./xpn_docker.sh if your user doesn't belong to the docker group
     * It could be solved by using "sudo usermod -aG docker ${USER}"


