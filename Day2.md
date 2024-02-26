# Virtualization
# What is virtualization?
Virtualization enables the hardware resources of a single computer—processors, memory, storage and more—to be divided into multiple virtual computers, called virtual machines (VMs). 

Virtualization uses software to create an abstraction layer over computer hardware that allows the hardware elements of a single computer—processors, memory, storage and more—to be divided into multiple virtual computers, commonly called virtual machines (VMs). Each VM runs its own operating system (OS) and behaves like an independent computer, even though it is running on just a portion of the actual underlying computer hardware.
#  Hypervisors 
A hypervisor is the software layer that coordinates VMs. It serves as an interface between the VM and the underlying physical hardware, ensuring that each has access to the physical resources it needs to execute. It also ensures that the VMs don’t interfere with each other by impinging on each other’s memory space or compute cycles.

There are two types of hypervisors:

 - Type 1 or “bare-metal” hypervisors interact with the underlying physical resources, replacing the traditional operating system altogether. They most commonly appear in virtual server scenarios.
 - Type 2 hypervisors run as an application on an existing OS. Most commonly used on endpoint devices to run alternative operating systems, they carry a performance overhead because they must use the host OS to access and coordinate the underlying hardware resources.

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/d54260ae-2448-4bdb-b49d-bb5676f09ccd)
