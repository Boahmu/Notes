The **T**ransmission **C**ontrol **P**rotocol (**TCP**). Potentially hinted by the name, this protocol is designed with reliability and guarantee in mind. This protocol reserves a constant connection between the two devices for the amount of time it takes for the data to be sent and received.

Not only this, but TCP incorporates error checking into its design. Error checking is how TCP can guarantee that data sent from the small chunks in the session layer (layer 5) has then been received and reassembled in the same order.

Let's summarise the advantages and disadvantages of TCP in the table below:
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
TCP is used for situations such as file sharing, internet browsing or sending an email. This usage is because these services require the data to be accurate and complete (no good having half a file!).

In the diagram below, we can see how a picture of a dog is broken down into small pieces of data (known as packets) from the "webserver", where the "computer" re-constructs the picture of the dog into the correct order.

![[TCP-protocol.png]]


Sources : https://tryhackme.com/room/osimodelzi
