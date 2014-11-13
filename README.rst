Modern Scientific Computing with Python
=======================================
Course at IEEE Nuclear Science Symposium and Medical Image Conference
---------------------------------------------------------------------

:Date:   2014-11-13
:Author: Matt McCormick <matt.mccormick@kitware.com>

Introduction
------------

Python is an increasingly popular scientific computing programming language,
offering an easy-to-learn, versatile interface that glues together work from
many other languages well. Furthermore, it is supported by a vibrant open
source community. While the Python standard library is often touted for being
“batteries-included”, the scientific Python environment is even richer, with
many powerful tools and packages to enhance the scientific computing workflow.

In this one-hour course, we will introduce and refresh participants to modern
Pythonic practices from the perspective of a researcher with a C or C++
background.

We will cover

1) Creating a reproducible computational environment with Docker,
2) Interactive analysis and literate programming with the IPython Notebook,
3) A brief survey of the fundamental scientific Python packages: numpy, matplotlib, scipy, sympy, and pandas, nose
4) Writing efficient, compiled C/Python hybrid code with Cython, and
5) Wrapping C and C++ libraries in Python with XDress.

By the end of the course, participants will be prepared to be more effective
computational researchers through an introduction into modern scientific
Python practices.

The course is delivered as series of IPython_ notebooks. The computational
environment to run the notebooks is stored as a Docker image.

View the Static Notebooks, Online
---------------------------------

Read-only renderings of the notebooks can be found at these links:

* `0 Introduction <http://nbviewer.ipython.org/github/thewtex/ieee-nss-mic-scipy-2014/blob/master/0_Introduction.ipynb>`_
* `1 Docker <http://nbviewer.ipython.org/github/thewtex/ieee-nss-mic-scipy-2014/blob/master/1_Docker.ipynb>`_
* `2 IPython <http://nbviewer.ipython.org/github/thewtex/ieee-nss-mic-scipy-2014/blob/master/2_IPython.ipynb>`_
* `3 SciPy Stack <http://nbviewer.ipython.org/github/thewtex/ieee-nss-mic-scipy-2014/blob/master/3_SciPy_Stack.ipynb>`_
* `4 Cython <http://nbviewer.ipython.org/github/thewtex/ieee-nss-mic-scipy-2014/blob/master/4_Cython.ipynb>`_
* `5 XDress <http://nbviewer.ipython.org/github/thewtex/ieee-nss-mic-scipy-2014/blob/master/5_XDress.ipynb>`_
* `6 Outro <http://nbviewer.ipython.org/github/thewtex/ieee-nss-mic-scipy-2014/blob/master/6_Outro.ipynb>`_

Run the Notebooks Live, Locally
-------------------------------

All the software required to run the notebooks is available in the provided
Docker_ image.

Install Docker
..............

To install Docker, follow the instructions distributed with the flash drive in
the `docker/installation` directory. Outside of the conference, the `online
installation instructions <https://docs.docker.com/installation/>`_ can also
be followed.

Import the Docker Image
.......................

There are three options to import the Docker image.

Import the stored image distributed with the flash drive.
  The Docker image is stored in the file `docker/image/ieee-nss-mic-scipy-2014.tar`.
  Run the command::

    docker load docker/image/ieee-nss-mic-scipy-2014.tar

  On OSX or Windows, move the tar file to `/Users` or `C:\\Users\\` which is
  mounted in the Docker VM as `/Users` or `/c/Users` so it is available to the
  docker client.

Pull the image from DockerHub_.
  DockerHub_ is an online repository of docker images that makes it easy to
  search, push, and pull images from public or private repositories. To
  download the image from DockerHub::

    docker pull thewtex/ieee-nss-mic-scipy-2014

Build the image from its sources.
  Docker images are created from a set of instructions that are stored in a
  *Dockerfile*. These are the set of commands that are used to set up the
  image, like installing packages, compiling dependencies, editing
  configurations, etc.  To build the image::

    cd docker/src/ieee-nss-mic-scipy-2014
    ./build.sh

Run the Docker Image
....................

To run the IPython notebook server::

  docker run -d --name notebook -p 443:8888 -v $PWD:/notebooks/:rw -e "PASSWORD=MakeAPassword" thewtex/ieee-nss-mic-scipy-2014

This command should be executed from the directory containing the `*.ipynb`
notebook files so `$PWD` will make the notebook files available to the docker
container. Replace *MakeAPassword* with a password of your choice.

Docker container port 8888, where the IPython notebook server is listening for
connections, will be forwarded to the localhost on port 443. To connect to the
notebook server, point your browser to *https://localhost/*.

.. note::

  On OSX and Windows, extra steps are required to find the address and the
  port that the container has been forwarded to.  In a Boot2Docker shell,
  run::

    boot2docker ip

  This should return an address like *192.168.59.103*.  Next, find the port
  in the docker environment with::

    docker port notebook 8888

  This should return a port like *49153*.

  Port your browser to the resulting address and port; for example:
  *https://192.168.59.103:49153*.

After connecting to the container, an "untrusted connection" warning from your
browser is expected.

To list the running containers::

  docker ps

To list the running and stopped containers::

  docker ps -a

To stop the container::

  docker stop notebook

To start the container again::

  docker start notebook

To remove the container::

  docker rm notebook


.. _IPython: http://ipython.org/
.. _Docker: https://www.docker.com/
.. _DockerHub: https://hub.docker.com/
