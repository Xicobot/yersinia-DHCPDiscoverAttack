# DHCP Discover attack

## Introduction to yersinia

With Yersinia, besides being able to carry out DHCP attacks, we can do many other things; however, in this case, we’ll perform the Discover attack, which is the most basic and easiest of all.
What we need is to have Kali Linux and, for ethical reasons, a DHCP server that does not limit incoming Discover packets so we can observe how the program operates.

## How to attack

First we install yersinia with this command.
```
sudo apt install yersinia
```

![install](/img/install.png)

Before we execute yersinia, we need to make sure that we have connection to the DHCP server.

![conection](/img/connect.png)

After making sure we have connection, we will run Yersinia in graphical mode with the command 
```
yersinia -I
```
and execute it.

(In graphical mode, we need to press space and F2 to change the attack mode, since yersinia have multiple attacks, we select DHCP mode, and them we press X that runs a new window, that displays what type of package we are going to send to te server as an attack)

![Attack](/img/attack.png)

### How to check out if it works?
Run the command 
```
journalctl -u isc-dhcp-server.service
```
and then check on the server to see if it is receiving all those Discover packets.
