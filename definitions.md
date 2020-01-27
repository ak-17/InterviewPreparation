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
- Default
    - No keyword required The data members, class or methods which are not declared using any access modifiers i.e. having default access modifier are accessible only within the same package.   
- public
    - The public access modifier has the widest scope among all other access modifiers.
- private
    - The methods or data members declared as private are accessible only within the class in which they are declared. private and protected modifiers in terms of application to classes, they apply only to nested classes and not on top level classes.
- protected 
    - the methods or data members declared as protected are accessible   within same package or sub classes in different package. 
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
### Hiding
- static methods can be inherited by child class.
- Hiding is what occurs when a static is method is declared in child class with the same signature.
- You cannot achieve runtime polymorphism with static methods since they are class methods, not instance methods.
- [Read Here for more details](http://geekexplains.blogspot.com/2008/06/can-you-override-static-methods-in-java.html).
- This is called hiding.
### Runnable and Callable
- Runnables can be executed using Thread class or Executor Service. Callable is executed using Executor service.
- Runnable interface is a functional interface that has a single run() method which doesn't accept any parameters and does not return any value (void method).
- in Runnable the method run() signature does not have the “throws” clause specified, there is no way to propagate further checked exceptions.
- The Callable interface is a generic interface containing a single call() method – which returns a generic value V Result of call() is returned in a Future object.
    - Future<Integer> future = executorService.submit(task); future.get(); // exception is thrown only when we call future.get(); or else not thrown
- Callable's call() method contains “throws Exception” clause so we can easily propagate checked exceptions further.
### Deadlock
- Deadlock is a situation where a set of processes are blocked because each process is holding one or more resources and waiting for another resource acquired by some other process and they are in a circular fashion.
- Deadlock can arise if following conditions hold true (Coffman conditions)
    - Mutual Exclusion: One or more than one resource are non-sharable (Only one process can use at a time)
    - Hold and Wait: A process is holding at least one resource and waiting for resources.
    - No Preemption: A resource cannot be taken from a process unless the process releases the resource.
    - Circular Wait: A set of processes are waiting for each other in circular form.
- Methods to handle deadlock
    - Deadlock prevention or avoidance : Prevention can be done by negating atleast one of the above mentioned necessary conditions for deadlock.
        - For avoidance we need to know all the information about the resources that processes will require in the future.
        - Bankers Algorithm is used for deadlock detection
    - Deadlock detection and recovery : Let deadlock occur and then do preemption to handle it
    - ignore the problem : if deadlock is very rare, then let it happen and reboot the system.Windows and unix take this approach
### Race Condition
- It is the condition where several processes tries to access the resources and modify the shared data concurrently and outcome of the process depends on the particular order of execution that leads to data inconsistency, this condition is called Race Condition.
- This condition can be avoided using the technique called Synchronization or Process Synchronization, in which we allow only one process to enter and manipulates the shared data in Critical Section.
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
```
class A { 
    int temp = 10; 
    public void print() 
    { 
        System.out.println("In Class A"); 
    } 
} 
class B extends A { 
    int temp = 20; 
    public void print() 
    { 
        System.out.println("In Class B"); 
    } 
} 
class C { 
    public static void main(String args[]) 
    { 
        A a = new B(); 
        System.out.println(a.temp); --line 1
        a.print();  -- line 2
    } 
} 
```
- in the above code line 1 prints 10 as variables are bind at compile time
- line 2 prints 20 as methods are invoked at run time
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
### BASE
- Basically Available Soft State, Eventual Consistency
- Basically Available : Guarantees the availability of the data. There will be a response to a request on success or failure.
- Soft State- The state of system can change over time
- Eventual Consistency - The system will become eventual consistent once it stops receiving input.
### NoSQL
- Schema Free
- Eventual Consistency
- Replication of data stores to avoid single point of failure
- can handle data variety and huge amounts of data
- Types
    - Key Value Stores
    - Wide Column Stores
    - Document databases
    - Graph Databases
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
### ACID properties
- A *transaction* is a single logical unit of work which accesses and possibly modifies the contents of a database.
- In order to maintain consistency in database certain conditions need to be followed. These are ACID properties.
- Atomicity - A transaction has to take place completely or does not take place at all. Partial trasactions are not allowed.
- Consistency - Database before the transaction and after the transaction must be consistent.
- Isolation - Multiple transactions must be able to perform independently without interference. Changes occuring in a particular transaction will not be visible to any other transaction until that change is written to memory.
- Durability - Changes of a successfull transaction should reflect even if the system goes down.
### Indexing
### DataBase Keys
- Super Key : Any attribute or a set of attributes that are used to uniquely identify a row is super key.
- Candidate Key : A minimal subset of a super key is a candidate key
- Primary Key : A key choosen from Candidate key which best represents the table is a primary key
- Foreign Key : A key that is used to express relation ship between two tables is a foreign key.
- Composite Key: A super set of Candidate keys is a Composite key.
- Compound Key : A Composite key that has a foreign attribute is called Compound Key.
- Surrogate Key : A Table that does not have a natural primary key. Then a artificial key is added to table to uniquely identify rows.
### DataBase Normalisation
- Normalisation is done to minimize data redundancy from a relation or a set of relations.
- Redundancy may cause irregularities while insertion, deletion and updation.
- Non-Prime Attribute : Attributes that are not part of any candidate keys
- 1NF
    - A table is said to be in 1NF if it doesnot contain any multivalued attributes.
- 2NF
    - A table is said to be in 2NF if it is in 1NF and does not contain any **partial dependency**
    - Partial Dependency : If the proper subset of a candidate key determines non-prime attribute, it is called partial dependency.i.e a non-prime attribute is related to a subset of candidate key.
- 3NF
    - A table is said to be in 3NF it is in 2NF and does not have transtive dependency for non-prime attributes.
    - When an attribute in the table depends on some non-prime attribute but not on prime attribute the it is transtive dependency.
    - For a functional dependency A -> B. If A is non-prime and B is non-prime then it is called transitive dependency.
- BCNF (Boyce Codd Normal Form)
    - A table is said to be in BCNF, it should be in 3NF and for any dependency A -> B, A should always be a super key i.e for A -> B, A cannot be a non-prime attribute with B being a prime attribute.
### Process and Process Table
- A process is an instance of a program in execution.
- Operating System is responsible for managing all the processes that are running on a computer and allocate each process certain amount of processor time for its execution.
- To keep track of the state of all processes, the OS maintains a table known as the process table.
- Inside the table every process is listed along with the resources the processes are using and the current state of the process.
- Process can be in 3 stages : *running, ready, waiting*
- running state means the process has all the resources it needs for execution and has been given permission by OS to use the processor.
- ready state means the process has all the resources it needs for execution and waiting for permission from OS to start executing.
- wating state means it is waiting for some external event to occur such as user input or disk access.
### Thread
- A thread is a single sequence stream with in a process.
- Because threads have properties of process they are also called light weight processes.
- They are used to achieve parallelism.
- A thread has its own program counter, register set and stack space.
- Threads are not independent of each other like processes, they share code section, data section and os resources.
### Scheduling Algorithms
- Arrival Time: Time at which the process arrives in the ready queue.
- Completion Time: Time at which process completes its execution.
- Burst Time: Time required by a process for CPU execution.
- Turn Around Time: Time Difference between completion time and arrival time. Turn Around Time = Completion Time – Arrival Time
- Waiting Time(W.T): Time Difference between turn around time and burst time. Waiting Time = Turn Around Time – Burst Time
- Objectives of Scheduling algorithms
    - Max CPU utilization [Keep CPU as busy as possible]
    - Fair allocation of CPU.
    - Max throughput [Number of processes that complete their execution per time unit]
    - Min turnaround time [Time taken by a process to finish execution]
    - Min waiting time [Time a process waits in ready queue]
    - Min response time [Time when a process produces first response]
- FCFS (First Come First Serve)
    - Simplest scheduling algorithm that schedules according to arrival times of processes.
    - Implemented using FIFO queue
    - non-preemptive scheduling algorithm
    - suffers from convoy effect
- Shortest Job First (SJF)
    - Process which have short burst times are scheduled first.
    - if two processess have same burst time then FCFS is taken into consideration
    - Non-Preemptive scheduling algorithm
- Shortest Remaining Time First (SRTF)
    - Preemptive model of SJF algorithm in which jobs are scheduled according to shortest remaining time
- Longest Job First (LJF)
    - Similar to SJF, but priority is given to process with long burst time
    - Non-Preemptive
- Longest Remaining Time First (LRTF)
    - Similar to above, longer remaining times are given priority
- Round Robing Scheduling
    - Each Process is assigned a fixed CPU time (time quantum) in a cyclic way.
    - It is designed for time-sharing systems
    - A circular queue is used for ready queue
    - After a 1 time quantum, context switch happens and the process is inturrupted and it will be put at the tail of queue.
- Priority Based Scheduling
    - Processess are scheduled according to priorities
    - if two priorities match, then the one which arrived earlier will be scheduled first.
    - starvation is possible.
- Multilevel Queue Scheduling (MLQ)
    - According to the priority of process, processes are placed in the different queues.
    - Generally high priority process are placed in the top level queue. Only after completion of processes from top level queue, lower level queued processes are scheduled.
- High Response Ratio Next
    - processess with high respose ratio are scheduled first
    - Response Ration = (Waiting Time + Burst Time)/Burst Time
- FCFS can cause long waiting times, when first job takes lot of time
- SJF and SRTF may cause starvation
- If time quantum is very long then Round Robin behaves as FCFS
- SJF is optimal in terms of avg waiting time for a given set of processess. But we cannot predict time of next job.
### Mutex and Semaphore
- Mutex and Semaphores are used to handle critical section problems. They are process synchronization tools.
- The basic difference between them is
    - Semaphore is a signalling mechanism i.e processess perform wait() and signal() operation to indicate whether they are acquiring or releasing the resource.
    - Mutex is a locking mechanism, it has to aquire the lock on mutex object if it wants to acquire the resource.
- Semaphore
    - Semaphore: It is a typically an integer variable that is initialized to the number of resources present in the system and the value can be modified by only wait() and signal().
    - The wait() and signal() operation modify the value of the semaphore indivisibly. It means that when a process is modifying the value of the semaphore, no other process can simultaneously modify the value of the semaphore.
    - Semaphores are distinguised by the operating system in two categories *counting semaphore* and *Binary Semaphore*
    - In Counting Semaphore, the semaphore S value is initialized to the number of resources present in the system. Whenever a process wants to access the resource it performs wait() operation on the semaphore and decrements the value of semaphore by one. When it releases the resource, it performs signal() operation on the semaphore and increments the value of semaphore by one.
    - When the semaphore count goes to 0, it means all resources are occupied by the processes. If a process need to use a resource when semaphore count is 0, it executes wait() and get blocked until the value of semaphore becomes greater than 0.
    - Binary Semaphore is similar to mutex but mutex is a locking mechanism where as semaphore is a signalling mechanism.
- Mutex
    - Only one process can access the given resource.
    - Mutex object allows the multiple program threads to use the same resource but one at a time not simultaneously.
    - Meanwhile, a process has acquired the lock on mutex object no other thread/process can access that resource. If the mutex object is already locked, the process desiring to acquire the lock on mutex object has to wait and is queued up by the system till the mutex object is unlocked.
- Key Differences
    - Semaphore is a signalling mechanism as wait() and signal() are performed on semaphore variable to indicate whether a process is acquiring a resource or releasing a resource. Mutex is a locking mechanism, as to acquire a resource, a process need to lock a mutex object and while releasing it has to unlock mutex object
    - Semaphore is typically an integer where as mutex is an object.
    - Semaphore allows multiple instances of threads to access a finite instance of resources. Mutex allows multiple program threads to access a single shared resource but one at a time
    - Semaphore variable can be modified by any process acquires or releases resource by calling wait() or signal() operations. Lock acquired on mutex object has to be released only by the process that has acquired it.
### Virtual Memory
- secondary memory: Hard disk (Logical Address Space)
- main memory : RAM
- Virtual Memory is a storage allocation scheme in which secondary memory can be addressed as though it were part of main memory. (Illusion of large main memory)
- Only few pages of a process are loaded into frames in main memory. when the process requires a page and it is not present in page-table,(this is called page fault) then the process gets interuppted and os takes over to bring the required page into main memory and swap it with a existing or a empty frame and updates the page table.
- This way processes that are larger than main memory can be executed.
- If there is too much swapping of pages, then it is called thrashing.
- The process of loading a page into memory on demand is called demand paging.
- ![image](https://media.geeksforgeeks.org/wp-content/uploads/VirtualDiagram-1.png)
- https://www.geeksforgeeks.org/virtual-memory-in-operating-system/
### Page Fault
- A page fault occurs when a program attempts to access a block of memory that is not stored in the physical memory, or RAM.
- This notifies the OS that it must locate the page from virtual memory, then transfer it from storage device to main memory.
- Once the page is moved to main memory then the program executes as usual.
- each page fault requires swapping of pages from virtual memory to primary memory. This is significantly slower than accessing data directly from memory.
### Page Replacement Algorithms
- FIFO
    -The operating system keeps track of all pages in the memory in a queue, the oldest page is in the front of the queue.
    - When a page needs to be replaced front of the queue is removed.
    - Belady's Anamoly : Belady’s anomaly proves that it is possible to have more page faults when increasing the number of page frames while using the First in First Out (FIFO).
- Optimal Page Replacement
    - In this algorithm, pages are replaced which have not been used for the longest duration.
    - This is perfect but not possible,as we cannot know future requests.
    - This is used to keep benchmar and analyse other algorithms
- LRU
    - Least Recently used page is replaced
- 
### Thrashing
- Thrashing is a situation when the performance of a computer degrades or collapses.
- Thrashing occurs when a system spends more time processing page faults than executing transactions.
-While processing pagefaults is necessary to get the benefits of virtual memory, thrashing has a negative effect on the system.
- As page fault rate increases more transactions need processing from the paging device. The queue at the paging device increases, resulting in increased service time for a page fault.
### How data is stored on hard disk
- Hard disk is a common data storage used in computers. Data is stored on the hard disk in the form of 0 and 1.
- The part of the hard disk that stores the data is known as platter.
- Platters are circular disk made of a non magnetic material typically aluminum alloy, glass or ceramic and are coated with a thin layer (10-20nm) of a magnetic material. Platters are further separated in to the tracks and sectors where tracks are concentric circles while sectors are pie shaped wedges on the track.
- Hard disk stores information in the form of magnetic fields. Data is stored digitally in the form of tiny magnetized regions on the platter where each region represents a bit.
- To write a data on the hard disk, a magnetic field is placed on the tiny field in one of these two polarities: N-S – If North Pole arrives before the south pole and S-N – if the south pole arrives before the north pole while the field is accessed.
- An orientation in the one direction (like N-S) can represent the ‘1’ while the opposite orientation (S-N) represents “0”. This polarity is sensed by integrated controllers built within the hard disk.
### NoSQL


### Operating Systems Keywords
- Mutex
- Semaphore
- Race Condition
    Several processes access and process the manipulations over the same data concurrently, then the outcome depends on the particular order in which the access takes place.
- Critical Section
- Priority Inversion
- Atomicity
- Independent Process : Execution of one process does not affects the execution of other processes.
- Cooperative Processes : Execution of one process affects the execution of other processes.
- https://www.geeksforgeeks.org/introduction-of-process-synchronization/
### SQL types
- DDL : Data Definition Language (Create, Alter, Drop)
- DML : Data Modification Language (Insert, Update, Select)
- DCL : Data Control Language (Grant, Revoke)
### SQL Functions
- CONCAT: joins two or more string values.
- SUBSTR: extracts string of a specific length.
- LENGTH: returns the length of the string
- INSTR: returns the position of the specific character.
- LPAD: padding of the left-side character value for right-justified value.
- RPAD: padding of right-side character value for left-justified value.
- TRIM: removes the defined character from beginning and end or both.
- REPLACE: replaces a specific sequence of characters with another sequence of characters.
- AVG, MAX, MIN, SUM, VARIANCE, COUNT
### Having and Where clause
- **Having** is used to specify a condition for a group or an aggregate function.
- **Where** works on row data not on selected data
- **Where** clause selects before grouping
- **Having** clause selects after grouping
- `EX: SELECT Student, Score FROM Marks WHERE Score >=40`
- `EX: SELECT Student, SUM(score) AS total FROM Marks GROUP BY Student HAVING total > 70`
### To find Duplicate rows do Group By
- `select NAME, count(NAME) as num from Person group by NAME;`
- `select NAME from Person group by NAME having count(NAME) > 1;`
### Joins
- Joins are used to combine data from two or more tables based on a common field between them.
- JOIN or INNER JOIN
    - ![image](https://blog.codinghorror.com/content/images/uploads/2007/10/6a0120a85dcdae970b012877702708970c-pi.png)
    - The INNER JOIN keyword selects all rows from both the tables as long as the condition satisfies.
    - This keyword will create the result-set by combining all rows from both the tables where the condition satisfies i.e value of the common field will be same
    - `SELECT StudentCourse.COURSE_ID, Student.NAME, Student.AGE FROM Student INNER JOIN StudentCourse ON Student.ROLL_NO = StudentCourse.ROLL_NO;`
- LEFT JOIN or LEFT OUTER JOIN
    - ![image](https://i.stack.imgur.com/VkAT5.png)
    - This join returns all the rows of the table on the left side of the join and matching rows for the table on the right side of join.
    - The rows for which there is no matching row on right side, the result-set will contain null.
    - LEFT JOIN is also known as LEFT OUTER JOIN.
    - `
        SELECT table1.column1,table1.column2,table2.column1, FROM table1 LEFT JOIN
        ON table1.matching_column = table2.matching_column;`
- RIGHT JOIN or RIGHT OUTER JOIN
    - ![image](http://www.databasejournal.com/img/jk_JustSQL4_image004.jpg)
    - RIGHT JOIN is similar to LEFT JOIN. RIGHT JOIN is also known as RIGHT OUTER JOIN
    - This join returns all the rows of the table on the right side of the join and matching rows for the table on the left side of join.
    - The rows for which there is no matching row on left side, the result-set will contain null.
    - `SELECT table1.column1,table1.column2,table2.column1 FROM table1 RIGHT JOIN table2 ON table1.matching_column = table2.matching_column`
- FULL JOIN
    -![image](https://i.stack.imgur.com/3Ll1h.png)
    - FULL JOIN creates the result-set by combining result of both LEFT JOIN and RIGHT JOIN.
    - The result-set will contain all the rows from both the tables. The rows for which there is no matching, the result-set will contain NULL values.
    - `SELECT table1.column1,table1.column2,table2.column1 FROM table1 FULL JOIN table2 ON table1.matching_column = table2.matching_column;`
- CROSS JOIN or CARTESIAN JOIN
    - The CARTESIAN JOIN is also known as CROSS JOIN.
    - In a CARTESIAN JOIN there is a join for each row of one table to every row of another table. This usually happens when the matching column or WHERE condition is not specified.
    - In the absence of a WHERE condition the CARTESIAN JOIN will behave like a CARTESIAN PRODUCT . i.e., the number of rows in the result-set is the product of the number of rows of the two tables.
    - In the presence of WHERE condition this JOIN will function like a INNER JOIN.
    - Generally speaking, Cross join is similar to an inner join where the join-condition will always evaluate to True
    - `SELECT table1.column1 , table1.column2, table2.column1 FROM table1 CROSS JOIN table2;`
- SELF JOIN
    - As the name signifies, in SELF JOIN a table is joined to itself.
    - That is, each row of the table is joined with itself and all other rows depending on some conditions.
    - In other words we can say that it is a join between two copies of the same table
    - `SELECT a.coulmn1 , b.column2 FROM table_name a, table_name b WHERE some_condition;`
### View
- A View is a virtual table based on the result of an SQL statement.
- `CREATE VIEW view_name AS SELECT column_name(s) from table_name WHERE condition`
- Views can represent a subset of the data contained in a table. Views can join and simplify multiple tables into single virtual table.
- Consequently, a view can limit the degree of exposure of the underlying tables to the outer world: a given user may have permission to query the view, while denied access to the rest of the base table.
- Views can act as aggregated tables, where the database engine aggregates data (sum, average etc.) and presents the calculated results as part of the data
- Views can hide the complexity of data; for example a view could appear as Sales2000 or Sales2001, transparently partitioning the actual underlying table
- Views take very little space to store; the database contains only the definition of a view, not a copy of all the data which it presents.
### Trigger
- A trigger is a code that associated with insert,update,delete operations.
- The code is executed automatically whenever the associated query is executed on a table.
- They are used to maintain integerity.
### Stored Procedure
- A stored procedure is like a function that contains a set of operations compiled together.
- It contains a set of operations that are commonly used in an application to do some common database tasks.
- Stored Procedures can be called directly. Triggers cannot be called directly they are assosciated with queries.
### Database Index
- A database index is a data structure that improves the speed of data retrieval operations on database table at the cost of additional writes and used more storage space.
- To support faster access according to different values, faster search like binary search for different values is desired.
- for this purpose, indexes are created on tables. These need extra space on disk but allow faster search according to different frequently searched values.
###  What is the difference between CHAR and VARCHAR?
- CHAR and VARCHAR are differ in storage and retrieval.
- CHAR column length is fixed while VARCHAR length is variable.
- The maximum no. of character CHAR data type can hold is 255 character while VARCHAR can hold up to 4000 character.
- CHAR is 50% faster than VARCHAR.
- CHAR uses static memory allocation while VARCHAR uses dynamic memory allocation.
### Spring Framework
-![link](https://www.journaldev.com/16966/spring-annotations)
- Spring Framework implements and promotes the principle of Inversion Of Control (IOC) or Dependency Inject (DI) and is in fact an IOC container.
- `@Configuration`
    - Used to indicate that a class declares one or more `@Bean` methods.
    - These classes are processed by the Spring Container to generate bean definitions and service requests for those beans at run time
- `@Bean`
    - Indicates that a method produces a bean to be managed by the Spring container.
    - This is one of the most used and important spring annotation. @Bean annotation also can be used with parameters like name, initMethod and destroyMethod.
    - name – allows you give name for bean
    - initMethod – allows you to choose method which will be invoked on context register (a method will be called on creation)
    - destroyMethod – allows you to choose method which will be invoked on context shutdown ( a method will be called on destroy)
- `@PostConstruct` and `@PreDestroy`
    - alternative way for bean initmethod and destroy method.
- `@ComponentScan`
### Java Memory Model
- Java Memory Model is a set of rules which all JVMs have to follow to ensure correct working of our concurrent programs
- JMM is a specification or set of rules which guararntees visibility of fields (aka happens before) amidst reordering of instructions
- Out of order exection
- Field Visibility
- Happens Before
### Init Block
```
{
    System.out.println("in init");
}
```
- init block executes before constructor on creation of object
### Java 8
- Consumer :  accepts a value but doesn't return anything
```
void accept(T t);
```
- Predicate : accepts a value and returns a boolean
```
boolean test(T t);
```
- Function: accepts a value and returns a value
```
R apply(T t);
```
- map(Function) : used to convert an object from one type to different type or same type
```
map(Function<? super T, ? extends R> mapper)
```
- mapToInt, mapToDouble, mapToLong : same as above but returns respective data types
-Collectors.groupingBy() - groups by a condition
```
Map<String,List<Employee>> groupedEmployeeMap =
    employeeList.stream()
                .collect(Collectors.groupingBy(Employee::getDepartment));

Map<String,Double> employeeSalaryMap =
    employeeList.stream()
                .collect(Collectors.groupingBy(Employee::getDepartment,
                         Collectors.summingDouble(Employee::getSalary)));
```