
Expand Docker v3.3
====================

Contents
========

 :: Some use cases with xpn-docker
    :: Examples using XPN Ad-Hoc
    :: Examples of benchmarks with XPN Ad-Hoc
    :: Examples of Ad-Hoc XPN with Apache Spark
 :: Using xpn-docker


Some use cases with xpn-docker
==============================

Examples using XPN Ad-Hoc
-------------------------

     * Expand (fuse)

       : 1. To start 3 containers
       ./xpn_docker.sh start 3
       ./xpn_docker.sh status

       : 2. Work from container 1
       ./xpn_docker.sh bash 1
       ./test/xpn-mpi-fuse.sh
       exit

       : 3. Stop all containers
       ./xpn_docker.sh stop

     * Expand (bypass)

       : 1. To start 3 containers
       ./xpn_docker.sh start 3
       ./xpn_docker.sh status

       : 2. Work from container 1
       ./xpn_docker.sh bash 1
       ./test/xpn-mpi-bypass.sh
       exit

       : 3. Stop all containers
       ./xpn_docker.sh stop

     * Expand (native)

       : 1. To start 3 containers
       ./xpn_docker.sh start 3
       ./xpn_docker.sh status

       : 2. Work from container 1
       ./xpn_docker.sh bash 1
       ./test/xpn-mpi-native.sh
       exit

       : 3. Stop all containers
       ./xpn_docker.sh stop


Examples of benchmarks with XPN Ad-Hoc
--------------------------------------

     * MDtest:

       : 1. To start 3 containers,
       : 2. sleep 5 seconds,
       : 3. work from container 1,
       : 4. and stop all containers
     
       ./xpn_docker.sh \
           start 3 \
           sleep 5 \
           exec 1 "./benchmark/xpn-mpi-mdtest.sh" \
           stop

     * IOR:

        : 1. To start 3 containers,
        : 2. sleep 5 seconds,
        : 3. work from container 1,
        : 4. and stop all containers

        ./xpn_docker.sh \
            start 3 \
            sleep 5 \
            exec 1 "./benchmark/xpn-mpi-ior.sh" \
            stop


Examples of Ad-Hoc XPN with Apache Spark
----------------------------------------

     * Word count for Apache Spark

       : 1. To start 3 containers
       ./xpn_docker.sh start 3
       ./xpn_docker.sh sleep 5

       : 2. Work from container 1
       ./xpn_docker.sh exec 1 ./spark/quixote-local.sh
       ./xpn_docker.sh exec 1 ./spark/quixote-xpn.sh

       : 3. Stop all containers
       ./xpn_docker.sh stop



Using xpn-docker
================

* Summary:

      ---------------------------------------------------------------------------------------------------------------
     |          Action                                                    |         Command                          |
      ---------------------------------------------------------------------------------------------------------------
     |                      | Build image                                 | ./xpndocker.sh build                     |
     | Container image      | IF (first time OR dockerfile updated)       |                                          |
     |                      | Save image                                  | ./xpndocker.sh image-save                |
     |                      | Load image                                  | ./xpndocker.sh image-load                |
      ---------------------------------------------------------------------------------------------------------------
     | Multiple nodes       | Starting docker swarm                       | ./xpndocker.sh swarm-create machinefile  |
     |                      | Stopping docker swarm                       | ./xpndocker.sh swarm-destroy             |
      ---------------------------------------------------------------------------------------------------------------
     |                      | To spin up 3 containers                     | ./xpndocker.sh start 3                   |
     | Work session         | To get into container 1                     | ./xpndocker.sh bash 1                    |
     |                      | To exit from container                      | exit                                     |
     |                      | To spin down all containers                 | ./xpndocker.sh stop                      |
      ---------------------------------------------------------------------------------------------------------------
     | Get information      | To check running containers                 | ./xpndocker.sh status                    |
     |                      | To get the containers internal IP addresses | ./xpndocker.sh network                   |
      ---------------------------------------------------------------------------------------------------------------

* Please beware of:

   * Any modification outside the "/work" directory will be discarded on container stopping.
   * Please make a backup of your work "frequently" (just in case).
   * You might need to use "sudo" before ./xpn_docker.sh if your user doesn't belong to the docker group
     * It could be solved by using "sudo usermod -aG docker ${USER}"


Authors
=======

 :: Félix García-Carballeira
 :: Alejandro Calderón Mateos
 :: Diego Camarmas Alonso
 :: Dario Muñoz Muñoz
 :: Elias del Pozo Puñal


