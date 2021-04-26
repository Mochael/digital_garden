---
title: C4 Model for Software Architecture
tree_state: 🌱
---

4 C's are **Context**, **Container**, **Component** and (optionally) **Code** (Usually don't do code diagrams because they are a lot of work, confusing, and not worthh the effort.)

Software System- A software system is the highest level of abstraction which includes the entirety of the software product you are building

Container- Not Docker! In the C4 model, a container represents an application or a data store. A container is something that needs to be running in order for the overall software system to work. Each container is a separately deployable/runnable thing or runtime environment, typically (but not always) running in its own process space.  Because of this, communication between containers typically takes the form of an inter-process communication. Examples are: Server-side web application, Client-side web application, Database, Serverless function, Shell script, etc.

Component- A component is a grouping of related functionality encapsulated behind a well-defined interface. Components are not separately deployable units.


### Level 1: System Context diagram
Treat your app as a black box and figure out other systems/users in the world that interact with it

https://c4model.com/img/bigbankplc-SystemContext.png

### Level 2: Container diagram
The Container diagram shows the high-level shape of the software architecture and how responsibilities are distributed across it. It also shows the major technology choices and how the containers communicate with one another.

https://c4model.com/img/bigbankplc-Containers.png



### Level 3: Component diagram
Next you can zoom in and decompose each container further to identify the major structural building blocks and their interactions.

https://c4model.com/img/bigbankplc-Components.png


### Level 4: Code
Finally, you can zoom in to each component to show how it is implemented as code; using UML class diagrams, entity relationship diagrams or similar.

https://c4model.com/img/bigbankplc-Classes.png