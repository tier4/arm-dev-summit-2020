# Autoware Open Source Software for Autonomous Vehicles
<a href="https://devsummit.arm.com/"><img src="Arm-DevSummit-EmailBanner-500x120-1A.png" alt="ARM Dev Summit Logo"></a>

# Hands-on workshop at Arm DevSummit October 2020
In this tutorial, we will run through some basic and then some more advanced features of Autoware, the first all-in-one open source autonomous driving system.

## Minimum System Requirements
### Hardware
 - x86 CPU (8 cores)
 - 16GB RAM 
 - NVIDIA GPU (4GB memory)

### Software
 - Ubuntu 18.04
 - NVIDIA driver


### Recommendations
- Run Ubuntu natively. Whilst Ubuntu can be easily run on other platforms as a virtual machine, Autoware is a computationally demanding piece of software that should be run natively whenever possible.
- Remove existing installations of CUDA and TensorRT. If CUDA or TensorRT were installed prior to setting up Autoware, both of them should be removed to avoid any version conflicts.

# Exercises
- [Exercise 0: Introduction (or how we're going to be doing things)](exercises/exercise0.md)
- [Exercise 1: Setting up your Autoware test environment](exercises/exercise1.md)
- [Exercise 2: RViz basics and replaying a rosbag](exercises/exercise2.md)
- [Exercise 3: NDT Scan Matching](exercises/exercise3.md)
- [Exercise 4: Simulation testing with dummy objects](exercises/exercise4.md)
