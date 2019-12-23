### Singleton Pattern
The singleton pattern is a design pattern that restricts the instantiation of a class to one object.
### Volatile keyword
Using volatile is yet another way (like synchronized, atomic wrapper) of making class thread safe.
### Comparable<T>
Is an interface that needs to implement compareTo method to use Arrays.sort(list) or Collections.sort(list).
### Comparator<T,T>
Is a functional interface that needs to implement compare method between two objects.
### String vs StringBuffer vs StringBuilder
- String is immutable whereas StringBuffer and StringBuider are mutable classes.
- StringBuffer is thread safe and synchronized, whereas StringBuilder is not, thats why StringBuilder is more faster than StringBuffer.
- String concat + operator internally uses StringBuffer or StringBuilder class.
- For String manipulations in non-multi threaded environment, we should use StringBuilder else use StringBuffer class.
### String Pool
String Pool in java is a pool of Strings stored in Java Heap Memory to save memory.
### How to Create an Immutable class
- Declare the class as final so it can’t be extended.
- Make all fields private so that direct access is not allowed.
- Don’t provide setter methods for variables Make all mutable fields final so that it’s value can be assigned only once.
- Initialize all the fields via a constructor performing deep copy.
- Perform cloning of objects in the getter methods to return a copy rather than returning the actual object reference.
### Interface
- Methods declared in interface are abstract by default. We can now add default method implementation for interface methods. A class can implement more than one interface.
- An interface can extends another interface or interfaces (more than one interface).
- All the methods are public and abstract. And all the fields are public, static, and final.
### Abstract Classes
- Abstract classes are defined by keyword abstract. Instance of Abstract class cannot be created.
- We can have references of abstract class though. We can have abstract class without any abstract methods.
- It can have final methods that cannot be overridden.
### Functional Interface
- A functional interface has only one abstract method but it can have multiple default methods.
- @FunctionalInterface annotation is used to ensure an interface can’t have more than one abstract method.
- The use of this annotation is optional.
### Lambda Expressions
- Lambda expression provides implementation of functional interface.
- It provides a clear and concise way to represent one method interface (Functional Interface) using an expression. Syntax : (argument-list) -> {body}
### Access Modifiers
- access modifiers in Java helps to restrict the scope of a class, constructor , variable , method or data member.
1. Default
No keyword required The data members, class or methods which are not declared using any access modifiers i.e. having default access modifier are accessible only within the same package.
2.public
The public access modifier has the widest scope among all other access modifiers.
3.private
The methods or data members declared as private are accessible only within the class in which they are declared.
private and protected modifiers in terms of application to classes, they apply only to nested classes and not on top level classes.
4.protected 
the methods or data members declared as protected are accessible   within same package or sub classes in different package. 
### Non-Access Modifiers -
They are used with classes, methods, variables, constructors etc to provide information about their behavior to JVM.

1.**static**
- To create a static member(block,variable,method,nested class), precede its declaration with the keyword static.
- Static variables are, essentially, global variables.
- All instances of the class share the same static variable. We can create static variables at class-level only.
- Local static variables cannot be created. They cannot be created inside a method or a block.
- static block and static variables are executed in order they are present in a program They can only directly call other static methods.
- They can only directly access static data. They cannot refer to this or super in any way.
- We can not declare top-level class with a static modifier, but can declare nested classes as static.
2. **final**
- final is a non-access modifier applicable only to a variable, a method or a class. 
- When a variable is declared with final keyword, its value can’t be modified, essentially, a constant.
- This also means that you must initialize a final variable.
- A final variable can only be initialized once, either via an initializer or an assignment statement.
- it can be initialized while declaration, in a static block, in a constructor, in a block of braces.
- final class cannot be extended(inherited).It is done to prevent inheritance and create immutable classes.
- final methods cannot be overriden.
3. synchronized
- Synchronized blocks in Java are marked with the synchronized keyword.
- A synchronized block in Java is synchronized on some object.
- This synchronization is implemented in Java with a concept called monitors.
- Only one thread can own a monitor at a given time. When a thread acquires a lock, it is said to have entered the monitor.
- All other threads attempting to enter the locked monitor will be suspended until the first thread exits the monitor.
- We do not always have to synchronize a whole method. Sometimes it is preferable to synchronize only part of a method.
- Java synchronized blocks inside methods makes this possible. ex: synchronized(this) { //some logic }
4. **transient**
- transient keyword is used in serialization.
- At the time of serialization, if we don’t want to save value of a particular variable in a file, then we use transient keyword.
- Another use of transient keyword is not to serialize the variable whose value can be calculated/derived using other serialized objects or system such as age of a person, current date, etc.  
5. volatile 
- volatile keyword is used to make class thread safe.
- Before we move on let’s take a look at two important features of locks and synchronization.
    - Mutual Exclusion: It means that only one thread or process can execute a block of code (critical section) at a time.
    - Visibility: It means that changes made by one thread to shared data are visible to other threads.  
    - synchronized keyword guarantees both mutual exclusion and visibility. volatile provides visibility i.e changes made by one thread are visible to other threads access the variable.
6. native
7. abstract 
### Exceptions 
- An exception is an unwanted or unexpected event, which occurs during the execution of a program or at compile time.
- **Error** - An Error indicates serious problem that a reasonable application should not try to catch. these indicate errors regarding the run time environment
- **Exception** - Exception indicates conditions that a reasonable application might try to catch.
- All exception and errors types are sub classes of class Throwable, which is base class of hierarchy.
![link](https://media.geeksforgeeks.org/wp-content/uploads/Exception-in-java1.png)
- Exception handling keywords : try, catch,throws,throw,finally 
    - Checked Exceptions   
        exceptions that are checked at compile time are checked exceptions.   
        If some code inside a method throws a checked exception then, the method should handle the exception gracefully or throw the exception forward.
    - Unchecked Exceptions  
      exceptions that are not checked at compile time are unchecked exceptions.
- Exceptions under error and runtime exception classes are unchecked, everything else is checked.
### Overloading
- Overloading allows different methods to have the same name, but different signatures where the signature can differ by the number of input parameters or type of input parameters or both.   
- It is an example of compile time polymorphism.
- If exact prototype doesn't match type conversion to higher type of higher family takes place.
- we can overload return type but the no of arguments or type of arguments should be different.
- static methods can also be overloaded. main() method can also be overriden.
- Overloading is about same function have different signatures. Overriding is about same function, same signature but different classes connected through inheritance.
- Overloading is an example of compiler time polymorphism and overriding is an example of run time polymorphism.
### Overriding
- Overriding is a feature that allows a subclass or child class to provide a specific implementation of a method that is already provided by one of its super-classes or parent classes Read more about this.
### Runnable and Callable
- Runnables can be executed using Thread class or Executor Service. Callable is executed using Executor service.
- Runnable interface is a functional interface that has a single run() method which doesn't accept any parameters and does not return any value (void method).
- in Runnable the method run() signature does not have the “throws” clause specified, there is no way to propagate further checked exceptions.
- The Callable interface is a generic interface containing a single call() method – which returns a generic value V Result of call() is returned in a Future object.
    - Future<Integer> future = executorService.submit(task); future.get(); // exception is thrown only when we call future.get(); or else not thrown
- Callable's call() method contains “throws Exception” clause so we can easily propagate checked exceptions further.
### Deadlock
Deadlock is a situation when two threads are waiting for each other and the waiting is never ends. Here both threads cant completes their tasks.
### Starvation
- In Starvation, threads are also waiting for each other.
- But here waiting time is not infinite after some interval of time, waiting thread always gets the resources whatever is required to execute thread run() method.
### Inner Class
- Java inner classes are defined inside the body of another class.
### Super
- Super keyword is a reference variable that is used to refer parent class objects.
- Call to super() must be first statement in Derived(Student) Class constructor. 
- If a constructor does not explicitly invoke a superclass constructor, the Java compiler automatically inserts a call to the no-argument constructor of the superclass.
### Translator
- The most general term for a software code converting tool is a translator.
- It could refer to compiler,interpreter, assembler. It converts high level code to another high level code or machine code.
### Compiler
- Compiler converts high level code to machine code in one go.
- It takes time as it has to process whole file. compiler creates machine code that runs on a processor with a specific Instruction Set Architecture(ISA)
### Interpreter
- Interpreter converts high level code to machine code one line at a time.
- So it is faster than a compiler at the start. They are used in debugging tools.
- JIT compiler is a interpreter
### SQL Query
    Select employee with nth highest salary Select name, salary from employee A where n-1 = (select count(*) from employee B where B.salary > A.salary);
### Generics
- Generics provide strong compile time type checking and reduces risk of classcastexception and explicit casting of objects. generic code ensures type safety.
-  The compiler uses type-erasure to remove all type parameters at the compile time to reduce the overload at runtime.
    - class signature 
    ```
       public class Fruit <T> {
                T color;
                Fruit(T color) {this.color = color;}
                void setColor(T color) {this.color = color;}
                T getColor() {return this.color;}
        }
    ```
- generic method in a non generic class signature 
        ```
        public <T> boolean isEquals(T value1, T value2) { return value1.equals(value2);}
        ```
- starting<T> is to define the type of object it works on as class in non generic 
### Microservices - 
- Microservice is a small, loosely coupled distributed service. 
- Seperation of concerns It is a solution to the problem of scalability and innovation challenges with monolith architecture.
- It takes large appilcations and breaks it into smaller easily manageable components.
### Daemon Thread - 
- It is an utmost low priority thread.
- Used to run background tasks such as garbage collection.
- JVM wont wait for daemon threads to finish when user threads finish execution.
- Thread can be made deameon by using method setDaemon(boolean on) as true (by default this value is false), currentStatus can be found by boolean isDaemon().
- need to make a thread daemon before starting it or else it throes illegalThreadStateException
### Polymorphism
- polymorphism means having many forms. In simple words, we can define polymorphism as the ability of a message to be displayed in more than one form.
- Polymorphism allows us to perform a single action in different ways.
- Compile time Polymorphism -  It is also known as static polymorphism. 
- Runtime Polymorphism - It is also known as Dynamic Method Dispatch.
### Abstraction
- Abstraction means using simple things to represent complexity.
- abstraction is achieved by using abstract classes and interfaces
### Encapsulation
- wrapping up of data under a single unit. There 
- This is the practice of keeping fields within a class private, then providing access to through methods.
  data-hiding
### Inheritance
- This is the practice of using existing code and extend the functionality.
- Supports Reusability  
#### No of ways to create a thread 
- 2 ways - by implementing Runnable and by extending Thread class
### Java Collections
![collection framework](https://media.geeksforgeeks.org/wp-content/uploads/java-collection.jpg)

### Automatic Resource Management in Java
- ` try-with-resources `
- Resource : A resource is an object that must be closed after the program is finished using it. Any object that implements java.lang.AutoCloseable, which includes all objects which implement java.io.Closeable, can be used as a resource.
- In try with resources there is no use of finally block. The file resource is openened in try block inside small brackets.
- Only objects of those classes can be opened within block which implements AutoClosable interface and those objects should be local.
- The resource will be closed automatically regardless of whether try statement completes normally or abruptly.
```
static String readFirstLineFromFile(String path) throws IOException
{
    try (BufferedReader br = new BufferedReader(new FileReader(path)))
    {
        return br.readLine();
    }
}
```
- Multiple resources can be used inside a try with resources block ad have them all automatically closed.
- Resourcess will be closed in the reverse order in which they were created inside the brackets.
```
try(Demo d = new Demo(); Demo1 d1 = new Demo1()) {
    int x = 10/0;
    d.show();
    d1.show1();
}
catch(ArithmeticException e) {
    System.out.println(e);
}
```
- ARM is done when you initialize resource in try-with-resources block because of the interface AutoCloseable. Its close method is invoked by JVM as soon as try block finishes.
- The resources which are used in multiple resource ARM must be closed in reverse order as given in above example
- A try-with-resources statement can have catch and finally blocks just like an ordinary try statement. In a try-with-resources statement, any catch or finally block is run after the resources declared have been closed.

### Kafka
- Kafka is generally used for two broad classes of applications:
    - Building real-time streaming data pipelines that reliably get data between systems or applications
    - Building real-time streaming applications that transform or react to the streams of data

- **Keywords**
    - Topics
        - Topic is a category or feed name to which records are published.
        - Topics in Kafka are always multi-subscriber i.e a topic can have zero,one or many consumers that subscribe to the data written to it.
        - For each topic, the Kafka cluster maintains a partitioned log that looks like this
        ![kafka](https://kafka.apache.org/23/images/log_anatomy.png)
        - Each partition is an ordered, immutable sequence of records that is continually appended to—a structured commit log.
        - messages can be retained for a particular retention period.
        - Kafka's performace is effectively constant wrt data size so storing data for a long time is not a problem.
    - Partitions
        - Partitions are distributed across brokers.
        - Partition can be replicated across a configurable number of servers for fault tolerance.
        - Each partition has one server that acts as the LEADER and zero or more servers that act as FOLLOWERS.
        - The leader handles all read write requests for the partition while the followers passively replicate the leader.
        -If the leader fails then one of the followers will automatically become the new leader.
    - Brokers
    - Cluster
    - Producers
        - Producers publish data tot the topics of their choice.
        - The producer is responsible to choosing which record to assign to which partition within the topic.
        - This can be done in a round-robin fashion simply to balance load or it can be done according to some funtion.
    - Consumer
        - Consumers label themselves within a consumer group.
        -![kafkaConsumer](https://kafka.apache.org/23/images/consumer-groups.png)
- Kafka Guarantees
    - Messages sent by a producer to a particular topic partition will be appended in the order they are sent. That is, if a record M1 is sent by the same producer as a record M2, and M1 is sent first, then M1 will have a lower offset than M2 and appear earlier in the log.
    - A consumer instance sees records in the order they are stored in the log.
    - For a topic with replication factor N, we will tolerate up to N-1 server failures without losing any records committed to the log.
- Kafka As a Messaging System
- Kafka As A Storage System
    - Data written to Kafka is written to disk and replicated for fault-tolerance.
    - Kafka allows producers to wait on acknowledgement so that a write isn't considered complete until it is fully replicated and guaranteed to persist even if the server written to fails.
### Serialization and Deserialization
- Serialization is the mechanism of converting the state of an object into a byte stream.
- Deserialization is the reverse process where the byte stream is used to recreate the actual Java object in memory.
![image](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2016/01/serialize-deserialize-java.png)
- The byte stream created is platform independent. So, the object serialized on one platform can be deserialized on a different platform.
- To make java object serializable it needs to implement ```java.io.Serializable``` interface
- used to save the state of an object or to transfer an object across a network.
- Serializable is a **Marker Interface** ( has no datamember of method ).
- Only non-static data members are saved via Serialization process.
- static data members and transient data memebers are not saved via Serialization process.
- Constructor is never called while deserialization
- Serializable runtime assosciates a version number with each serializable class called ```SerialVersionUID```, which is used during Deserialization.
- If the reciever has loaded an object that had different UID than that of corresponding sender's class, the deserialization will result in an ```InvalidClassCastException```.
- ``` ANY-ACCESS-MODIFIER static final long serialVersionUID=42L;``` preferably final
- a variable defined as ```transient``` is not serialized during serialization process. This variable will be initialized with default value during deserialization.
- a variable defined as ```static``` is not serialized during serialization. This variable will be loaded with current value defined in the class during deserialization.
### CAP THEOREM
- CAP Theorem is a concept that a distributed database system can only have 2 of the 3: Consistency, Availability and Partition Tolerance.
- ![image](https://miro.medium.com/max/444/1*WPnv_6sG9k4oG3S1A09MDA.jpeg)
- It is very important while designing distributed systems and take decissions by tradeoffs.
- Partition Tolerance
    - A system that is partition-tolerant can sustain any amount of network failure that doesn’t result in a failure of the entire network.
    - Data records are sufficiently replicated across combinations of nodes and networks to keep the system up through intermittent outages.
    - When dealing with modern distributed systems, Partition Tolerance is not an option. It’s a necessity. Hence, we have to trade between Consistency and Availability.
- High Consistency
    - A guarantee that every node in a distributed cluster returns the same, most recent, successful write. 
    - This condition states that all nodes see the same data at the same time.
    - Simply put, performing a read operation will return the value of the most recent write operation causing all nodes to return the same data. 
    -  A system has consistency if a transaction starts with the system in a consistent state, and ends with the system in a consistent state. 
    -  In this model, a system can (and does) shift into an inconsistent state during a transaction, but the entire transaction gets rolled back if there is an error during any stage in the process.
- High Availability
    - Every non-failing node returns a response for all read and write requests in a reasonable amount of time.
    - This condition states that every request gets a response on success/failure.
### OSI MODEL (Open System Interconnection Model
- Introduced to standardize communication
- Conceptual framework used that describes the functions of a networking system.
- 7 Layers (All People Seem To Need Data Processing)
    - 7. Application
    - 6. Presentation
    - 5. Session
    - 4. Transport
    - 3. Network
    - 2. Data Link
    - 1. Physical
- Application Layer
    - Application layer acts as an interface to access network services for clients.
    - It has protocols to communicate through http and https
    - It sends and recieves information from Presentation layer.
    - Layer that is closest to end user.
- Presentation Layer
    - Transforms the data from application format to network format and vice-versa.
    - example is encryption and decryption of data for secure transmission.
- Session
    - Used to create a session to communicate between two devices.
    - Functions at this layer involve setup, coordination and termination b/w applications at the end of session.
- Transport
    - It deals with the cooordination of the data transfer between end systems and hosts.
    - How much data to send, at what rate, where it goes etc
    - It ensures data units are delivered error-free and in sequence.
    - The best known example of the Transport Layer is the Transmission Control Protocol (TCP), which is built on top of the Internet Protocol (IP), commonly known as TCP/IP.
    - TCP and UDP port numbers work at transport layer.
- Network
    - Network Layer is where we'll find most of the router functionality that most networking professionals care about and love. 
    - It is responsible for packet forwarding, including routing through different routers.
    - IP addresses work at Network layer.
- Data Link
    - this provides node to node data transfer and also handles error correction from physical layer.
    - This consists of two sub-layers 
        - Media Access Layer (MAC)
        - Logical Link Layer (LLC)
    - Most switches operate at data link layer
- Physical
    - This represents electrical and physical representation of our system.
    - This includes everything from cable type, radio link.

### TCP/IP Model (Transport Control Protocol / Internet Protocol) 
- TCP/IP helps you how a specific computer should be connected to the internet and how  data should be transmitted between them.
- It is designed to offer highly reliable and end-to-end byte stream over an unreliable network.
- Support for a flexible architecture and adding to a network is easy.
- It is a **connection-oriented** protocol
- Four layers of TCP/IP
    - Application
    - Transport
    - Internet
    - Network Interface
- It is a layered server architecture system in which each layer is defined according to a specific function to perform.
- ![image](https://www.guru99.com/images/1/093019_0615_TCPIPModelW2.png)
- Application Layer
    - The application layer is the OSI layer, which is closest to the end-user.
    - Application Layer interacts with software applications to implement a communicating component.
    - talks to transport layer using ports;
    - http uses port 80
- Transport Layer
    - TCP and UDP
    - TCP adds headers to the packets so the reciving computer knows how to construct the data and check for any losses.
- Internet Layer
    - attaches both origin and destination addresses to the packet so it knows where to go and where it came from.
    -  The main work of this layer is to send the packets from any network, and any computer still they reach the destination irrespective of the route they take.
    - Layer-management protocols that belong to the network layer are:
        - Routing protocols
        - Multicast group management
        - Network-layer address assignment.
- Network Interface Layer
    - This layer is also called a network access layer. It helps you to defines details of how data should be sent using the network.
    - Handles mac addressing so the data goes to the right physical machine as well as converting data to electrical impulses.
- Differences between OSI and TCP/IP
![image](https://www.guru99.com/images/1/093019_0615_TCPIPModelW3.png)
### TCP vs UDP
- TCP : Transmission Control Protocol
- UDP : User Datagram Protocol
- Tcp is connection oriented i.e once a connection is established data can be sent bidirectional
- Udp is a simpler connectionless Internet protocol. Multiple messages are sent as packets in chunks using udp.
- In udp one program can send a load of packets to another and that would be end of the relationship.
- TCP : HTTP, HTTPS, FTP, SMTP
- UDP: DNS,VOIP
- TCP rearranges data packets in the order specified
- UDP has no inherent order as all packets are independent of each other. If ordering is required it has to managed by the application layer.
- UDP is faster than TCP because error recovery is not attempted. It is a best effort protocol.
- Reliability
    - TCP is more reliable since it manages message acknowledgement and retransmissions in case of lost parts. Thus there is absolutely no missing data.
    - UDP does not ensure that communication has reached receiver since concepts of acknowledgement, time out and retransmission are not present.
- Ordering
    - TCP transmissions are sent in sequence and they are recieved in same sequence. If they arrive in wrong order, it reorders and delivers application.
    - in UDP message sequence may not be maintained when it reaches receiving application. There is absolutely no way of predicting the order in which message will be recieved.
- Connection
    - Tcp is a heavy weight connection requiring three packets for a socket connection and handles congestion control and  reliability
    - UDP is a lightweight transport layer designed a top an IP. There are no tracking connections or ordering of messages.
- Method of transfer
    - Tcp reads data as byte stream and message is transmitted a to segment boundaries.
    - UDP messages are packets which are sent individually and on arrival are checked for their integrity. Packets have defined boundaries while data stream has none