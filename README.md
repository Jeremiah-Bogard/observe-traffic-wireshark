# Observing Traffic Using Wireshark

In this repo I explain how to observed different types of traffic between a Windows 10 Virtual Machine and a Linux Virtual Machine using Wireshark.

## Requirments

- [Microsoft Azure](https://azure.microsoft.com/en-us/free/search/?ef_id=_k_CjwKCAjwjMiiBhA4EiwAZe6jQ5TPLrZtFBu6ZmulD8e96TJdh5lYt6AUC570-7RRDCMackhTQGSTExoCdQYQAvD_BwE_k_&OCID=AIDcmm5edswduu_SEM__k_CjwKCAjwjMiiBhA4EiwAZe6jQ5TPLrZtFBu6ZmulD8e96TJdh5lYt6AUC570-7RRDCMackhTQGSTExoCdQYQAvD_BwE_k_&gad=1&gclid=CjwKCAjwjMiiBhA4EiwAZe6jQ5TPLrZtFBu6ZmulD8e96TJdh5lYt6AUC570-7RRDCMackhTQGSTExoCdQYQAvD_BwE)
  - Windows 10 Virtual Machine
  - Linux (Ubuntu) Virtual Machine
- [Wireshark](https://www.wireshark.org/download.html) installed on Windows 10 VM

## Getting Started

After you have set up both Virtual Machines and downloaded Wireshark on the Windows 10 VM, then remote desktop into the Windows VM.

> ### For Mac Users
> If you are on a Mac, you will need to download [Microsoft Remote Desktop](https://apps.apple.com/us/app/microsoft-remote-desktop/id1295203466?mt=12) to connect to your Virtual Machines.

Now that you have logged in, open wireshark. Yours should look something like this:

![image](/wireshark.png)

As you can see there is a lot of messages spamming us in wireshark. You can think of Wireshark as a chat app. It connects us to the room and lets us see what the computer is saying along with who said it and other stuff. We can search for specific messages sent by a specific protocal by typing in the search bar. Go ahead and try it, type **icmp** in the search bar.

> ### ICMP (Internet Control Message Protocol)
> ICMP is a network level protocol. ICMP messages communicate information about network connectivity issues back to the source of the compromised transmission. It sends control messages such as destination network unreachable, source route failed, and source quench. It uses a data packet structure with an 8-byte header and variable-size data section[^1].
> [^1]: <https://www.extrahop.com/resources/protocols/icmp/>

It should stop spamming us with messages. If there are still some you can hit the reload button that is right above the search bar. The ICMP protocol is what the [ping](https://www.techtarget.com/searchnetworking/definition/ping) command uses. So if we were to ping our Linux VM in wireshark we would see the message log appear in wireshark. Go ahead and try it. Get the Linux VM's private IP address and open the Command Prompt in your Windows VM. Then type ``` ping 10.0.0.5 ``` where 10.0.0.5 is your Linux VM's private IP address.

![image](/icmp.gif)

## Other Traffic Examples

Here are some more examples of watching traffic through wireshark.

1. [SSH](#ssh)
2. [DNS](#dns)
3. [DHCP](#dhcp)

## SSH

![image](/ssh.gif)

## DNS

![image](/dns.gif)

## DHCP

![image](/dhcp.gif)
