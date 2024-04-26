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


# What is Web Hooks 
Whenever we make any changes to a GitHub repository, a notification email is automatically sent out to relevant recipients. So here is a quick gist explaining how we get these mails.

A WebHook is an HTTP-based callback function that allows lightweight, event-driven communication between 2 APIs. They are essentially HTTP callbacks that are triggered by specific events happening in another application or service. When an event occurs, the source application sends an HTTP POST payload to a predefined URL (the web hook URL) with relevant data about the event. The receiving application can then process this data and take appropriate actions.

In GitHub, web hooks are commonly used to trigger actions whenever certain events occur, such as pushing new code, opening an issue, or creating a pull request. This enables automation and integration with other systems.

When you make changes to a repository and a web hook is set up to trigger on those changes, here's a simplified explanation of how a mail can be sent:

1  Change in Repository : Let's say you push new code to a GitHub repository.

2 Web hook Triggered : GitHub detects this event (pushing new code) and triggers the web hook associated with that repository.

3 HTTP POST Request: GitHub sends an HTTP POST request to the web hook URL configured for that repository. This request contains information about the event, such as the type of event (e.g., push), details of the commits made, which branch affected, etc.

4 Receiving Server : The HTTP POST request is then sent to the URL endpoint specified in the web hook. The receiving application or service listens for incoming requests at this endpoint.

5 Processing the Payload : The receiving server processes the payload of the POST request. In this case, it might parse the information to understand what changes were made, who made them, and any other relevant details.

6 Sending Email : Based on the information extracted from the payload, the server can then trigger an action, such as sending an email. For example, it will compose an email notifying relevant folks about the changes made to the repository, including details like the commits pushed and the branch affected.

Web hooks provide a flexible and efficient way for applications and services to communicate and stay synchronised in real-time, enabling seamless integration and automation of workflows.

# UPI 
Recently UPI is launched in Europe and  people are amazed by seeing transaction through QR. They have never witnessed something like this either they pay through cash or through card. 
UPI is a great initiative launched by the government making our life easy. In milliseconds we can transfer money to others without nay hassle. 

Recently UPI is launched in Europe and folks are pretty amazed. It's all about QR codes which is new to them. Before this, they were used to paying with cash or card. UPI is a great initiative that has simplified our lives. With just a few clicks, money can be transferred to others within milliseconds, eliminating any unnecessary hassle. Here is a gist explaining how UPI works 


What is UPI ?
UPI is Unified Payment Interface. The main objective of the UPI was to take different payment interface which are exposed by bank it can be payment wallets or any transaction capable systems and unify them. This is the ideal phase to come in as a government and unify all the private entities creating different system having different behaviours, so that the user can have similar behaviour for any type of payment.

UPI Address 
The UPI address acts as a unique identifier for each user's bank account within the UPI system. It is similar to a username or an address in other network protocols. When a user wants to send money to another user, they only need to know their UPI address. Once they have set up their account, they can link their bank account to the app and create a Virtual Payment Address (VPA). It's like giving your money its own email address - it's a unique identifier that allows you to send and receive payments easily.
One of the objectives of UPI was to take the payments from banks and unify them( standardised). Through one address any transaction can be made to any other address regardless of the bank they have an account of.
They are not physical addresses but they are addresses which can referred to they are the identity of user.

So where are these addresses stored? All these virtual address belonging to one user are stored in a huge data store which is maintained and administered by NPCI. This registry acts as a lookup table, allowing the UPI system to route transactions to the correct bank accounts based on the recipient's UPI address. 

How Authentication works ?
So let's say i want to transfer money from my bank account to my friend's bank account how will UPI know that i am the real user how it will authenticate? So all of this happens through NPCI.
When a request is sent it needs to be authenticated. A signature is attached to the address such as a private key. The private key is a secret that NPCI maintains.

How does the receiver's bank know that the request is authentic ?
The sign-in request is made with the help of a pin. The pin number already contains details such as your bank card details. The pin is validated by the NPCI and the request is signed and then forwarded to the banks for further processing. So it goes like i have made the payment request it goes to my PSP then it goes to the NPCI and then to the receiver's PSP.

Instead of going directly to NPCI it is going to pass through sender's bank PSP to reduce the load otherwise If all the people directly connect to NPCI through direct requests the load will keep increasing.

 
How UPI handles billions of transactions with ease?
The users connect to their bank through the payment interface which is authenticated through a pin. This request is then forwarded to the NPCI which is followed by the bank to the money that needs to be transferred.
UPI is designed to be interoperable across different banks and payment service providers, allowing users to initiate transactions seamlessly regardless of their bank or payment app. This interoperability enhances convenience and accessibility, driving adoption and transaction volume.
UPI's architecture is designed to scale horizontally to accommodate a growing number of users and transactions. Its distributed nature allows for efficient load distribution and resource utilisation, enabling the system to handle increasing transaction volumes without significant performance degradation.

But what if NPCI goes down ?
All the request are passing through the NPCI either its from the sender side or from the receiver side .We can clearly see that NPCI is a single point of failure. If NPCI fails all the online transactions will go on pause.

Another place where NPCI comes in is suppose i want to transfer money from my account(Account A) to my friend account(Account B). How my bank will know what B is? So here comes NPCI it works as a Central Entity similar to DNS and it will tell me where does b point to.

How does the UPI system work exactly?
The UPI system consists of four main components: the issuing bank, the acquiring bank, the NPCI, and the UPI app.
1. The issuing bank or the sender's bank is the bank that holds the user's account and issues their debit or credit card.
2. When a user initiates a payment using their UPI app, the issuing bank processes the payment request and transfers the funds to the recipient's bank account.
3. The acquiring bank or the receiver's bank is the bank that holds the recipient's account and receives the payment from the issuing bank.
4. It then credits the funds to the recipient's account.
5. The NPCI comes into picture for the routing purposes of the virtual address.
6. It receives the payment request from the issuing bank and routes it to the receiver's bank.
7. It also handles the settlement of funds between the banks and ensures that the transaction is completed successfully.
8. The UPI app is the interface that users interact with to initiate and complete payments.

# Gomail
There are times when we have to integrate mailing service to our product. Timely notifying our customer is one of the most important thing. If you are working with go and want to integrate notification service to your product you can use Gomail.

Integrating mailing services into your product is crucial for timely customer notifications. If you're working with Go and seeking a seamless solution, look no further than Gomail.
Gomail simplifies email sending in Golang with an easy-to-use API for crafting emails with attachments and managing recipients. It simplifies the way you handle emails, making communication more efficient and effective.

Gomail supports:
- Attachments
- Embedded images
- HTML and text templates
- Automatic encoding of special characters
- SSL and TLS
- Sending multiple emails with the same SMTP connection

Upgrade your email experience today with Gomail – the ultimate solution for efficient inbox management. Ready to go with Golang? Explore Gomail now and revolutionize the way you communicate!
# Load Balancer vs reverse proxy vs api gateway 

Apis Gateways, Load Balancer and Reverse Proxy Servers  are essential components in modern software architecture. Each serves a specialised function, enhancing the performance, security, and scalability of web applications. 