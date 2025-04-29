---
title: "Software Architecture Patterns"
date: 2025-04-29T20:27:25+07:00
draft: false
---

# Introduction
- It is common for programmers to create software without careful preparation.
- This sometimes makes the software difficult to maintain and develop when it has already been made.
- Therefore, before making a large software, one of the things that must be done is to choose the architecture that will be used.
- In choosing a software architecture, we must understand its advantages and disadvantages, so that it helps in the creation of the software to be carried out.

## Software Architecture Patterns
- Architecture Patterns are a collection of architectural styles in software development.
- There are many Architecture Patterns, and each pattern has its own advantages and disadvantages. In Architecture Patterns there is no right and wrong, but whether it fits or not.
- Programmers need to know about this material so that they can determine what pattern to use when creating software.

## Purpose of Architecture Patterns
- Each Architecture Pattern has characteristics such as easy to develop, scalable and easy to maintain.
- The hope is that by using the right Architecture Pattern when making software, the results of the software we make will be easy to develop in the future.


# Architecture Classification
- Software Architecture Patterns are broadly divided into two classifications, Monolithic and Distribute.
- Monolithic is a single deployment unit or runs in one application.
- Distributed is multiple deployment units, usually consisting of several applications.

## Monolithic Architectures
- Monolithic Architecture is generally very simple compared to Distributed Architecture.
- Monolithic application design is simpler and easier to implement.
- Applications that use Monolithic Architecture will be very fast to build and distribute.
![Monolithic Architectures](https://i.imgur.com/YQkdFLv.png)

## Distributed Architecture
- Distributed Architecture usually consists of several applications working simultaneously, in contrast to Monolithic applications which are only one application.
- Usually in Distributed Architecture, each application unit is called a Service.
- Distributed Architecture development is more complex than Monolithic Architecture, but offers advantages such as fault tolerance, for example when one service fails, other services can still run normally.

![Distributed Architecture](https://i.imgur.com/CAHCQzg.png)

## Which one to choose?
- When making applications, sometimes we are confused about whether to use Monolithic or Distributed architecture?
- If the application we are going to create is simple or still unclear in terms of business requirements, it is highly recommended to use Monolithic, because it is easy to create.
- But if the application we are going to make is very clear, and also requires good scalability, including good fault tolerance, then we can use Distributed architecture.

# Architecture Partitioning
- In addition to the classification of monolithic or distributed, software architecture can also be seen in its partition structure.
- Software architecture, be it monolithic or distributed, can be partitioned based on technical or domain.
- Partitioning by structure can be used in monolithic or distributed.

## Technical Partitioning
- Technical Partitioning architecture divides the components in the system or application technically.
- An example of a classic architecture that is often used is Layered (N-Tier) Architecture.
- In Technical Partitioning, the components in the system are grouped technically, for example :
	- Presentation Layer is the component that handles the user interface.
	- Business Layer, a component that handles business logic and rules.
	- Persistence Layer, a component that handles interaction with the database system.
	- Database Layer, a component for storing data.

![Technical Partitioning](https://i.imgur.com/jFaaqq7.png)

## Domain Partitioning
- In contrast to Technical Partitioning, in Domain Partitioning, the division of the component structure in the system is grouped based on the Domain / Feature / Department in business.
- This means that all Technical Partitioning such as Presentation, Business Logic, Persistence, are combined in the system domain.
- Domain-based system partitioning has been popular since it was introduced in a book titled “Domain Driven Design” by Eric Evans.

![Domain Partitioning](https://i.imgur.com/UA9tXUz.png)

## Which one to choose?
- Both Technical and Domain Partitioning have advantages and disadvantages, but personally I recommend using:
- Technical Partitioning when the application to be created is simple and not complex, and also when the number of development team members is not too large.
- Domain Partitioning when the application to be created is complex and there are many application features. And it is suitable when the development team members are many team divisions based on the type of domain.

# Layered Architecture
- Layered Architecture is also known as N -Tier Architecture.
- This architecture is one of the standard architectures for most applications, where applications are divided technically.
- Because this architecture is very widely known by software developers, it makes this architecture one of the most widely used choices.

## Components of Layered Architecture
- Layered Architecture is technically divided, therefore the components in Layered Architecture are the same as Technical Partition.
- On average, many divide into 4 layers, Presentation Layer, Business Layer, Persistence Layer and Database Layer. However, it is possible to have more layers when the application is very complex.

![ayered Architecture Components](https://i.imgur.com/JrUPelT.png)

## Tasks of each layer
- Each layer in Layered Architecture has its own tasks.
- The Presentation Layer is responsible for handling all user interfaces.
- The Business Layer is responsible for executing the request logic or business rules that match the request.
- The Persistence Layer is responsible for interacting with the database to perform data processing in the database.
- Database Layer is responsible for storing all application data.

## Layers of Isolation
- In Layered Architecture, each layer is isolated, and the direction of communication is only with the layer below or above it.
- That is, for example, when the Presentation Layer wants to retrieve Product data, the Presentation Layer will send a request to the Business Layer, then it will retrieve the data to the Persistence Layer and then enter the Database Layer.
- It is not recommended to directly access from the Presentation Layer directly to the Database Layer.

## Example
- After knowing how Layered Architecture works, we can easily describe the flow that must be made when creating an application.
- For example, we want to display the Product page, but in the Product page we also want to display the Seller data.
- Then we can create an application flow as in the next diagram.

![Layered Architecture Flow Example](https://i.imgur.com/UbjXlTr.png)


## Considerations
- Layered Architecture is one of the most widely understood and used architectures.
- Use Layered Architecture if we are still confused about what architecture to use, because this is a good architecture to start the application.
- But don't use Layered Architecture when the division of teams in the company is based on domains, it is more suitable to use Distributed Architecture which we will discuss in the next materials.

# Model-View-Controller Architecture
- Model View Controller (MVC) Architecture is one of the most popular architectures when creating the Web.
- MVC is similar to Layered Architecture, only the layers are different.
- In MVC, the center of interaction between layers is usually done by the Controller.

![Model-View-Controller Architecture](https://i.imgur.com/TSq4w4X.png)

## Tasks of Each Layer
- In MVC, each layer has its own tasks.
- Controller is the layer responsible for receiving requests and executing the logic and business rules that occur in the application.
- Model is the layer responsible for representing the data in the database and also interacting with the database.
- View is a layer that contains templates for displaying web pages.
- Database is a layer for storing application data.

## Example
Suppose we have a web where there is one web page that needs to display wishlist data. On that page, in addition to the wishlist data, we also have to display the product details contained in the wishlist.

![Example of Model-View-Controller Architecture](https://i.imgur.com/7Fh4CWw.png)

## Considerations
- MVC is the first choice when we want to create a web application.
- Many web frameworks automatically use this architecture such as Laravel, NestJS, Rails, Django, and others.
- But when we create a RESTful API for example, we are not obliged to follow the MVC rules, because usually we don't need a View layer. In this case, we can just combine this MVC architecture with Layered Architecture.

# Hexagonal Architecture
- One of the problems when using Layered Architecture is that changes in the type of technology used, will complicate development.
- For example, when we have to change the database technology used, there will automatically be a major overhaul of the Persistence Layer and Database Layer program code, which may cause an overhaul of the Business Layer as well.
- Hexagonal Architecture is an architecture developed from Layered Architecture, but better when handling technological changes that occur.
- Hexagonal Architecture is also known as Port & Adapter Architecture.

![Hexagonal Architecture](https://i.imgur.com/g98YhPu.png)

## Ports and Adapters
- Hexagonal Architecture was actually introduced under the name Pert & Adapter Architecture, but is currently more popular as Hexagonal Architecture.
- Port is a technology-agnostic OOP (Object Oriented Programming) Interface, which is used by application code to communicate with other parties.
- An Adapter is the part that interacts directly through the Port, and uses a predefined technology.

![Port and Adapter](https://i.imgur.com/AAV5hSj.png)

## Application Layer
- In Hexagonal Architecture, the Application Layer will contain business logic and rules, where the code created will interact only with the Port, without knowing which Adapter is used.
- This is to be technology agnostic, so that when the Adapter is changed, the Application Layer does not need to change.
- In addition, within the Application Layer, there is a Domain Layer, which contains a representation of the application domain data.
- The Driving part, usually called User Interface/Transport Layer/Gateway, is the source of incoming requests to the application.
- The Driven part, usually called Infrastructure/Data Source/External Interfaces, is the target of data leaving the application.

![Application Layer](https://i.imgur.com/gBwZEBA.png)

## Clean Architecture
- Nowadays, Clean Architecture is also famous.
- Don't be confused if you have to choose Hexagonal Architecture or Clean Architecture.
- Actually Clean Architecture is not much different from Hexagonal Architecture, even the author of the Clean Architecture book has explained that one of the Clean Architecture references is from Hexagonal Architecture.

## Example
- Suppose we have an online store Web application, where we will create a payment page.
- Where when making a payment data besides being stored in the database, it will be sent to the Payment Gateway.

![Example of Hexagonal Architecture](https://i.imgur.com/hu9jRuY.png)

## Considerations
- Hexagonal Architecture is a good architecture to use when we are going to create complex applications and so that the application is technology agnostic so that it can be easily replaced.
- However, developing Hexagonal Architecture is not as easy as Layered Architecture, so if the developer is not familiar with Hexagonal Architecture, it can be constrained during the development process.

# Microkernel Architecture
- Microkernel Architecture is very flexible and extensible, so developers can easily add features to applications in the form of extensions or plug-ins, without fear of disrupting the functionality of the application itself.
- Therefore, Microkernel Architecture is also often referred to as Plug-in Architecture.
- Microkernel Architecture is widely used in desktop-based applications, for example Visual Studio, Eclipse, and others, where there are many extensions or plug-ins available for these applications.

![Microkernel Architecture](https://i.imgur.com/tM4zGf2.png)

## Topology
- In Microkernel Architecture, there are only two layers, Core System and Plugin Modules.
- Application logic in Microkernel Architecture is usually placed in Plugins, so this architecture looks like Hexagonal Architecture, but it is not.
- In Hexagonal Architecture, application logic is placed in the application, while in Microkernel Architecture, application logic details are in each respective Plugin.

## Considerations
- Microkernel Architecture is very popular when creating plugin-based Desktop applications, such as Visual Studio, Eclipse, IntelliJ IDEA Ghkan like Browser.
- Use Microkernel Architecture if we really want to create a Plugin-based application.
- One of the advantages of Microkernel Architecture is that other people can contribute to creating Plugins for our applications.

# Client-Server Architecture
- Client-Server Architecture is one of the Distributed System Architectures that is widely known and used.
- This architecture is very simple, where there are Client and Server applications that interact with each other.
- Usually communication between Client and Server uses a TCP/IP network, although it is possible to use other networks such as UDP.

![Client-Server Architecture](https://i.imgur.com/NWSKhhf.png)

## Topology
- Client is an application used by users and interacts directly with users, Usually Client applications are applications based on user interfaces, be it Web, Desktop or Terminal-based, Client will send all requests requested by the user to the Server application
- Server is the core of the application, where all logic and business rules are carried out on the Server, Server will execute commands requested by the Client, and return the requested data to the Client
- The advantage of using Client-Server Architecture is that we can run many Client type applications using only one Server application

## Example
- Client-Server Architecture is an architecture that is currently widely used, maybe even unconsciously, we have used this architecture.
- When we create a Mobile application and then connect to the RESTful API, it is actually a Client-Server Architecture.

![Client-Server Architecture Example](https://i.imgur.com/mhQdLau.png)

## Considerations
- When we want to create an application, which wants to separate the Client application, or even create many types of Client applications, then the Client-Server architecture is very suitable for use.
- However, if we want to create a standalone application, do not need to store data on the Server, then we do not need to create a Client-Server application, for example an editor application for Photos, Videos and the like.

# Master-Slave Architecture
- Master-Slave Architecture is an architecture where applications can distribute all their work to other applications.
- The application that commands the application is called the Master, and the application that receives the command is called the Slave.
- Just like the Client-Server Architecture, usually the Master and Slave communication uses a TCP/IP network.

![Master-Slave Architecture](https://i.imgur.com/ISP00p4.png)

## Topology
- Usually, all requests to the application will go through the Master application.
- All work received by the Master will usually be distributed to the Slave application.
- That way, work can be faster because it can be done by many Slave applications.
- In the diagram, we only create 3 Slave applications, but in reality, there is no limit to the number of Slave applications.

## Fault Tolerance
- One of the advantages of Master-Slave Architecture is Fault Tolerance, where when an error occurs that causes one of the Slave applications to die, the work can still be done by other Slave applications.
- Likewise, when a problem occurs that causes the Master application to die, one of the Slaves will automatically be promoted to become the new Master.

![Fault Tolerance](https://i.imgur.com/cQ3Accc.png)

## Master-Master Architecture
- One of the disadvantages of Master-Slave Architecture is that all requests must go through the Master application, so when there is a delay in the Master application, all users will automatically feel the impact, even though the Slave application may not be slow.
- In such cases, there is also Master-Master Architecture, which is an improvement on Master-Slave Architecture.
- What distinguishes Master-Master Architecture is that all applications can run as Master, so they can receive requests from users independently
- And because all applications are Master, each application can send requests to other applications, when for example the application has handled too many requests from users.

![Master-Master Architecture](https://i.imgur.com/kNpvSUc.png)

## Replication
- What needs to be remembered in Master-Slave/Master-Master Architecture, usually data in the application is always replicated/duplicated to all Slaves/Masters.
- This is so that the data is always the same, so that the work done by all Slave/Master applications will always be consistent.

## Example
- Master-Slave/Master-Master Architecture should not be used when creating information system applications, this architecture is often used when we create stateful applications! (storing data) such as database systems.
- Almost most database system applications such as MySQL, PostgreSQL, MongoDB implement the Master-Slave Architecture
- Or like the Elasticsearch and Cassandra database system applications, which use the Master-Master Architecture.

## Considerations
- Use the Master-Slave/Master-Master architecture when we want to create a stateful application! (save data)
- If we create a stateless application (do not store data), then it is recommended not to use this architecture.

# Peer-to-Peer Architecture
- Peer-to-Peer Architecture is an architecture that is almost similar to Client-Server Architecture.
- However, in Peer-to-Peer, all applications can be Clients and Servers simultaneously.
- Usually the application logic will be centralized in the Server application, in Peer-to-Peer, the application logic is not centralized in one application, all applications can be Servers and Clients at the same time.

![Peer-to-Peer Architecture](https://i.imgur.com/QIkp4fF.png)

## Topology
- In Peer-to-Peer Architecture it seems simple, but in fact this architecture is very complex.
- Each Peer can be a Client that makes requests to other Peers, or even become a Server at the same time by sending responses to other Peers.
- Therefore, creating a Peer-to-Peer Architecture application is very complex because each Peer must know when there is a new Peer, because in reality new Peers can come and go at any time.

## vs Master-Master Architecture
- What is the difference between Peer-to-Peer Architecture and Master-Master Architecture?
- In Peer-to-Peer, each Peer can be a Client or Server.
- While in Master-Master, each Master is a Server, usually the Client is a separate application and connected to the Master-Master with a Client-Server architecture.

## Example
- Peer-to-Peer is widely used for file sharing applications such as Torrent, for example, where everyone can share files, while requesting files from other Peers in their Torrent network.
- In addition, Peer-to-Peer is also often used in Cryptocurrency where all data is distributed across all Peer applications to keep data safe because to change data, we have to change all data in all Peers, and that is very difficult to do.

## Considerations
- Peer-to-Peer Architecture may look very attractive, but this is a type of architecture that is rarely used, except in types of applications that require decentralized logic.
- Peer-to-Peer Architecture is also a very scalable architecture, because it is difficult for system failures to occur because all logic is distributed across all Peers
- The disadvantage is, because we cannot be the quality of resources in each Peer, so, it is likely that the quality and speed of the application cannot be maintained properly, especially if the Peer runs on hardware with insufficient resources.

# Microservices Architecture
- Microservices Architecture is a type of architecture that is currently widely used by many people. However, this architecture is not a simple type of architecture, it is a complex type of architecture.
- In Microservices Architectures, the system will be created in a number of small applications or called Services, and used to complete certain specific tasks only.
- In addition, in this architecture, each Service will be deployed and run independently
- In this architecture, it is not strange if a system has hundreds or even thousands of independent Services, this is because each Service does have its own task.

![Microservices Architecture](https://i.imgur.com/QHtOgoT.png)

## Topology
- Usually in Microservices Architecture, each Service will run independently and have its own database, not sharing the database with other Services.
- Usually, each Service will not be exposed openly to users, but users will go through the API Gateway, which is an application that acts as a gateway to receive requests and forward them to the intended Service.
- Because each Service has its own tasks, it is not uncommon for the databases used to be different, this is because usually the Service will use a database that is in accordance with the tasks that must be done.

## Bounded Context
- As previously explained, each Service will have and manage its own database.
- This means that the database and table can only be accessed by the Service
- For example, when we have a Service that is used to manage Seller data, then the Seller Service can only manage the Seller data.
- This concept is called Bounded Context, which was introduced by Eric Evans in the Domain-Driven Design book.

![Bounded Context](https://i.imgur.com/4e1CUGn.png)

## Communication Between Services
- With Bounded Context, it means that no one can access the Seller database directly from another Service except the Seller Service.
- If there is another Service that requires Seller data, then the other Service must request Seller data from Seller Service, using a predetermined communication method, for example RESTful API (Client-Server Architecture).

## Example
- On the online store web page, we want to display detailed Product data.
- However, on the Product detail data page, in addition to Product information, we also want to display data from the Seller who sells the Product.
- In this case, we can take Product data to Product Service, then Product Service requests Seller data from Seller Service.

![Example of Microservices Architecture](https://i.imgur.com/8wFM0gc.png)

## Supporters
- To use Microservices Architecture usually does not only involve the programmer team.
- There are many things that must be changed such as infrastructure and product/business teams.
- This is because usually in Microservice Architecture, the division of Services will be done based on the business domain, so it is not easy to create small applications.

- In some cases, errors in creating Service types can complicate the development team, therefore Domain Experts or those who are experts in their fields in terms of business are needed.

## Considerations
- Microservice Architecture is usually used in large companies with large development teams, this is because this architecture requires a lot of work other than application creation, such as infrastructure, automation, deployment and others.
- Do not use this architecture if the team is still small, we can start with Monolith Architecture and Layered Architecture, if it is time to need rapid team scaling, we can consider using Microservices Architecture.

# Event-Driven Architecture
## Microservices Architecture Problems
- With the increasing use of Microservices Architecture, finally there is one problem that is often experienced by users of this architecture, namely the dependency between Services.
- For example, in the previous case, when the Seller Service has a problem, for example it dies, then we cannot see the Product data, this is because the Product Service needs to call the Seller Service when it wants to display Product data.

## Event-Driven Architecture
- Event-Driven Architecture is an architecture that uses Async Process to communicate with each other between Services.
- Usually, in this architecture, the Service will send every data change that occurs in the Service to an application called Message Broker in the form of Event data.
- We call the sender of Event data Producer/Publisher.
- The service that needs its Event data will take the data from the Message Broker.
- We call the recipient of Event data Consumer/Listener.

![Event-Driven Architecture](https://i.imgur.com/KFTW5Ec.png)

## Duplicate Data
- As we already know, in Microservices Architecture there is a Bounded Context rule, where data can only be accessed by the Service itself.
- In the case of Event-Driven Architecture, because we will not call Sync to Other Services (such as using API Call), then usually the Service will consume event data and duplicate the data needed in the Service database.
- In the previous case, for example, the Product Service will consume Seller Event data, then save the Seller data to the Product database as duplicate data.

![Event-Driven Architecture Example](https://i.imgur.com/fIO65AG.png)

## Considerations
- Event-Driven Architecture is currently widely used, because of the problems that occur in Microservices Architecture, but it should be noted, there are also consequences that occur when we use Async Process.
- In the previous case, we must ensure that the Seller Event data is received properly by the Product Service, if it fails automatically the Seller data will not be in the Product database.
- Async Process will also cause the process to be delayed, therefore sometimes users do not receive results in real time, because the Async Process has not finished
- When a problem occurs in the Async Process, searching for problems is more difficult than the Sync Process in the Microservices architecture.

# Pipeline Architecture
- Pipeline Architecture is an architecture that is closely related to Data Stream.
- In some cases, sometimes we encounter data sources that come in non-stop, for example user activity log data.
- In cases like this, storing data in a database will be very difficult to process, because incoming data is usually in large quantities and continuously.
- Pipeline Architecture is an architecture where we utilize Message Queue like Message Broker as a place for data flow, and we can focus on creating Filters to process the data.

![Pipeline Architecture](https://i.imgur.com/C4PQC3i.png)

## Topology
- In Pipeline Architecture, the main focus is the Filter process for messages.
- There is no rule for the Filter process whether it must be in the same or different applications, so there is no right or wrong.
- Filters are usually processes that are carried out from receiving input data, processing data, and ending with producing output data.

## Cloud Function
- This Pipeline Architecture is now very popular in Cloud Providers such as Google Cloud or Amazon Web Service.
- These Cloud Providers now have features for Cloud Function, which can be used as Filters in Pipeline Architecture.
- One of the advantages of using Cloud Function, we only need to pay when the Filter processes data.

## Data Pipeline
- Pipeline Architecture is also often used in data processing, or often known as Data Pipeline.
- In Data Pipeline, there is usually a Source (data source), Destination (final destination of data), and also Processing (data processing).

![Data Pipeline](https://i.imgur.com/DnpaHg3.png)

## Example
- We want to create a report on the number of daily visitors to our website, where in the report, we can see the number of visitors based on the country of the visitor
- In this case we can use Pipeline Architecture.
- Starting from every visit data to our website, we will send it as an event to the Message Broker, then we will create a filter, from a filter to detect the IP address, a filter to get the country based on the IP, and a filter to group by country.

![Example of Pipeline Architecture](https://i.imgur.com/1ofWLgu.png)

## Considerations
- Pipeline Architecture is a very suitable architecture when we want to do very long and gradual processing.
- Pipeline Architecture can take a very long time to process, depending on how long the Filter is, therefore it is not suitable for doing work that requires real time.

# Space-Based Architecture
## Triangle-Shaped
- In certain cases, there are types of applications that usually have unexpected visitor traffic, such as flash sale websites, ticket sales or bidding.
- The architectures that we discussed earlier, we can actually use to create these types of applications, but in certain cases, sometimes we end up getting triangle-shaped problems.

![Triangle-Shaped](https://i.imgur.com/tyOQZcQ.png)

## Triangle-Shaped Topology
- Triangle-Shaped Topology is a condition where we do scalability by increasing the number of applications when there is a slowdown in our system.
- In cases when we create a website, increasing the number of web servers is usually very easy, because it only provides a website user interface, then usually the slowdown will move to the Backend server, for example in the RESTful API.
- Next, we will usually add the number of RESTful API servers, but not as many as Web Servers, because usually the application is heavier and requires more resources, then the slowness will move to the Database.
- In cases like this, adding servers to the database is not easy, not as flexible as Web Servers and RESTful APIs, because the database is a stateful application (storing data).

## Space-Based Architecture
- Space-Based Architecture is an architecture specifically designed for cases like this, where we need good scalability and performance for the application.
- Space-Based Architecture solves this problem by removing the database from the application transaction process and replacing it with shared memory (Data Grid).

- High Scalability is achieved by connecting all applications to shared memory (Data Grid) synchronously, and asynchronously the data in shared memory will be synced to the database,

![Space-Based Architecture](https://i.imgur.com/vA0NYSq.png)

## Topology
- In Spaced-Based Architecture, the application we create is called a Processing Unit.
- In the Processing Unit, there is our application logic and also contains the In Memory Data Grid which is used as a replacement for the Database.
- Usually there is a Data Replication Engine which is used to synchronize all data in the In Memory Data Grid for all Processing units assisted by the Data Grid Cluster.
- If we want, we can async save the changes that occur in the In Memory Data Grid to the Database.

## Data Grid Example
- Usually Data Grid does not need to be created manually by application developers, just like the Database, we can use the Data Grid application that is already available, for example.
- Hazelcast.
- Apache Ignite.
- Oracle Coherence.
- And others.

## Considerations
- Spaced-Based Architecture is a very complex solution to achieve excellent scalability.
- However, although this solution is very good, sometimes this solution is not the best, we must see many considerations when using this architecture.
- For example, if our data is too large, it will be difficult to use this architecture, because all data must be moved to memory, which certainly requires a very large cost.
- Because of the complexity and high cost of this solution, we must also consider the costs that must be incurred to use this architecture.

# Conclusion
- Software Architecture Patterns are not a rigid solution where we have to choose one.
- We can combine several Patterns that suit our needs.
- For example, we can combine Microservices and Event-Driven, or Monolith with Layered, Microservices with Layered, and so on.
## Other Software Architecture Patterns
- This class does not discuss all existing Software Architecture Patterns, only those that are often used.
- Technology, especially in Software Design, is always evolving over time, in the early 2000s not many people used Microservices, but now almost all large companies use them.
- There are still many patterns that have not been discussed, and can be studied independently, such as: Onion Architecture, Screaming Architecture, Event-Bus Architecture, and many others.

---
Source:
{{< youtube Ix09qfew6oA >}}