# FortiGate Bootstrapping for Containerlab

This repository contains a modified `launch.py` script for running FortiGate containers in [Containerlab]. 

## The Problem
When running FortiGate images built with `vrnetlab` inside Containerlab, the standard YAML definition is often limited. It allows for basic settings (like changing the hostname), but it lacks native support for injecting a full startup configuration or template during the boot process.

## The Solution
I tweaked the Python launch script used by the container to allow for better flexibility. This modification enables you to inject a custom pre-configuration file (Day 0 config) into the FortiGate VM before it fully boots up.

## Contents
* `launch.py`: The modified Python launch script.
* `fgt_init.cfg`: A sample pre-configuration file to demonstrate the setup.

## How to Use

1.  **Build the Image:**
    Use [vrnetlab](https://github.com/vrnetlab/vrnetlab) to build your FortiGate docker image as usual.

2.  **Apply the Fix:**
    You will need to replace the default `launch.py` inside your built image or mount this modified version over it in your Containerlab topology file.


## Notes
* Ensure your FortiGate image version is compatible with the `vrnetlab` build process.

## Disclaimer
This is a personal project/tweak. Use at your own risk in lab environments.
