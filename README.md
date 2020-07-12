# Accelerating The “Stable” Three-Way QuickSort Performance Leveraging The Modern Nvidia GPGPUs

### Author: Arthur V. Ratz @ Intel® DevMesh

Download the complete project ISO-images from Google Drive: https://drive.google.com/drive/folders/158kR9MPDbSYm0o7gGuw4dzKtoJDyqjyu?usp=sharing https://drive.google.com/drive/folders/1oSPPXOWTTUB9Mmng6uPjCxnnGqYymsTR?usp=sharing

## Overview / Usage
The following project is another alternative of the parallel “stable” three-way quicksort implementation, previously introduced in my https://devmesh.intel.com/projects/parallel-stable-sort-performance-optimization-using-intel-parallel-studio-xe-and-intel-oneapi-hpc-toolkit project. The main goal of this project is to provide an even better performance speed-up gain of the parallel “stable” three-way quicksort, offloading the execution of specific workloads to the Nvidia GPUs, rather than host CPU and other acceleration targets, offering the ultimately high performance (about 36x faster) compared to the sequential quicksort execution. Unlike the previous project, I’ve used the OpenMP 4.5/5.0 library with offloading capabilities and open-source distribution of the Intel’s Clang/LLVM compiler (https://github.com/llvm/llvm-project) to deliver a modern code, implementing the parallel three-way quicksort, being introduced.

## Methodology / Approach
The parallel “stable” three-way quicksort algorithm introduced in:
1.	"An Efficient Parallel Three-Way Quicksort Using Intel C++ Compiler And OpenMP 4.5 Library" - https://software.intel.com/en-us/articles/an-efficient-parallel-three-way-quicksort-using-intel-c-compiler-and-openmp-45-library
2.	"How To Implement A Parallel "Stable" Three-Way Quicksort Using Intel C++ Compiler and OpenMP 4.5 library" - https://software.intel.com/en-us/articles/how-to-implement-a-parallel-stable-three-way-quicksort-using-intel-c-compiler-and-openmp-45
3.	"How To Implement The Parallel "Stable" Sort Using Intel® MPI Library And Deploy It To A Multi-Node Computational Cluster" - https://software.intel.com/en-us/articles/how-to-implement-a-multi-node-parallel-stable-sort-using-intel-mpi-library
4.	"How To Optimize A Parallel Stable Sort Performance Using The Revolutionary Intel® oneAPI HPC Toolkit" - https://software.intel.com/en-us/articles/how-to-optimize-the-parallel-stable-sort-performance-using-intel-oneapi-hpc-toolkit

## How To Build And Run This Code

0. Download The Project's ISO-image at https://drive.google.com/drive/folders/158kR9MPDbSYm0o7gGuw4dzKtoJDyqjyu?usp=sharing

1.	Mount the iso-image by using the following command from bash-console terminal:

		user@intel-llvm:~$ mount .parallel_stable_sort_nvptx64.iso /mnt

2.	Copy all files from the mnt directory to a preferred location (e.g. home/user/Projects)

3.	Execute the disable-nouveau.sh script with root privileges by using the following command to permanently disable Nouveau default graphics driver:

	        user@intel-llvm:~$ sudo sh disable-nouveau.sh

	The system will reboot when the script execution is completed

4.	Execute the nvinstall.sh script with root privileges by using the following command to install the latest Nvidia Accelerated Graphics Driver and Nvidia CUDA Development Toolkit:
	
      	        user@intel-llvm:~$ sudo sh nvinstall.sh

	The system will reboot when the script execution is completed
	
5.	Execute the setup.sh script with root privileges by using the following command to install intel-llvmclang-10.0.0 development and build tools:

                user@intel-llvm:~$ sudo sh setup.sh

       The system will reboot when the script execution is completed

6.	Execute the buildrun.sh script to build and run the project’s code:
	
  	        user@intel-llvm:~$ sudo sh buildrun.sh

## Technologies Used
### Hardware:
•	Nvidia GeForce GTX 1070 SLI x 2 8 GiB GDDR5 Graphics Cards;
### Software:
•   OS Ubuntu Desktop 18.04.4 Bionic Beaver (Linux Kernel x86_64 5.3.0 or higher) **only**

•	Nvidia CUDA Development Toolkit;

•	Intel’s Open-Source Clang/LLVM compiler distribution;

•	OpenMP 4.5/5.0 Library with offloading capabilities;
