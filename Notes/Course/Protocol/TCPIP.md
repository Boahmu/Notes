#Protocol 
**TCP** (or **T**ransmission **C**ontrol **P**rotocol for short) is another one of these rules used in networking.

This protocol is very similar to the OSI model that we have previously discussed in room three of this module so far. The TCP/IP protocol consists of four layers and is arguably just a summarised version of the OSI model. These layers are:
-   Application
-   Transport
-   Internet
-   Network Interface

Very similar to how the OSI model works, information is added to each layer of the TCP model as the piece of data (or packet) traverses it. As you may recall, this process is known as encapsulation - where the reverse of this process is decapsulation.

One defining feature of TCP is that it is **connection-based**, which means that TCP must establish a connection between both a client and a device acting as a server **before** data is sent.

Because of this, TCP guarantees that any data sent will be received on the other end. This process is named the Three-way handshake, which is something we'll come on to discuss shortly. A table comparing the advantages and disadvantages of TCP is located below:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Advantages of TCP&nbsp;<br></b></td>
            <td style="border:2px solid #FFF"><b><span>Disadvantages of TCP</span><br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF"><span>Guarantees the accuracy of data.</span><br></td>
            <td style="border:2px solid #FFF"><span>Requires a reliable connection between the two devices. If one small chunk of data is not received, then the entire chunk of data cannot be used.</span><br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Capable of synchronising two devices to prevent each other from being flooded with data.<br></td>
            <td style="border:2px solid #FFF">A slow connection can bottleneck another device as the connection will be reserved on the receiving computer the whole time.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Performs a lot more processes for reliability.<br></td>
            <td style="border:2px solid #FFF"><span>TCP is significantly slower than UDP because more work has to be done by the devices using this protocol.</span><br></td>
        </tr>
    </tbody>
</table>

TCP packets contain various sections of information known as headers that are added from encapsulation. Let's explain some of the crucial headers in the table below:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Header<br></b></td>
            <td style="border:2px solid #FFF"><b>Desciption<br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Source Port<br></td>
            <td style="border:2px solid #FFF">This value is the port opened by the sender to send the TCP packet from. This value is chosen randomly (out of the ports from 0-65535 that aren't already in use at the time).<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Destination Port<br></td>
            <td style="border:2px solid #FFF">This value is the port number that an application or service is running on the remote host (the one receiving data); for example, a webserver running on port 80. Unlike the source port, this value is not chosen at random.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Source IP<br></td>
            <td style="border:2px solid #FFF">This is the IP address of the device that is sending the packet.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Destination IP<br></td>
            <td style="border:2px solid #FFF">This is the IP address of the device that the packet is destined for.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Sequence Number<br></td>
            <td style="border:2px solid #FFF">When a connection occurs, the first piece of data transmitted is given a random number. We'll explain this more in-depth further on.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Acknowledgement Number<br></td>
            <td style="border:2px solid #FFF">After a piece of data has been given a sequence number, the number for the next piece of data will have the sequence number + 1. We'll also explain this more in-depth further on.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Checksum<br></td>
            <td style="border:2px solid #FFF">This value is what gives TCP integrity. A mathematical calculation is made where the output is remembered. When the receiving device performs the mathematical calculation, the data must be corrupt if the output is different from what was sent.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Data<br></td>
            <td style="border:2px solid #FFF">This header is where the data, i.e. bytes of a file that is being transmitted, is stored.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Flag<br></td>
            <td style="border:2px solid #FFF">This header determines how the packet should be handled by either device during the handshake process. Specific flags will determine specific behaviours, which is what we'll come on to explain below.<br></td>
        </tr>
    </tbody>
</table>

Sources : https://tryhackme.com/room/packetsframes
