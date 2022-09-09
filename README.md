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

## Why so sad?
Deepstream can be incredibly frustrating to get started with. Although there is documentation and support from the Nvidia forums, it can still be very challenging to even get it working.

* The example apps sometimes don't work or have weird bugs
* Sometimes Nvidia introduces a bug that breaks builds and it lingers for months
* The "API" if you can call it one, is painful
* It's not even clear how to start building

## The Good Path

After working with Deepstream for a year, I have found my way to use it. I'll show you how to get started with it, and then show how Cutting Edge AI's workflow looks.

## Pre-requisites

* Nvidia GPU
* VSCode or some IDE that supports remote container development
* Docker
* Nvidia Docker




