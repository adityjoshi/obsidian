# What is Process ?
We know how a **Process** moves using schedulers, from the hard disk to RAM and then to the CPU. But what actually is a Process ?

A process is basically a program in execution. It is more than the program code, which is sometimes known as the **text section**. To put it in simple terms, we write our computer programs in text files, which, when run, turn into processes that carry out all the tasks the programs specify.

A process generally also includes the process stack, which contains temporary data (such as function parameters, return addresses, and local variables), and a data section, which contains global variables. A process may also include a heap, which is memory that is dynamically allocated during process run time.

A program for which a process is created is called **Passive Entity**. A file containing a list of instructions stored on disk (often called an executable file). In contrast, a process is an **Active Entity**, with a program counter specifying the next instruction to execute and a set of associated resources.

 A process itself can be an execution environment for other code.The Java programming environment provides a good example. In most circumstances, an executable Java program is executed within the Java virtual machine (JVM). The JVM executes as a process that interprets the loaded Java code and takes actions (via native machine instructions) on behalf of that code.
 For example, to run the compiled Java program Program.class, we would enter java Program. The command java runs the JVM as an ordinary process, which in turns executes the Java program Program in the virtual machine. The concept is the same as simulation, except that the code, instead of being written for a different instruction set, is written in the Java language.

I keep on sharing my learning and knowledge, so if it sparks your curiosity, then follow along. And as always, it will be no-fluff; just engineering. 

# What is switch (internal working)
A switch is a networking device used to connect multiple devices within a local area network.
It works on Data Link layer(Layer 2). It is responsible for filtering and forwarding the packets between LAN segments based on MAC Address. Here's a breakdown of how switch works:

Broadcast Address Handling: A switch will check if it has the broadcast address of host in the table if not it will register it.Then it will check if it has the MAC address of the destination. If not it will flood frame.

Forwarding: It happens when the switch has entry for the frame's destination MAC address. That frame will be forwarded only out the port indicated by the MAC table.

Flooding: It occurs when the switch has no entry for the frame's destination MAC address in its MAC table. With flooding, the frame is sent out to the every port except the port the frame come in.

Filtering: It happens when the source and destination MAC address are located off the same port. The frame is simply dropped. 

These techniques allow a switch to efficiently manage traffic within a local area network by selectively forwarding packets based on MAC addresses, reducing unnecessary network congestion.

I keep on sharing my learning and knowledge, so if it sparks your curiosity, then follow along. And as always, it will be no-fluff; just engineering. 

# What is any casting ?

I recently went through Dukkan's transition from the cloud to Bare Metal . During this, I was fascinated by how Dukkan's servers work on the same IP address. So here is a quick gist explaining how all the servers can run on the same IP address. ⚡️

Anycasting is the networking technique that allows multiple servers, usually geographically dispersed to advertise same ip address. Based on the location of the user request, the anycast routers send it to the server in the network based on a least-cost analysis that includes assessing the number of hops, shortest distance, lowest transit cost, and minimum latency measurements to optimize the selection of a destination server.

Efficient Traffic Routing: Anycast uses the Border Gateway Protocol (BGP) to route incoming traffic to the nearest server based on network proximity. This means that when a user requests data from an Anycast IP address, the network automatically directs their request to the closest server in terms of routing distance. This optimization reduces latency and improves response times.

**Enhanced Reliability**: If one server goes down or experiences issues, the network seamlessly redirects traffic to the next nearest server. This minimises downtime and ensures continuous service availability, even in the face of hardware failures or network disruptions.

Optimised Content Delivery: CDN service providers use Anycast to efficiently distribute content for faster network access in CDN networks. An anycast-enabled CDN assigns the same IP address to multiple edge servers, relying on IP routing to deliver requests to the servers that are nearby in the network to the clients originating the requests. By strategically placing servers closer to target audiences, CDNs reduce latency and accelerate content delivery, resulting in faster website loading times, improved streaming quality, and enhanced overall user satisfaction.

Let's consider an example of a web service with three servers deployed using anycasting: two in the USA (New York and Los Angeles) and one in India (Mumbai). These servers are all advertising the same anycast IP address.

Now, if one of the servers in the USA, let's say the New York server, goes down, here's what happens:
• When a user tries to access the service, their device sends a request to the anycast IP address.

• The network routers determine the best path to reach this anycast IP address based on routing metrics. Let's assume that the user's request initially travels through routers that determine that the shortest path (in terms of network distance) is to the Los Angeles server.

• The Los Angeles server receives the request and processes it, serving the user's needs.

So, in this scenario, because the New York server is down, users are automatically redirected to the Los Angeles server, which is still operational and can serve their requests. 

I keep on sharing my learning and knowledge, so if it sparks your curiosity, then follow along. And as always, it will be no-fluff; just engineering. 
