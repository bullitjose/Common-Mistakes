>GIT HUB
# REPOSITORIO PROYECTO

Tenemos un proyecto Git en local, y lo subiremos a GitHub. En local tenemos la carpeta "Hello git" y en GitHub hemos creado el repositorio "hello-git"

+ remote, configuramos con que repositorio en github queremos que se asocie el git local:
```
$git remote add origin https://github.com/bullitjose/hello-git.git
```

+ push , subir el repositorio local (master) de git al remoto github (origin):
```
$git push -u origin master
```

+ cambiar remote, para validar con ssh:
```
$git remote -v
origin	https://github.com/bullitjose/hello-git.git (fetch)
origin	https://github.com/bullitjose/hello-git.git (push)

$git remote set-url origin git@github.com:bullitjose/hello-git.git

$git remote -v
origin	git@github.com:bullitjose/hello-git.git (fetch)
origin	git@github.com:bullitjose/hello-git.git (push)
```

# SOLID

- Single Responsibility Each class should have only one sole purpose, and not be filled with excessive functionality

- Open Closed Classes should be open for extension, closed for modification. In other words, you should not have to rewrite an existing class for implementing new features.
Create interfaces, not modify or rewrite classes, extended with interface to implementing new features!!

- Liskov Substitution Let Φ(x) be a property provable about objects x of type T. Then Φ(y) should be true for objects y of type S where S is a subtype of T. This means that every subclass or derived class should be substitutable for their base or parent class. 

- Interface Segregation Interfaces should not force classes to implement what they can’t do. Large interfaces should be divided into small ones.

- Dependency Inversion Components should depend on abstractions, not on concretions. Create:
```
private final IVariable variable;
```
IVariable is a interface, its the abstraction, its better than:
```
private Variable variable=new Variable(); 
```
Variable its a class, a concrete class. Best create a interface from a Class, IClass, so Class implements IClass.
Now we can define new variable, as IClass, and then add a constructor with the variable as paramether:
```
private final IClass class;

//constructor with class as paramether
//here we use dependency injection
public ShapesPrinter (IClass class){
this.class=class;
}


```

>Single Responsibility

>Open Closed Classes should be open for extension, closed for modification.


# Common-Mistakes

[10 most common java mistakes](https://www.youtube.com/watch?v=rjDUpxtUPAE&ab_channel=Amigoscode )

>USE ITERATOR.

**Removing Items from a Collection, Iterators are designed to easily change the collections that they loop through**. 
An Iterator is an object that can be used to loop through collections, like ArrayList and HashSet.
The remove() method can remove items from a collection while looping.
Trying to remove items using a for loop or a for-each loop would not work correctly because the collection is changing size at the same time that the code is trying to loop.

```
  // Get the iterator
    Iterator<String> it = cars.iterator();

    // Print the first item
    System.out.println(it.next());
    
    //looping through a collection 
     while(it.hasNext()) {
  System.out.println(it.next());
}

```
 Looping through a collection and remove numbers less than 10:
```
ArrayList<Integer> numbers = new ArrayList<Integer>();
    numbers.add(12);
    numbers.add(8);
    numbers.add(2);
    numbers.add(23);
Iterator<Integer> it = numbers.iterator();
    while(it.hasNext()) {
      Integer i = it.next();
      if(i < 10) {
        it.remove();
      }
    }
    System.out.println(numbers);

```

>USE GENERICS.

Exemple:
```
ArrayList listOfNumbers=new ArrayList();
listOfNumbers.add(10);//int
listOfnumbers.add("20");//String, and COMPILE!!
```

We only allow Integers:
```
ArrayList <Integer> listOfNumbers=new ArrayList<>();
listOfNumbers.add(10);//int
listOfnumbers.add("20");//ERROR!!

```

Also change:
```
List <Integer> listOfNumbers=new LinkedList<>();
```

List as interface. LinkedList class  is the implementation we need, or whatever we need!!! Other class that impliment List interface, ArrayList, Vector, Customer, Stack, etc...

>Strings & equals

**never compare string with ==**
```
String brand="Pepe";
String brand1="pepe";
return brand ==brand2;//ERROR, THEY COMPARE MEMORY LOCATION
return brand.equals(brand2);//CORRECT
```

>IFs.

BAD:
```
var bool="a".equals("A");//result is true || false
if(bool==true){
..
}
```

CORRECT:
```
if (bool){
return true;
}

if(!bool){
return false;
}
```
**use bool or !bool**
**We can use ternary operator**
```
return age>= 18 ? "Adult" :  "Child";
```

>Statics()

If we are in:
```
public class Mistakes{

    public static void main (Strings[] args){

    statics(); //ERROR, we can`t use statics, here we have 2 options
    //1st option, if we need a new instance (new Mistakes()) of Mistakes
    new Mistakes().statics();
    
    ....
    //2nd option, now we don't need a instance 
    statics();

    }
    //2nd option, we don't need a new instance of Mistakes, we make static statics()
    private static void statics(){
    
    }
    
    }
```

>Switch()

Don't forget break; after a case:
```
swith (caseIndex){
case 0:
    System.out.println("zero");
    //break; //<-------------
    case 1:
    System.out.println("one");
    break;
default:
    System.out.println("default");


}
```

>Excessive_garbage_allocation. **StringBuilder**

```
private void excessive_garbage_allocation(){
String out ="";
    for (int i=0; i<1_000_000; i++){ 
    out +=i;//Error, we create a million of new Strings!!!
    }

System.out.println(out);
}
```
Better use:
```
StringBuilder out = new StringBuilder();
    for (int i=0; i<1_000_000; i++){ 
    out.append(i);//Better
    }
```


# Ternary operator

# GENERICS

# stop using for loops

[](https://www.youtube.com/watch?v=-640IYSEnVE&ab_channel=Amigoscode)

#10 BAD PROGRAMMING HABITS
[](https://www.youtube.com/watch?v=lyx7HNufwXQ&ab_channel=Amigoscode)