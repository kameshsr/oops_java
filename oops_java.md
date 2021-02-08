# **Object-Oriented Programming Concepts in java**
___

Object-Oriented Programming is a programming paradigm which is based on the concept of objects. 
Here objects contains 2 things data and code. Data can be in the form of fields. In other words fields can be called attributes or properties.

**Concepts in Object-Oriented Programming**

1. [Object](https://docs.oracle.com/javase/tutorial/java/concepts/object.html) 
2. [Class](https://docs.oracle.com/javase/tutorial/java/concepts/class.html)
3. [Inheritance](https://docs.oracle.com/javase/tutorial/java/concepts/inheritance.html)
4. [Encapsulation](https://www.javatpoint.com/encapsulation)
5. [Abstraction](https://www.javatpoint.com/abstract-class-in-java)
6. [Polymorphism](https://www.javatpoint.com/runtime-polymorphism-in-java)



1. **Object:-**

Objects are conceptually similar to real-world objects. They too consist of state and related behavior. An object stores it’s state in fields and exposes it’s behavior through methods. In Java we can create object using ‘new’ keyword.

**Example:-**

```
class Room{
    
    //This is a constructor with one parameter
    public Room(String type){       
        System.out.println("Your room is "+type); 
    }
    public static void main(String args[]){
        //This will create an object living
        Room living=new Room("Living Room");            
    }
}
```
**Output:-**

Your room is Living Room

2. **Class:-**

A class is the blueprint from which individual objects are created.
In real world too you can find many individual objects all of the same kind.

**Example:-**
```
class NewsPaper {
void print(int pages){
System.out.println("Your NewsPaper has "+pages+" pages.");
   }
}
class NewspaperPageCount {
public static void main(String[] args){

        //creating object of NewsPaper class
        NewsPaper hindu = new NewsPaper(); 
        
        //invoking methods on object
        hindu.print(16); 
    }
}
```
**Output:-**

Your NewsPaper has 16 pages.

3. **Inheritance:-**
   
   Different kinds of objects often have a certain amount in common with each other. Mountain bikes, road bikes and tandem bikes all share the characteristics of bicycles( current speed, current gear).
   Object-oriented programming allows classes to inherit commonly used state and behavior from other classes.In Java programming language, each class is allowed to have one direct super-class, and each super-class can have any number of sub-classes.



```
//Bicycle is parent class
class Bicycle{
    int gear=0;
}

//using extends keyword we implement inheritance in child class
class MountainBike extends Bicycle { 
    void printGear(int number){
        System.out.println("Number of gear="+number);
    }
    public static void main(String[] args){
        MountainBike Himalaya=new MountainBike();
        Himalaya.printGear(4);
    }
}
```
**Output:-**\
Number of gear=4

**There are 3 types of inheritance in java**. \
These are

a). **Single Inheritance:-**\
In this type of inheritance a class inherit properties of it’s parent class. For Example Car class can inherit properties of vehicle class.

**Example:-**

```
//Vehicle is super class
class Vehicle{
    void run(){
        System.out.println("Vehicle run on petrol");
    }
}

//car is extending Vehicle class 
class Car extends Vehicle{
    void numberOfWheels(int number){
        System.out.println("Number of wheels="+number);
    }
}

class VehicleCheck{
    public static void main(String[] args){
        Car maruti= new Car();
        maruti.numberOfWheels(4);
        
        //maruti object is using run method of vehicle class 
        maruti.run();
    }
}
```
**Output:-**

Number of wheels=4\
Vehicle run on petrol

b). **Multi-level Inheritance:-**\
In this type of inheritance parent class is having their own parent class like grand parents in real life.\
**Example:-**

```
//Super class
class GrandParent{
    void grandParentPrint(){
        System.out.println("Grandparent");
    }
}

//child class of GrandParent
class Parent extends GrandParent{
    void parentPrint(){
        System.out.println("Parent");
    }
}

//child class of Parent implements multi-level inheritance
class child extends Parent{
    void childPrint(){
        System.out.println("Child");
    }
}

class Person{
    public static void main(String[] args){
        child kamesh=new child();
        kamesh.childPrint();
        kamesh.parentPrint();
        kamesh.grandParentPrint();
    }
}
```
**Output:-**

Child \
Parent\
Grandparent


c). **Hierarchy Inheritance:-**\
In this type of inheritance one parent can have more than one child like we have siblings in our real life.\
**Example:-**

```
//Super class Vehicle
class Vehicle{
    void run(){
        System.out.println("It run on petrol");
    }
}

//Tractor extending Vehicle Class
class Tractor extends Vehicle{
    void carriagePower(){
        System.out.println("Tractor can lift 100 kg of sand.");
    }
}

//Car also extending Vehicle Class implements Hierarchy Inheritance
class Car extends Vehicle{
    void print(){
        System.out.println("Car capacity is to carry 4 people.");
    }
}

class TestVehicle{
    public static void main(String[] args){
        Car nano=new Car();
        nano.print();
        nano.run();
        Tractor kisan= new Tractor();
        kisan.carriagePower();
        kisan.run();
    }
}
```
**Output:-**

Car capacity is to carry 4 people.\
It run on petrol\
Tractor can lift 100 kg of sand.\
It run on petrol

4. **Encapsulation:-**

The process of combining data and code together is called encapsulation.
We can use a private keyword and use setter and getter to implement encapsulation in java.\
**Example:-**
```
class Person{
    //private variable name
    private String name; 
    //getter method for name
    public String getName(){ 
        return name;
    }
     //setter method for name
    public void setName(String name){ 
        this.name=name;
    }
}

class PersonName{
    public static void main(String[] args){
        //creating object of encapsulated class
        Person p=new Person();  
        p.setName("Bhagat");
        System.out.println(p.getName());
    }
}
```
**Output:-**

Bhagat

5. **Abstraction:-**

Abstraction is the process to show only necessary things to user and hide implementation. Like in real life we apply brake in bike and it stop but we don’t know how internally it works.

We can implement abstraction using abstract class or interfaces in java.\
**Example:-**
```
// Here only numberOfWheels method is declared
interface vehicle{
    void numberOfWheels(int number);
}

class Car implements vehicle{
    
    //Here method numberOfWheels implementation 
    public void numberOfWheels(int number){
        System.out.print("Number of wheels in Car "+number);
    }
    public static void main(String args[]){
        Car maruti= new Car();
        maruti.numberOfWheels(4);
    }
}
```
**Output:-**

Number of wheels in Car 4

6. **Polymorphism:-**

Polymorphism in java is a concept by which we can perform single action in different ways. Using this objects can take many forms.\
**In java polymorphism is of 2 types.**\
1.Compile time polymorphism: is implemented using method overloading.\
2.Run time polymorphism : is implemented using method overriding.
**Example:-**
```
class Add{
    int add(int a, int b){
        return a+b;
    }
    //Here method overloading (compile time polymorphism)
    int add(int a, int b, int c){
        return a+b+c;
    }
}

class Sum{
    public static void main(String[] args){
        Add a=new Add();
        System.out.println(a.add(4,3));
        System.out.println(a.add(3,4,5));
    }
}
```
**Output:-**

7\
12

**References**
1. [Java docs](https://docs.oracle.com/javase/tutorial/java/concepts/index.html)
2. [javatpoint](https://www.javatpoint.com/java-tutorial)



