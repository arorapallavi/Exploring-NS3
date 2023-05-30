# NS-3 INSTALLATION 
## Steps are for installing NS3 on WSL2 (Windows Subsytem for Linux) - Ubuntu 20.04.5 LTS

### Step 1 : Update system packages
``` 
sudo apt update
sudo apt upgrade
```
### Step 2 : Install required dependencies 
```
sudo apt install build-essential autoconf2.64 libgtk2.0-dev git python3-pip python3-dev pkg-config python3-setuptools
 ```
### Step 3 : Download NS3
Create a directory where you want to download NS3 and navigate into it:
```
mkdir ns3
cd ns3
```
Now, clone the NS3 repository :
```
git clone https://gitlab.com/nsnam/ns-3-dev.git
```
Switch into the directory
```
cd ns-3-dev
```
### Step 4 : Build NS3
```
cmake /home/<linux_user>/ns3/ns-3-dev
```

### Step 5 : Adjust build options
 If required, you can pass additional options to the cmake command to adjust the build configuration.Eg:
 ```
 cmake -DCMAKE_BUILD_TYPE=Release /home/<linux_user>/ns3/ns-3-dev
 ```
### Step 6 : Build the project
```
cmake --build .
```
### Step 7 : Test using first.cc
```
cd /home/<linux_user>/ns3/ns-3-dev/examples/tutorial
cp first.cc ../../scratch/
cd /home/<linux_user>/ns3/ns-3-dev/
make
```
Notice these lines when the command finishes execution
```
-- Configuring done
-- Generating done
-- Build files have been written to: /home/<linux_user>/ns3/ns-3-dev
Scanning dependencies of target scratch_first
[  0%] Building CXX object scratch/CMakeFiles/scratch_first.dir/first.cc.o
[  0%] Linking CXX executable ../build/scratch/ns3-dev-first
```
Navigate to folder where the executable file has been created and run it
```
cd /home/<linux_user>/ns3/ns-3-dev/build/scratch
./ns3-dev-first
```
Output should be similar to below
```
At time +2s client sent 1024 bytes to 10.1.1.2 port 9
At time +2.00369s server received 1024 bytes from 10.1.1.1 port 49153
At time +2.00369s server sent 1024 bytes to 10.1.1.1 port 49153
At time +2.00737s client received 1024 bytes from 10.1.1.2 port 9
```
### Congratulations, You have successfully installed ns3 !


