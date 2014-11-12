Modern Scientific Computing with Python
=======================================
Course at IEEE Nuclear Science Symposium and Medical Image Conference
---------------------------------------------------------------------

:Date:   2014-11-12
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

Running the Notebooks
---------------------

All the software required to run the notebooks is available in the provided
Docker_ image.

Install Docker
..............

To install Docker, follow the instructions distributed with the flash drive in
the `docker/installation` directory. Outside of the conference, the `online
installation instructions <https://docs.docker.com/installation/>`_ can also
be followed.

.. _IPython: http://ipython.org/
.. _Docker: https://www.docker.com/
