# NS3 and NS3-GYM Installation

Installation guide for NS3, NetAnim and NS3-gym for Linux systems (works on WSL too)

## NS3 Installation
1. Update the Linux spt 
    `sudo apt upgrade`

2. Install the pre-requisites for NS3
    `sudo apt install g++ python3 cmake ninja-build git`

3. Create a directory
    ```
    mkdir ns3
    cd ns3
    ```

4. Clone the NS3 repository (/home/username/ns3)
    ```
    git clone https://gitlab.com/nsnam/ns-3-dev.git
    cd ns-3-dev 
    ```

5. Set up the NS3 configuration and build it
    ```
    ./ns3 configure --enable-examples --enable-tests
    ./ns3 build
    ```

6. Run the unit tests to check build
    `./test.py`   

7. Run an example code to cross verify
    `./ns3 run hello-simulator.cc`

## NetAnim Installation

1. Prerequisites
    ```
    sudo apt install qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools

    ```

2. Move to main NS3 directory and clone the NetAnim repo
    ```
    cd ns3
    git clone https://gitlab.com/nsnam/netanim
    ```

3. Move to netanim folder and run the make commands
    ```
    cd netanim
    qmake NetAnim.pro
    make
    ```

4. Run the GUI 
    ```
    ./NetAnim
    ```


## NS3-gym Installation

1. Prerequisistes
    ```
    sudo apt-get install libzmq5 libzmq3-dev libprotobuf-dev protobuf-compiler pkg-config
    ```

2. Move to the `contrib` directory
    ```
    cd /ns3/ns-3-dev/contrib
    ```

3. Clone the `ns3-gym` repo into the `contrib` folder
    ```
    git clone https://github.com/tkn-tub/ns3-gym.git ./opengym
    cd opengym/
    git checkout app-ns-3.36+
    ```

4. Build the project again
    ```
    ./ns3 configure --enable-examples
    ./ns3 build
    ```

> The build might show FAILED and deprecated APIs. Ignore those

5. Install `ns3-gym` models 
    ```
    cd ./contrib/opengym/
    pip3 install --user ./model/ns3gym
    ```

6.  Run sample to cross verify

    ```
    cd ./contrib/opengym/examples/opengym
    ./simple_test.py
    ```