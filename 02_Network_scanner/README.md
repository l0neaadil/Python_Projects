# Network Scanner:
  
- Network scanning refers to scanning of whole network to which we are
  connected and try to find out what are all the clients connected to 
  our network. We can identify each and every client using their IP and
  MAC address.
  
## Steps for creating Network Scanner:

1. Create an ARP packet using ARP() function.
2. Create an Ethernet packet using Ether() function.
3. Combine ARP request packet and Ethernet frame using ‘/’.
4. Send this to your network and capture the response from different devices using srp()
   function.
5. Print the IP and MAC address from the response packets.
  
## Scapy:

- Scapy is a library supported by both Python2 and Python3. It is used
  for interacting with the packets on the network. It has several 
  functionalities through which we can easily forge and manipulate the 
  packet. Scapy module is not included in Python3 library by default.
  
- *summary():* This method provides us the status of the packet that we
 have created. It does not provide the detailed information about the 
 packet, it just gives us the basic idea like what is the destination 
 of the packet etc.

- *show():* This method is very similar to summary() method. It gives
 more detailed information about the packet.

- *ARP():* This function defined in scapy module allows us to create 
ARP packets (request or response). By default, if we are calling it, 
it will create an ARP request packet for us. 

			arp_packet = scapy.ARP()
			arp_packet.show()
			

- *Ether():* This function defined in scapy module allows us to create 
Ether packets.
   
            Ethernet_packet = scapy.Ether()
            Ethernet_packet.show()
			
			
- ARP Packet and Ethernet_packet:
		
![Ethernet_Packet](https://user-images.githubusercontent.com/68290275/99192307-373a1e00-2798-11eb-98c0-5258bce53067.png)

- *Send/Receive Functions:* Scapy comes with send(), sendp(), sr(), srp(),
  sr1() and srp1() functions for sending packets and receiving responses.
  The send() functions are used to send  packets while sr() functions are
  used to send  packets when you expect a response back. The p at the end 
  of the function name means that we're sending at L2 instead of L3. The 
  functions with a 1 in them mean that Scapy will send the specified packet
  and end after receiving 1 answer/response instead of continuing to listen
  for answers/responses.

### Note:
- Both the programs are to be run through command line (linux).
- Both the programms have been tested on python2.
- Illustration for running main_scanner.py (through command line) :
   
   '''
   root@kali:~/PycharmProjects/Network_scanner# python main_scanner.py -t 10.0.2.3
   '''
   
- To run scanner_basics.py use command in the form:
   
   '''
   root@kali:~/PycharmProjects/Network_scanner# python scanner_basics.py
   '''
   
- Dont misuse the program.
   
