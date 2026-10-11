# My CSN09112 Lab and Coursework Page
This is my page which outlines the CSN09112 labs and coursework, and outlines the labs completed and the development of the coursework.

## Lab 1: Network Architecture
Within this lab [here](https://github.com/billbuchanan/csn09112/tree/master/week02_ids/lab), we were tasked with setting up the following network architecture:

<img width="1810" height="981" alt="image" src="https://github.com/user-attachments/assets/1ba17022-ceb9-4870-b53e-02f4430d1691" />

My running lab is [here](), and I completed all of the elements.

### Key elements of learning
In this lab, I learned how to configure pfsense to enable traffic the DMZ. This included DNS (Port 53 UDP), HTTP (Port 80 TCP) and HTTPs (Port 443 TCS).

### Key difficulties
I encounted difficulties related to Metasploit and Kali on the DMZ, and I solved these by re-applying the network settings. For the future, I will disable DHCP on the required interfaces.

## Lab 2: Network Security
Within this lab [here](https://github.com/billbuchanan/csn09112/tree/master/week03_ns/labs), we continued to use the architecture in Lab 1, and added new elements of Penetration Testing, such as using Hydra, NMAP and Metasploit.

### Key elements of learning
I learnt that I had to open up the firewall port on the DMZ to allow Kali on the DMZ to nmap the Ubuntu machine on the Private network. The lab is running [here](). Once I had completed this, I could properly nmap and discover that FTP, HTTP and IPP were running:

```
$ nmap 192.168.10.7
Starting Nmap 7.80 ( https://nmap.org ) at 2026-10-11 09:32 BST
Nmap scan report for localhost (192.168.10.7)
Host is up (0.000086s latency).
Not shown: 997 closed ports
PORT    STATE SERVICE
21/tcp  open  ftp
80/tcp  open  http
631/tcp open  ipp

Nmap done: 1 IP address (1 host up) scanned in 0.05 seconds

```
### Key difficulties
I had to make sure that I had the right firewall rules on pfsense. Hydra did not work initially, but I fixed it by making sure I had the right IP address on the target.


## Lab 3: AWS Architecture
In this lab [here](https://github.com/billbuchanan/csn09112/tree/master/week03_ns/labs), we aimed to set up a Microsoft Windows and an Ubuntu instance. The running servers are at [here]() and [here](), but these will only be temporary addresses as AWS will change after it powers the instances off.

### Key elements of learning
I discovered there were three main AWS keys that I needed to use to properly access the CLI. I fixed this by using:

```
eee_W_7008910@172.31.10.67:~$ export AWS_CONFIG_FILE=myconfig
eee_W_7008910@172.31.10.67:~$ nano myconfig 
    <<paste your user credentials in the editor >>

eee_W_7008910@172.31.10.67:~$ cat myconfig 
[default]
aws_access_key_id=ABBBUWYEY47O5FQCEWLA
aws_secret_access_key=iLLLLLiGocWkg+W6XyS4HhnWDXzcBKkayS8LAtM

eee_W_7008910@172.31.10.67:~$ aws ec2 describe-instances
{
    "Reservations": []
}
```



### Key difficulties
I found I had to open-up the ICMP port on the firewall to ping the running instances.



