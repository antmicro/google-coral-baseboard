======================
Google Coral Baseboard
======================

.. image:: Images/google-coral-baseboard.jpg
   :scale: 40%

Overview
========

This repository contains open hardware design files created by `Antmicro <http://www.antmicro.com>`_.
The design files describe a custom carrier board supporting a TPU SoM module included in `Coral Edge TPU Development Board <https://coral.withgoogle.com/products/dev-board>`_.
The board offers standard I/O interfaces and allows to connect MIPI CSI-2 compatible image sensors over a unified Flexible Flat Cable (FFC) connector.

Key features
============

* Interface connectors for Coral Edge TPU module
* Gigabit Ethernet RJ45 connector
* Micro USB serial debug connector
* Micro SD card interface
* 50-pin FFC connectors exposing MIPI CSI-2 camera interfaces
* USB-C DFP (Host) port
* Mini HDMI video output interface
* Integrated DC/DC power supply accepting 6-36VDC of input voltage

The PCB project files were prepared in Altium Designer 14.1

Board layout & dimensions
=========================

The picture below presents the general layout of the PCB with IO interfaces marked.

.. figure:: Images/coral-baseboard-layout.png

Getting started
===============

The board can be produced and assembled using the provided design files.
Please take a look at the mechanical layers for more information regarding the PCB stackup recommended for fabrication.
The board accepts power supply voltage in range of 6-36VDC.
It is recommended to use a 12V 2A DC supply to power the board.
The board will start the processing module automatically after connecting the power supply.
Please refer to the Coral documentation for more details regarding `flashing procedure <https://coral.withgoogle.com/tutorials/devboard-reflash/>`_.

Debug UART connection
---------------------

Most of the debug messages are provided through the serial console.
The board is equipped with a FTDI chip offering both UART interface to the host PC.
Please refer to the schematic sheets for more details.
The default debug UART channel is accessible through ``/dev/ttyUSB0`` (assuming that there are no other FTDI units connected to your PC).
The default baudrate for serial debug connection is 115200 baud with 8-bit transmission, 1 stop bit and with no flow control.
