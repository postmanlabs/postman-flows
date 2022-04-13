---
icon: home
label: Postman Flows
---
### A visual programming language for APIs 
[!embed](https://www.youtube.com/watch?v=4Yr9CG8Pp14)

Postman Flows is an API workflow builder that lets you connect APIs logically. Use Flows to chain requests, handle data and create real world workflows right in your Postman workspace.

Postman Flow is a beta feature and is available to members of all plans **_for free_**. Head on to [Postman web app](https://go.postman.co/) or use the latest version of [Postman desktop app](https://www.postman.com/downloads/     ) to start creating Flows.

## Fundamentals
There are just **4 fundamental** concepts that you need to know before starting
to use flows.

![](static/concepts.png)

+++ Block
A *block* is something that the system is capable of doing. In the above example the block is capable of Sending a HTTP request.

To be able to send a request, the block might need some information like variable. Once its firing pattern is met, it starts processing, and gives some information like the response as output.

The block is a single black-box process which  when executed figures out how to send a request by itself. Additionally, a flow program can itself be considered as a block.

Note: A block is not a function but a process
+++ Connection
A connection is a construct by which data from one block can be transferred to another.

They can be imagined as FedEx like courier service that transfer mail or information from source to destination.

Connections do not in any way store data, they just transmit.
+++ Messages
A Message is a packet of data. More specifically, it is a pointer to a discrete bundle of data which travel together from one block to another.

It is also possible to club together multiple pointers using special markers called as brackets, in which case they behave like data streams.
+++ Signal
A signal is a special kind of connection that does not carry data but a signal which is triggered when a block completes processing.

All blocks would start executing as soon as their firing pattern has been met. Very often their execution happens in parallel, but there may be requirements to halt the execution of block until other blocks have completed their execution. In such cases the signal can be used to pause execution and synchronize. 

Signal ports also respect stream, so they don’t turn on until the entire stream is processed.
+++

## Getting Started
* [The Interface](getting-started/interface.md)

## Tutorials
* [Level 1 - Sending a Request](tutorial/sending-a-request.md)
* [Level 2 - Chaining Requests](tutorial/chaining-requests.md)
* [Level 3 - Working with Access Tokens](tutorial/working-with-access-token.md)
* [Level 4 - Loops & Lists](tutorial/loops.md)

## Contribute

Flows is in beta and we're building it actively. We would love to hear what you're making with flows, what issues you face while doing so, and what new you'd like to see in Postman Flows.

Head on over to the [discussions page](https://github.com/postmanlabs/postman-flows/discussions) to start or join a conversation
