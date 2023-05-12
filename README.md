>GIT HUB
## REPOSITORIO PROYECTO

Tenemos un proyecto Git en local, y lo subiremos a GitHub. En local tenemos la carpeta "Hello git" y en GitHub hemos creado el repositorio "hello-git"

+ remote, configuramos con que repositorio en github queremos que se asocie el git local:
```
$git remote add origin https://github.com/bullitjose/hello-git.git
```

+ push , subir el repositorio local (master) de git al remoto github (origin):
```
$git push -u origin master
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