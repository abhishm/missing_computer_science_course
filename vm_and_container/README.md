The article web page is [here](https://missing.csail.mit.edu/2019/virtual-machines/).

## Virtual Machines

1. Simulated computer within the main computer
2. Provide isolation that brings security from malicious softwares
3. There is a hypervisor that is responsible for simulating these machines.
4. All the call to hardware goes via host OS therefore VMs are sometimes slow.
5. Some of the hardware such as graphics card are not accessible to VMs.
6. There is also some inbuilt support in hardware such as CPU's to make VM's faster.
7. Most of the cloud providers use VMs for simulating many customers within their server such Amazon EC2.

## Docker

1. Share the kernel with the host.
2. Can simulate the same machine as the host OS. For example, it is not possible to have a windows docker image in a Mac
   OS.
3. Host OS is responsible for providing a thin layer called `jail` to let the container feels its isolated.
4. The docker is created by 4 steps
    1. FROM - Download the docker image from
    2. CMD - Execute these commands after downloading
    3. EXPOSE - Expose these ports to outside world
    4. ENTRY POINTS - Run this code
5. Containers are lightweight and faster compare to VM because they share the host kernel so all the calls to hardware
   goes
   same as the host OS.
6. Containers provide weaker isolations compare to VM.
7. Many companies such as Heroku they allow users to define their code and requirements, they spin-off their containers,
   and serve their web servers.