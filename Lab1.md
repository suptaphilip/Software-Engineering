# City University
#### SE 416: Software Engineering Laboratory
##### Lecture 1 & 2
Supta Richard Philip
supta.philip@gmail.com
****
## Relationships in UML
> It is the messages sent among objects that give a system dynamic behavior, and these are represented in UML through the relationships among classes. There are four kinds of relationships.

   1. Dependency:  A depends on B. This is a very loose relationship.
   
   ![dependency](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/dependency.png)
    ![dependency](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/dependency.jpg)
```java
public class Customer {
	private String customerId;
	private String customerName;
	//getter and setter
	}
```
```java
public class CustomerView {
	
	public void displayCustomer(Customer c){
		System.out.println("Customer Id:"+c.getCustomerId()+
				" Customer Name:"+c.getCustomerName()+" "
				);
	}
}
```
```java
public class CustomerTest {
	public static void main(String[] args) {
		Customer richard = new Customer();
		richard.setCustomerId("C001");
		richard.setCustomerName("Richard");
		CustomerView cv = new CustomerView();
		cv.displayCustomer(richard);
	}
}
```
   2. Association: A sends messages to a B. In programming terms, it means instances of A can call methods of instances of B, for example, if a B is passed to a method of an A.
    
   ![Association](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/association.png)
    
   3. Aggregation: An A is made up of B. This is a part-to-whole relationship, where A is the whole and B is the part. In code, this essentially implies A has fields of type B.
    
   ![Aggregation](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/aggregation.png)
    
   4. Composition: An A is made up of B with lifetime dependency. That is, A aggregates B, and if the A is destroyed, its B are destroyed as well.
    
   ![Composition](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/composition.png)
    
Two other important relationships deal with the relationship among classes.

   1. Generalization: A generalizes B. Equivalently, B is a subclass of A. In Java, this is extends.
    
   ![Generalization](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/generalization.png)
    
   2. Realization: B realizes (the interface defined in) A. As the parenthetical name implies, this is used to show that a class realizes an interface. In Java, this is implements, and so it would be common for A to have the «interface» stereotype.
    
   ![Realization](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/realization.png)

## Multiplicity
* A Teacher has between 20 to 30 students in a term, and that a student has exactly five teachers.
![Multiplicity](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/Multiplicity1.jpg)
* If a teacher had 20 or 30 students, then the class diagram.
![Multiplicity](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/Multiplicity2.jpg)
* If a teacher had zero or more students, then the class diagram.
![Multiplicity](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/Multiplicity3.jpg)
* If a teacher had one or more students,then the class diagram.
![Multiplicity](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/Multiplicity4.jpg)
```java
Class Teacher{
private String teacherId;
private String teacherName;
private List<Student> pupil;
//setter and getter
    }
}

Class Student{
private String studentId;
private String studentName;
private List<Teacher> instructors;
//setter and getter
    }
}
```
* Self Association

![SelfAssociation](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/SelfAssociation.jpg)

```java
class Person {
   private Person spouse;
   // etc.
}
```
* Association Example 1

![Association1](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/Association1.jpg)

```java
class Person {
   private Phone[] phones = new Phone[2];
   // etc.
}
```
* Association Example 2

![Association2](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/Association2.jpg)

```java
class Person {
   private Phone home;
   private Phone office;
   // etc.
}
```
* Association Example 3

![Association2](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/Association3.jpg)

```java
class Company {
   private Collection<Employee> employees;
   private Collection<SharePrice> sharePrices;
   // etc.
}
```
## Practice Problem

* Write the java code from the following class diagram.

![BankAccount](https://github.com/suptaphilip/Software-Engineering/raw/Lab-Summer2019/BankAccount.png)

## References
https://www.dariawan.com/tutorials/java/association-aggregation-and-composition-in-java/
http://www.cs.sjsu.edu/~pearce/modules/lectures/uml/class/association
