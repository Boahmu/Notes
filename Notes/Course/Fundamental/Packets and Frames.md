#Fundamental
## What are Packets and Frames
Packets and frames are small pieces of data that, when forming together, make a larger piece of information or message. However, they are two different things in the OSI model. A frame is at layer 2 - the data link layer, meaning there is no such information as IP addresses. Think of this as putting an envelope within an envelope and sending it away. The first envelope will be the packet that you mail, but once it is opened, the envelope within still exists and contains data (this is a frame).

This process is called encapsulation . At this stage, it's safe to assume that when we are talking about anything IP addresses, we are talking about packets. When the encapsulating information is stripped away, we're talking about the frame itself.

Packets are an efficient way of communicating data across networked devices such as those explained in Task 1. Because this data is exchanged in small pieces, there is less chance of bottlenecking occurring across a network than large messages being sent at once.

For example, when loading an image from a website, this image is not sent to your computer as a whole, but rather small pieces where it is reconstructed on your computer. Take the image below as an illustration of this process. The dog's picture is divided into three packets, where it is reconstructed when it reaches the computer to form the final image.

Packets have different structures that are dependant upon the type of packet that is being sent. As we'll come on to discuss, networking is full of standards and protocols that act as a set of rules for how the packet is handled on a device. With the Internet predicted to have approximately 50 billion devices connected by the end of 2020, things quickly get out of hand if there is no standardisation.

Let's continue with our example of the Internet Protocol. A packet using this protocol will have a set of headers that contain additional pieces of information to the data that is being sent across a network.

Some notable headers include:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Header<br></b></td>
            <td style="border:2px solid #FFF"><b>Desciption<br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Time to live<br></td>
            <td style="border:2px solid #FFF">This field sets an expiry timer for the packet to not clog up your network if it never manages to reach a host or escape!<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Checksum<br></td>
            <td style="border:2px solid #FFF">This field provides integrity checking for protocols such as TCP/IP. If any data is changed, this value will be different from what was expected and therefore corrupt.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Source Address<br></td>
            <td style="border:2px solid #FFF">The IP address of the device that the packet is being sent <strong>from</strong> so that data knows where to <strong>return to</strong>.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Destination Address<br></td>
            <td style="border:2px solid #FFF">The device's IP address the packet is being sent to so that data knows where to travel next.<br></td>
        </tr>
    </tbody>
</table>


Sources : https://tryhackme.com/room/packetsframes
