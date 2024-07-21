#System design 999

## Context

- This document is my take on concepts around system design
- This is in no ways a doucment only meant for interview purposes
- Aim is to educate budding engineers and wannabe architects on concepts around system design, but helps with interviews too
- Attempt is to highlight patterns instead of specific technologies ro build a mental model of the concept
- Mainly technology agnostic but in some cases technologies are used for example and illustration purposes
- Concepts are generally post 2020. Any references to previous architectures is just for comparison purposes

## A few concepts unique to this article

**H**istorically a lot of names have been used to call different components i prefer using a 
few terms which have become most popular post 2020 times

- **Client** - Represents a UI component visible to the end user, could be a mobile App or UI using React js, etc
- **Compute**- Represents back end processing, such as services, cache and queue, generally of no significance to the end user
- **Persistence** - Something which can store data for long term (Basically databases)


## Abstract concepts

### The holy SixTrait of technology

Any technology uses underlying infrastructure and runtime
Any logical component (Refer below section [Worfklows and components]) needs the below to be able to do something meaningful

![The holy SixTrait of technology](https://github.com/saurabh-herwadkar/system-design-999/blob/main/images/The%20holy%20SixTrait%20of%20technology.png)



**Hardware **

- Processor - CPU or GPU
- Memory - RAM
- Storage - SSD or HDD
- Input/Output (IO) - Network cards, Display cards

**Software**

- Operating system | Kernel - Some variant of Linux or Windows which gives access to the above 4 mentioned hardware components via 
- Runtime - The underlying installed programmin softwares - For example Python 3.9, PIP and other python libraries

  To add to the above we have the code base which executes some bsuiness functionality and cannot run
  without the blessings of the above mentioned "Sixtrait"


### Concept , features and tools

**W**henever i work with an engineer to discuss an idea i use the above three key words to helpp build a mental model

- **Concept** - Understand the underlying concept at an abstract level in a technology agnostice manner
- **Features** - What are the properties and features of that concept
- **Tools** - What are the industry grade tools which help implement this concept

To take the example of a queue mechanism 

- **Concept** - Queue - A mechanism where a publisher can send messages. A consumer can consume these messages asynchronously
- **Features** -Publisher | Subscriber | Asynchronous | Decoupled | FIFO queues | Dead letter queues | Message retention
- **Tools** - Active MQ, Rabbit MQ, AWS SQS

### Worfklows and components

**N**ow for this definition I have leaned a bit on AWS take on the above two terms

[https://aws.amazon.com/what-is/workflow/]

A **workflow** is a business process which achieves a business objective. 
- It brings value
- It surely incurrs a cost
- Yet reduces overall costs
- Increases profits

A **component** is a logical unit of software
Many such **components** work together to complete a **Workflow**

For example a UI client, microservice and database **components** work together to achieve a user registration **workflow**

A few examples of components are

| Component Category | Example           
| :-------------:|:-------------:| 
| Client | IOS app, Android app, Reactive app, Progressive web app, Hybrid app | 
| Compute | Microservice, Lambda | 
| Persistence | MySql database, Cassandra |
|Orchestration| Queue, Event bus, Cache|

![Worfklows and components](https://github.com/saurabh-herwadkar/system-design-999/blob/main/images/Worfklows%20and%20components.png)


### Logical component

**A**t the onset I need to clarify the concept of Logical component 

A component is basically a
(code + runtime + OS ) running on either a Container , VM or a Physical instance (Quite unlikely but possible)
A logical component may represent a Client component , or a compute component or a persistence component

For example

UI - A UI project or Mobile application
Compute - A container running a micro service
Persistence - A Mysql database
Orchestration - Queue, Event bus


### Polyglot persistence

**A** misconception is that we should ideally use only one persistence (database) technique for our information system
Different use cases (user stories) may ask for different types of database solutions within the same workflow
For example
1. Finanical transactions may require a Relational database with strong ACID properties (eg Oracle)
2. While user profiles may be ok with a No SQL databse with BASE properties (eg Mongo DB)

Modern engineers and budding Architects should be open to use different databse for different use cases within the same solution

**A** few key features are

1. Fit for purpose usage of database technologies as per us case
2. Mainly **Breaking** of the previous notion that there is only one database solution pre workflow
3. Cloud technologies and managed services make provisioning of these databases very easy

# Polyglot programming

**S**imilar to the concept of Polyglot persistence above different use cases may demand for different programming languages
Engineers should be open to using different programming languages in different components in different Micro services

For example

1. A Payment service may work best in Java Spring boot Spring MVC Container configuration + Oracle relation database (ACID)
2. An OTP generation service may fit good in Python 3, Lambda Serverless  + Mongo DB (BASE)

**A** few key features are

1. Use seperate programming language for a different use case (Possibly micro service)
2. Seperate programming languages would mean the associated underlying run times and a compatible DevOps pipeline


![Polyglot](https://github.com/saurabh-herwadkar/system-design-999/blob/main/images/Polyglot.png)


### Distributed systems

Contrary to the previous concept of having all components on a single machine and probably in a monolith
Distributed systems by default will have their components on seperate instances.
Components like UI, Compute and persistence will be on seperate logical instances

**A** few key features are

- In modern achitectures (Post 2020) by default your system will be distributed
- Communication betwweh these components will be mainly using HTTP(s) though  other protocols may apply
- This surely increase the complexity of the system overall
- This reduces the total points of failure and mitigates against a single point of failure (SPF)
- Having components on different logical isntances ensures that there is optimum usage of resources
- Addition or removal of resources can be managed by concepts such as Auto scaling 

### Monolith v/s Micro sevices


### Virtual machine (VM) v/s Containers


### Disaster recovery


### DNS


### CDN


## Client

### Mobile app


### Front end


### Micro front ends

### Backend For Frontend (BFF) pattern


## Compute

### HTTP

### SSL (oh you meant TLS)

### API gateway


### REST v/s GraphQ: v/s gRPC


### Long staying HTTP connections

### Long polling
 
### Websockets

### Server side events (SSE)

### Service discovery

### Caching

### Serverless


## Orchestration

### Messagebroker

### Event bus

### Streaming architecture

### Event friven architecture EDA

### SLA SLO SLI


## Persistence

### Relational databases

### Keys

### Normalization and Denormalization


### ACID

### BASE

### CAP and PARCELC

### NoSql databases

###Sharding

###Database replication


###Database federation




## Agile 

## DevOps









