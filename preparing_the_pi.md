# Setting up the Raspberry Pi For PWM directly to servo's

## Prerequisites

First have a Raspberry Pi setup with Raspian. I prefer a headless setup but it doesn't really matter.

It should have python3. You should be able to get to a command line on it.

## Installing the python packages 

From a command line:

    $ sudo apt-get update 
    $ sudo apt install python3-gpiozero pigpio python3-pigpio

## Enabling the deamon

    $ sudo systemctl enable pigpiod
    $ sudo systemctl start pigpiod

## MeArm Wiring

The wiring I followed is from https://pinout.xyz/pinout/mearm_pi.
