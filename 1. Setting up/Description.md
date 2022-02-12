
![IP](https://user-images.githubusercontent.com/98809671/153718181-d72a81f7-4952-4fc2-b21d-53d3217c0f59.jpg)

Since both zones (INOVA and ENTA) are mirrors of each other, we're just going to describe one.

---

### Control

#### Subnets
The only machine with a public IP and direct access to the internet.

We will have three network interfaces and therefore three private IPs 172.31.(0.100; 110.100; 210;100).

1. The subnet 172.31.0.0/24 will only be used by our control machine.
2. The subnet 172.31.110.0/24 will only allow connection to our DMZ (demilitarized zone), 
3. The subnet 172.31.210.0/24 will server to connect all our network and private machines.

#### Services

Certificate Authority (CA), VPN, DNS, NAT and firewall

---

### DMZ

DMZ = Demilitarized Zone

#### Subnets

By separating our HTTP/S and FTP services to a single machine in a secular subnet, we are protecting our network from outside attacks, since they can use those service to target us.

#### Services

HTTP and HTTPS
1. In INOVA we will install the NGINX package
2. IN ENTA we will install the APACHE package

FTP
1. In INOVA we will install the ProFTPD package
2. IN ENTA we will install the VSFTPD package

---

### CENTRAL

#### Services

NFS = Network File System

NIS = Network Information Service

Mail Server
1. In INOVA we will install the Postfix and Courier packages
2. In ENTA we will install the Postfix and Dovecot packages

---

### Wazuh

We will install the service Wazuh in this machine and use it as our server. All the other machines will be our Wazuh clients.

Wazuh will allows us to see our weakness and how we can improvethe security on each machine.

---

### Sales and Marketing

We will install a graphic interface on each machine and use this to test all our services (HTTP, FTP, NFS, NIS and Mail)
