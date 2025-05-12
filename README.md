# cs455-homework-6-icmp-traceroute-solved
**TO GET THIS SOLUTION VISIT:** [CS455 Homework 6-ICMP Traceroute Solved](https://www.ankitcodinghub.com/product/cs455-homework-6-icmp-traceroute-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;91755&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS455 Homework 6-ICMP Traceroute Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<div class="page" title="Page 1">
<div class="layoutArea">
<div class="column">
ICMP Traceroute Lab

In this lab you will learn how to implement a traceroute application using ICMP request and reply messages. Students are strongly encouraged to first do the ICMP Ping lab before the ICMP Traceroute lab as it is done with the same approach. The checksum and header making are not covered in this lab, refer to the ICMP ping lab for that purpose, the naming of most of the variables and socket is also the same.

Traceroute is a computer networking diagnostic tool which allows a user to trace the route from a host running the traceroute program to any other host in the world. Traceroute is implemented with ICMP messages. It works by sending ICMP echo (ICMP type ‘8’) messages to the same destination with increasing value of the time-to-live (TTL) field. The routers along the traceroute path return ICMP Time Exceeded (ICMP type ‘11’ ) when the TTL field become zero. The final destination sends an ICMP reply (ICMP type ’0’ ) messages on receiving the ICMP echo request. The IP addresses of the routers which send replies can be extracted from the received packets. The round-trip time between the sending host and a router is determined by setting a timer at the sending host.

Your task is to develop your own Traceroute application in python using ICMP. Your application will use ICMP but, in order to keep it simple, will not exactly follow the official specification in RFC 1739..

Code

Below you will find the skeleton code for the client. You are to complete the skeleton code. The places where you need to fill in code are marked with #Fill in start and #Fill in end. Each place may require one or more lines of code.

Additional Notes

<ol>
<li>You do not need to be concerned about the checksum, as it is already given in the code.</li>
<li>This lab requires the use of raw sockets. In some operating systems, you may need administrator/root
privileges to be able to run your Traceroute program.
</li>
<li>See the end of Lab 4 ‘ICMP Pinger’ programming exercise for more information on ICMP.</li>
<li>This will not work for websites that block ICMP traffic.</li>
<li>You will have to turn your firewall or antivirus software off to allow the messages to be sent and
received.
</li>
</ol>
What to Hand in

You will hand in the complete code and screenshots of your Traceroute output for four different target hosts.

</div>
</div>
</div>
<div class="page" title="Page 2">
<div class="layoutArea">
<div class="column">
Skeleton Python Code for the ICMP Traceroute

from socket import * import os

import sys

import struct

import time import select import binascii

ICMP_ECHO_REQUEST = 8 MAX_HOPS = 30

TIMEOUT = 2.0

TRIES = 2

# The packet that we shall send to each router along the path is the ICMP echo # request packet, which is exactly what we had used in the ICMP ping exercise. # We shall use the same packet that we built in the Ping exercise

def checksum(string):

# In this function we make the checksum of our packet

# hint: see icmpPing lab

def build_packet():

# In the sendOnePing() method of the ICMP Ping exercise ,firstly the header of our # packet to be sent was made, secondly the checksum was appended to the header and # then finally the complete packet was sent to the destination.

# Make the header in a similar way to the ping exercise. # Append checksum to the header.

# Don’t send the packet yet , just return the final packet in this function. # So the function ending should look like this

packet = header + data return packet

def get_route(hostname):

</div>
</div>
</div>
<div class="page" title="Page 3">
<div class="layoutArea">
<div class="column">
bytes])[0]

</div>
</div>
<div class="layoutArea">
<div class="column">
timeLeft = TIMEOUT

for ttl in range(1,MAX_HOPS):

</div>
</div>
<div class="layoutArea">
<div class="column">
for tries in range(TRIES):

destAddr = gethostbyname(hostname)

#Fill in start

# Make a raw socket named mySocket

#Fill in end

mySocket.setsockopt(IPPROTO_IP, IP_TTL, struct.pack(‘I’, ttl)) mySocket.settimeout(TIMEOUT)

try:

d = build_packet()

mySocket.sendto(d, (hostname, 0))

t= time.time()

startedSelect = time.time()

whatReady = select.select([mySocket], [], [], timeLeft) howLongInSelect = (time.time() – startedSelect)

if whatReady[0] == []: # Timeout

print(” * * * Request timed out.”) recvPacket, addr = mySocket.recvfrom(1024)

timeReceived = time.time()

timeLeft = timeLeft – howLongInSelect

</div>
</div>
<div class="layoutArea">
<div class="column">
if timeLeft &lt;= 0: print(” *

except timeout: continue

else:

</div>
<div class="column">
* *

</div>
<div class="column">
Request timed out.”)

</div>
</div>
<div class="layoutArea">
<div class="column">
#Fill in start

#Fetch the icmp type from the IP packet #Fill in end

if types == 11:

bytes = struct.calcsize(“d”)

timeSent = struct.unpack(“d”, recvPacket[28:28 +

</div>
</div>
</div>
<div class="page" title="Page 4">
<div class="layoutArea">
<div class="column">
(timeReceived -t)*1000, addr[0]))

</div>
</div>
<div class="layoutArea">
<div class="column">
bytes])[0] (timeReceived-t)*1000, addr[0]))

</div>
<div class="column">
print(” %d rtt=%.0f ms

</div>
</div>
<div class="layoutArea">
<div class="column">
bytes])[0]

print(” %d (timeReceived – timeSent)*1000, addr[0]))

return

else:

print(“error”)

<pre>                           break
                    finally:
</pre>
</div>
<div class="column">
rtt=%.0f ms

</div>
</div>
<div class="layoutArea">
<div class="column">
get_route(“google.com”)

Optional Exercises

</div>
</div>
<div class="layoutArea">
<div class="column">
print(” %d rtt=%.0f ms

</div>
<div class="column">
%s” %(ttl,

recvPacket[28:28 + %s” %(ttl,

recvPacket[28:28 + %s” %(ttl,

</div>
</div>
<div class="layoutArea">
<div class="column">
elif types == 3:

bytes = struct.calcsize(“d”) timeSent = struct.unpack(“d”,

</div>
</div>
<div class="layoutArea">
<div class="column">
elif types == 0:

bytes = struct.calcsize(“d”) timeSent = struct.unpack(“d”,

</div>
</div>
<div class="layoutArea">
<div class="column">
mySocket.close()

</div>
</div>
<div class="layoutArea">
<div class="column">
Currently the application only prints out a list of ip addresses of all the routers along the path from source to the destination. Try using the gethostbyname method to print out the names of each intermediate route along the route.

</div>
</div>
</div>
