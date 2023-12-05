### CKS
* read-only secret as volume 
<details><summary>UFW</summary>
<br>
<p>List of Open Ports</p>
<p>
  
```bash
netstat -an | grep -w LISTEN
```
</p>
<p>Install UFW</p>
<p>
  
```bash
apt-get install ufw
```
</p>
<p>Rules</p>
<p>
  
```bash
#Add
ufw status #get ufw status
ufw default allow outgoing #allow outgoing
ufw default deny incomming #deny incoming
ufw allow from 172.16.238.5 to any port 22 proto tcp
ufw allow from 172.16.238.5 to any port 80 proto tcp
ufw allow from 172.16.100.0/28 to any port 80 proto tcp
ufw allow 1000:2000/tcp #allow ports between 1000-2000 tcp
ufw deny 8080 #optional, the all incoming ports were already denied
ufw enable

#Delete
ufw delete deny 8080
ufw delete 5 #order is taken from "ufw status"
```
</p>

</details>

<details><summary>AppArmor</summary>
<br>
<p>Essential commends</p>
<p>
  
```bash
systemctl status apparmor # check if apparmor is already installed
cat /sys/module/apparmor/parameters/enabled # check if apparmor module is enabled
cat /sys/kernel/security/apparmor/profiles # get list of loaded profiles
aa-status # summary of all loaded profiles

```
</p>
<p>Example 1 - a profile for restricting file write</p>
<p>
  
```bash
#include <tunables/global>

profile k8s-deny-write flags=(attach_disconnected) { #k8s-deny-write - name of the profile
  #include <abstractions/base>

  file, # applied to file operations

  deny /** w, #action - deny
}

```
</p>

```bash
sudo apparmor_parser -q /etc/apparmor.d/k8s-deny-write # load the profile into AppArmor
sudo aa-status
  
}

```
</p>

</details>
