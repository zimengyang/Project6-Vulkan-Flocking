Vulkan Flocking: compute and shading in one pipeline!
======================

**University of Pennsylvania, CIS 565: GPU Programming and Architecture, Project 6**

* Zimeng Yang
* Tested on: Windows 10, i7-4850 @ 2.3GHz 16GB, GT 750M (Personal Laptop)

### Simulation Overview

![overview](gif/overview.gif)

### Questions and Answers

*Why do you think Vulkan expects explicit descriptors for things like generating pipelines and commands? HINT: this may relate to something in the comments about some components using pre-allocated GPU memory.*

* The explicit descriptors will make the pipeline more predictable by the programmer (because the programmer will be responsible for speicifying detailed configuration of pipeline stages).

*Describe a situation besides flip-flop buffers in which you may need multiple descriptor sets to fit one descriptor layout.*

* Rendering multiple models using same vertex and fragment shaders will be the situation where one descriptor layout but different descriptor sets. Different vertex indice and position information among different models but they all share the same layout. 

*What are some problems to keep in mind when using multiple Vulkan queues? take into consideration that different queues may be backed by different hardware; take into consideration that the same buffer may be used across multiple queues*
 
* Different hardwares may have different supported compatibilities, queues across multiple hardwares might need to consider this.
* Same buffer with accessing from different queues, there might be race conditions need to be considered.

*What is one advantage of using compute commands that can share data with a rendering pipeline?*

* Sharing the data through pipeline can get rid of copying input/output data, which is really expensive.

### Credits

* [Vulkan examples and demos](https://github.com/SaschaWillems/Vulkan) by [@SaschaWillems](https://github.com/SaschaWillems)
