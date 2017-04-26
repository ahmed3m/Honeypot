# Project 9 - Honeypot

Time spent: **5** hours spent in total

> Objective: Setup a honeypot and provide a working demonstration of its features.

### Required: Overview & Setup

- [X] A basic writeup (250-500 words) on the `README.md` desribing the overall approach, resources/tools used, findings
	- There are lots of resources online available for setting up a honeypot; however, it is usually confusing and hard configuring and setting it up. Therefore, I used the [Modern Honey Network (MHN)](https://github.com/threatstream/mhn) which provides a streamlined approach to setting up a low-interaction honeypot. I first cloned the github repository on my host machine, then I started setting up the MHN server and honeypot virtual machines (VM) via Vagrant. Then inside the server VM, I cloned the mhn repository again but using a patched fork instead due to an [oustanding issue](https://github.com/threatstream/mhn/issues/383). Then I started installing and running the server using `./install_mhnserver.sh`. This allowed me to create the server that monitors the honeypot. Then after that, I went to the server IP address in the browser, in order to deploy the honeypot, which in this case is `Ubunto - Dionea`. [Dionea](https://github.com/rep/dionaea) is a low-interaction honeypot designed to trap malware although in this case, I will just use it to detect network activity specifically port scanning. Then using the honeypot VM, I executed the deploy command I copied from the browser. Finally, using the server VM, I ran a scan against the honeypot VM using nmap by using the following command `nmap -sV -P0 10.254.254.101`, and I was able to see the attacks in the attacks page.
- [X] A specific, reproducible honeypot setup, ideally automated:
	- A Vagrantfile or Dockerfile which provisions the honeypot as a VM or container

### Required: Demonstration

- [X] A basic writeup of the attack (what offensive tools were used, what specifically was detected by the honeypot)
	- I used nmap for the attack. nmap maps a network by sending packets and analyzing responses. It can detect hosts, services, OS, and more. The command I used for the attack was `nmap -sV -P0 10.254.254.101`. This detected the ports
- [X] An example of the data captured by the honeypot (example: IDS logs including IP, request paths, alerts triggered)
- [X] A screen-cap of the attack being conducted
<img src='' title='Video Walkthrough' width='' alt='Video Walkthrough' />
