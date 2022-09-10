# Tears in the Rain - Deepstream Workshop
![image](https://user-images.githubusercontent.com/1065118/189254429-e423a27a-14bb-4908-91c8-61be38b939cf.png)

## Overview
Nvidia Deepstream is an incredible accelerated operational inference pipeline? What does that mean?

* Decodes Video
* Runs accelerated Inference
* Re-Encodes

All of this occurs on the GPU as much as possible. One of the bottlenecks in video inference is copying video data back and forth from CPU to GPU memory.
This leads to a massive acceleration.

![image](https://user-images.githubusercontent.com/1065118/189396248-2832f7b6-961b-4145-8ca9-36057260cc26.png)

Not only is it fast, it supports a vast amount of neural net architectures.

![image](https://user-images.githubusercontent.com/1065118/189408180-3b0def90-a65c-4d26-9fa6-45dbbc8ebc4c.png)

Thus, given almost any neural net for visual problems, you can ingest, infer, and output incredbily quickly.

## Why Care?

There are two extremes that appear to be common in visual AI usage in the real world. Experimental algorithms that are impressive but run slowly 
in real life data pipelines, and then highly rigid optimized pipelines. What Deepstream lets you do is cross the gap. You can run research-y neural networks hot off the grill in your preferred deep learning framework, and then have them running at high fps in a real life inference situation.


## Why so sad?
Deepstream can be incredibly frustrating to get started with. Although there is documentation and support from the Nvidia forums, it can still be very challenging to even get it working.

* The example apps sometimes don't work or have weird bugs
* Sometimes Nvidia introduces a bug that breaks builds and it lingers for months
* The "API" if you can call it one, is painful
* It's not even clear how to start building

## The Good Path

After working with Deepstream for a year, I have found my way to use it. I'll show you how to get started with it, and then show how Cutting Edge AI's workflow looks.

## Pre-requisites

* Linux (No WSL!)
* Nvidia GPU
* VSCode or some IDE that supports remote container development
* Docker
* Nvidia Docker

## Workshop

### A little on pre-requisites
Nvidia Docker is tricky to get set up. Different linux distributions have different packages for this. Even sub varietes like PopOS do.
Due to the cgroups changes in modern linux, you may have to use this kernel parameter to disable the unified cgroups.

https://github.com/NVIDIA/nvidia-docker/issues/1447

### Remote Development
First, you must get remote development set up. Don't even try to set up Deepstream on your local machine. There are way too many fragile dependencies.

You main guides for this:

* https://code.visualstudio.com/docs/remote/containers
* https://catalog.ngc.nvidia.com/orgs/nvidia/containers/deepstream

I'll show you how it's set up in this repository, take a look at the .devcontainer folder. That fully describes the development container setup.

### Access Control
Giving access to the docker container that deepstream is running to expose an X window is not easy. If you have a workstation on a secured network, all your troubles can be solved with a simple 

  xhost +
  
Run in a terminal *not* in the container. 

### Running your first deepstream sample, test 1

Move in terminal or open the `opt/nvidia/deepstream/deepstream/samples/apps/sample_apps/deepstream_test1`.

We just need to build then

    make
  
Then we can run the app

    ./deepstream-test1-app opt/nvidia/deepstream/deepstream/samples/streams/sample_720p.h264
  
So that demonstrates one of the simplest possible applications of deepstream, given a file, run inference on it. It only run on local files, so let's expand on that

### Running your expanded deepstream sample, test 2

    cd /opt/nvidia/deepstream/deepstream/sources/apps/sample_apps/deepstream-test2
  
Build it

    make

Run it

    ./deepstream-test2-app opt/nvidia/deepstream/deepstream/samples/streams/sample_720p.h264






