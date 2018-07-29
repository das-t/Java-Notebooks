
## Data Types in Java

- The only allowed characters for identifiers are all alphanumeric characters([A-Z],[a-z],[0-9]), ‘$‘(dollar sign) and ‘_‘ (underscore).For example “geek@” is not a valid java identifier as it contain ‘@’ – special character.
- Reserved Words can’t be used as an identifier. For example “int while = 20;” is an invalid statement as while is a reserved word. There are 53 reserved words in Java.

<img src="http://www.java2learn.com/wp-content/uploads/2015/06/Reserved-Keywords1.png" alt="Classification of Java Keywords" />

<div class="alert alert-block alert-warning">
<b>NB:</b> The keywords const and goto are reserved, even though they are not currently used. In place of const, final keyword is used. Some keywords like strictfp are included in later versions of Java.
</div>

- Java is statically typed and also a strongly typed language because in Java, each type of data (such as integer, character, hexadecimal, packed decimal, and so forth) is predefined as part of the programming language and all constants or variables defined for a given program must be described with one of the data types.
- Java has two categories of data:
    - Primitive data (e.g., number, character)
    - Object data (programmer created types)
    
<img src="https://cdncontribute.geeksforgeeks.org/wp-content/uploads/data-types-in-java.jpg" alt="Data Types of Java" />

## enum in Java

Enumerations serve the purpose of representing a group of named constants in a programming language. Enums are used when we know all possible values at **compile time**

``` java
enum Color{
    RED, GREEN, BLUE;
}
 
public class Test{
        public static void main(String[] args){
            Color c1 = Color.RED;
            System.out.println(c1);
        }
}```
 
- First line inside enum should be list of constants and then other things like methods, variables and constructor.
- According to Java naming conventions, it is recommended that we name constant with all capital letters
- Every enum constant is always implicitly public static final. Since it is static, we can access it by using enum Name. Since it is final, we can’t create child enums.
- We can declare main() method inside enum. Hence we can invoke enum directly from the Command Prompt.
``` java
enum Color{
    RED, GREEN, BLUE;
        public static void main(String[] args)
        {
            Color c1 = Color.RED;
            System.out.println(c1);
        }
}```

<div class="alert alert-block alert-warning">
<b>NB:</b> All enums implicitly extend java.lang.Enum class. As a class can only extend one parent in Java, so an enum cannot extend anything else.
</div>

## Variables in Java
- A variable is the name given to a memory location. It is the basic unit of storage in a program.
<img src="http://cdncontribute.geeksforgeeks.org/wp-content/uploads/Variables-in-Java.png" alt="Variable in Java">

There are three types of variables in Java:
    1. Local Variables
    2. Instance Variables
    3. Static Variables

1. Local Variables: exists only within the block in which the variable is declared
```java
public class StudentDetails{
        public void StudentAge(){   
        //local variable age
        int age = 0;
        age = age + 5;
        System.out.println("Student age is : " + age);
        }

        public static void main(String args[]){
            StudentDetails obj = new StudentDetails();
            obj.StudentAge();
        }
}```
2. Instance Variables:  these variables are created when an object of the class is created and destroyed when the object is destroyed
```java
class Marks{   
        //These variables are instance variables.
        //These variables are in a class and are not inside any function
        int engMarks;
        int mathsMarks;
        int phyMarks;
}
class MarksDemo{
        public static void main(String args[]){
                //first object
                Marks obj1 = new Marks();
                obj1.engMarks = 50;
                obj1.mathsMarks = 80;
                obj1.phyMarks = 90;

                //displaying marks for first object
                System.out.println("Marks for first object:");
                System.out.println(obj1.engMarks);
                System.out.println(obj1.mathsMarks);
                System.out.println(obj1.phyMarks);
        }
}
```
3. Static Variables:
```java
import java.io.*;
class Emp {
       // static variable salary
       public static double salary;
       public static String name = "Harsh";
}```

```java
public class EmpDemo{
     public static void main(String args[]) {
          //accessing static variable without object         
          Emp.salary = 1000;
          System.out.println(Emp.name + "'s average salary:" + Emp.salary);
     }
}```
- Unlike instance variables, we can only have one copy of a static variable per class irrespective of how many objects we create.
- Static variables are created at start of program execution and destroyed automatically when execution ends. 
- We can access instance variables through object references and Static Variables can be accessed directly using class name.

<div class="alert alert-block alert-warning">
<b>NB:</b> Changes made in an instance variable using one object will not be reflected in other objects as each object has its own copy of instance variable. In case of static, changes will be reflected in other objects as static variables are common to all object of a class.
</div>

|Modifier      |Package  |Subclass  |World   |
|--------------|---------|----------|--------|
|    public    |   Yes   |   Yes    |   Yes  |
|   protected  |   Yes   |   Yes    |   No   |
|    Default   |   Yes   |   No     |   No   |
|    private   |   No    |   No     |   No   |

###### Some Important Points about Variable scope in Java:
- In general, a set of curly brackets { } defines a scope.
- In Java we can usually access a variable as long as it was defined within the same set of brackets as the code we are writing or within any curly brackets inside of the curly brackets where the variable was defined.
- Any variable defined in a class outside of any method can be used by all member methods.
- When a method has same local variable as a member, this keyword can be used to reference the current class variable.
- For a variable to be read after the termination of a loop, It must be declared before the body of the loop.
    

#### Some Important rules for switch statements :
- Duplicate case values are not allowed.
- The value for a case must be the same data type as the variable in the switch.
- The value for a case must be a constant or a literal.Variables are not allowed.
- The break statement is used inside the switch to terminate a statement sequence.
- The break statement is optional. If omitted, execution will continue on into the next case.
- The default statement is optional, and it must appear at the end of the switch.

#### String in Switch Case in Java 
- Expensive operation: Switching on strings can be more expensive in term of execution than switching on primitive data types. Therefore, it is best to switch on strings only in cases in which the controlling data is already in string form.
- String should not be NULL: Ensure that the expression in any switch statement is not null while working with strings to prevent a NullPointerException from being thrown at run-time. 
    
#### Do we need forward declarations in Java?
- Unlike C++, we don’t need forward declarations in Java. Identifiers (class and method names) are recognized automatically from source files. Similarly, library methods are directly read from the libraries, and there is no need to create header files with declarations.
```java
class Test2 {      
    public static void main(String[] args) {    
         Test1 t1 = new Test1();
         t1.fun(5);         
    }
}    
class Test1 {   
    void fun(int x) {
        System.out.println("fun() called: x = " + x);
    }
}
```

## Type Conversion
```java
public class Test{
    public static void main(String[] args){
        System.out.print("Y" + "O");
        System.out.print('L' + 'O');
    }
}
```
**Output: YO155** (when we use single quotes, the characters ‘L’ and ‘O’ are converted to int. This is called widening **primitive conversion**)

<img src="http://cdncontribute.geeksforgeeks.org/wp-content/uploads/Widening-or-Automatic-Type-Conversion.png">
<img src="http://cdncontribute.geeksforgeeks.org/wp-content/uploads/Narrowing-or-Explicit-Conversion.png">

#### Type promotion in Expressions
While evaluating expressions, the intermediate value may exceed the range of operands and hence the expression value will be promoted. Some conditions for type promotion are:
1. Java automatically promotes each byte, short, or char operand to int when evaluating an expression.
2. If one operand is a long,float or double the whole expression is promoted to long,float or double respectively.
    
#### Comments in Java
In Java there are three types of comments:
    1. Single – line comments.
    2. Multi – line comments.
    3. Documentation comments.

####  Using underscore in Numeric Literals in Java
- A new feature was introduced by JDK 7 which allows to write numeric literals using the underscore character. Numeric literals are broken to enhance the readability.
- This feature enables us to separate groups of digits in numeric literals, which improves readability of code. 
 
#### Interesting facts about null in Java
- null is Case sensitive
- Any reference variable in Java has default value null.
-  Unlike common misconception, null is not Object or neither a type. It’s just a special value, which can be assigned to any reference type and you can type cast null to any type.
-  **Static vs Non static Methods:** We cannot call a non-static method on a reference variable with null value, it will throw NullPointerException, but we can call static method with reference variables with null values. Since static methods are bonded using static binding, they won’t throw Null pointer Exception.

```java
public class Test{             
    public static void main(String args[]){
        Test obj= null;
        obj.staticMethod();
        obj.nonStaticMethod();                             
    }
     
    private static void staticMethod(){
        //Can be called by null reference
        System.out.println("static method, can be called by null reference");
    }
         
    private void nonStaticMethod(){
        //Can not be called by null reference
        System.out.print(" Non-static method- ");
        System.out.println("cannot be called by null reference");
    }
 
}
```

#### Does Java support goto?
Java does not support goto, it is reserved as a keyword just in case they wanted to add it to a later version.
- Unlike C/C++, Java does not have goto statement, but java supports label.
- The only place where a label is useful in Java is right before nested loop statements.
- We can specify label name with break to break out a specific outer loop.
- Similarly, label name can be specified with continue.

```java
public class Main {
    public static void main(String[] args){
        outer:
            for (int i = 0; i < 10; i++) {
                for (int j = 0; j < 10; j++) {
                    if (j == 1)
                        break outer;
                    System.out.println(" value of j = " + j);
                }
            }
        }
}
```
