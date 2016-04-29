# Project ideas

## What is this?

I got asked if I have any ideas for projects for motivated enthusistic OpenCL/compute/ml guys.  Since ideas evolve over time, I created this page, to brainstorm a bit

## OpenCL Benchmarks

Soumith is creating/organizing GPU benchmarking at https://github.com/DeepMark/deepmark
- his original [convnet-benchmarks](https://github.com/soumith/convnet-benchmarks) page already contains a couple of OpenCL libraries, ie a couple of mine (DeepCL, cltorch), and an OpenCL port of Caffe by Fabian Tschopp, "greentea"
- there are far too many benchmarks for me to support all of these personally, at least straight off
- therefore a project could be to take one of greentea/DeepCL/cltorch, and ensure it runs on one or more of the deepmark benchmarks
  - and bonus marks for optimizing the library for best performance in the process :-)
 
## OpenCL support for ml libraries

Two existing libraries now provide OpenCL support, ie:
- caffe
- torch

Several do not, eg:
- mxnet
- tensorflow (but I guess Google might handle this, and some combination of sycl, or an opencl backend for gpucc might go a long way for this?)
- theano

Therefore, a project could be to port one of these libraries, with the goal for example being to port enough layers across to be able to run at least one of the [convnet-benchmarks](https://github.com/soumith/convnet-benchmarks) or [deepmark](https://github.com/DeepMark/deepmark) benchmarks

## Decoupling machine learning libraries from hw-optimized convolutions

I'm sort of working on this myself, so if you pick this, there is a risk it might already have been done before you even start. Who knows? Anyway, the idea is expressed in the following slides, decoupling ml libraries from the convolutional implementation, to give optimal performance on any platform, whilst the ml library keeps everything else in opencl, and is itself also portable.

Alternatively, if the architecture has already been accepted and implemented by the community, then a related project could be to create one specific hardware device, and create an optimized convolutional library implementation for that hardware.  Note that this might not involve much/any OpenCL, although such a design decision would obviously be handled by the implementor.


