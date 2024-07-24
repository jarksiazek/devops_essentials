* Container Networking
  * Linux Virtual Networking
   * <img width="423" alt="image" src="https://github.com/user-attachments/assets/028b6590-4ad3-4da2-bb9b-33cff9df4fc4">
    * virtual switch/bridge
      * docker0 bridge  
    * virtual interfaces
      * veth, tap
    * namespace
      * a logical copy of the network stack with routes, firewalls, network devices

  * Docker Networking
    * <img width="285" alt="image" src="https://github.com/user-attachments/assets/cfa8ddb2-3fcc-44da-a705-9eafec5ccd22">
    * virtual bridge "docker0"
    * source NAT rules to provide connectivity for the containser outside world via the Host IP address
    * destination NAT rules to expose services running inside the containers
    * the docker network is completely isolated (host private networking)

  * IPtables
    * a program used to configure the tables provided by the Linux kernel firewall (netfilter) and the chains and rules it stores
    * tables
      * raw
      * mangle
      * nat
      * filter
    * chains
      * INPUT
      * PREROUTING
      * FORWARD
      * POSTROUTING
      * OUTPUT
* Kubernetes Networking
  *  
* Network plugins

for learnig
- IPTABLE
- NAT
- PROXY
- REVERSE PROXY 
