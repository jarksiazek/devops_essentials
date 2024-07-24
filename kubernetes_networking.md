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
* Docker Networking vs K8s Networking
  * ![image](https://github.com/user-attachments/assets/bb0ce3b1-2a71-4391-9354-f2b0e905ef78)
  * docker networking has the same IP addresses
  * kubernetes networking has different IP addresses
 
* POD
  * every pod has an unique IP address in the cluster
  * POD - 2 or more containers (pause container + actual containers)
  * pause container - has the actual network ns
  * actual container uses the network namespace of the pause container
  * docker equivalent
    * ```
      docker run --name pause -itd ubuntu sleep infinity
      docker run --name actual-app --net=container:pause -itd appimage
      ```
* POD Network CIDR
  * range of IPS is shared by all PODs in the entire cluster
  * The pool of addresses is split into smaller chunks
  * non overlapping with the host network CIDR
* Cluster IP
  * helps to reach the actual containers providing the service
  * hides scaling up/down, failures, restarts of containers behidn the service
  * any microserivce that provides a service consumed by another party should use a Cluster IP
  * no network interfaces associated with the Cluster IP
  * totally virtual and implemented using iptables

for learnig
- IPTABLE
- NAT
- PROXY
- REVERSE PROXY 
