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
El primer operand ha de ser una expressió booleana , i el segon i tercer operands poden ser qualsevol expressió que retorni algun valor. La construcció ternària retorna expression1 com a sortida si el primer operand s'avalua com a true , expression2 en cas contrari:

```
booleanExpression ? expression1 : expression2

//Ex:
final String msg = num > 10 
  ?  "Number is greater than 10" 
  :  "Number is less than or equal to 10";

```

# GENERICS
[genericsl](https://docs.oracle.com/javase/tutorial/java/generics/types.html)

>Why Use Generics?
Els genèrics permeten que els tipus (classes i interfícies) siguin paràmetres a l'hora de definir classes, interfícies i mètodes. Igual que els paràmetres formals més familiars utilitzats en les declaracions de mètodes, els paràmetres de tipus ofereixen una manera de reutilitzar el mateix codi amb diferents entrades. La diferència és que les entrades als paràmetres formals són valors, mentre que les entrades als paràmetres de tipus són tipus.
El codi que utilitza genèrics té molts avantatges respecte al codi no genèric:

- Comprovacions de tipus més fortes en temps de compilació.
Un compilador de Java aplica una verificació de tipus forta al codi genèric i emet errors si el codi infringeix la seguretat de tipus. Corregir errors en temps de compilació és més fàcil que corregir errors en temps d'execució, que pot ser difícil de trobar.

- Eliminació de casts.
El següent fragment de codi sense genèrics requereix de casts:
```
Llista de llista = new ArrayList(); 
list.add("hola"); 
String s = (String) list.get(0);
```

Quan es torna a escriure per utilitzar genèrics, el codi no requereix casts:
```
List<String> list = new ArrayList<String>(); 
list.add("hola"); 
String s = list.get(0); // sense cast
```
- Permetre als programadors implementar algorismes genèrics.
Mitjançant l'ús de genèrics, els programadors poden implementar algorismes genèrics que funcionen en col·leccions de diferents tipus, es poden personalitzar i són segurs i fàcils de llegir.

>Tipus genèrics [genericsl](https://docs.oracle.com/javase/tutorial/java/generics/types.html)


>Type Parameter Naming Conventions
By convention, type parameter names are single, uppercase letters. This stands in sharp contrast to the variable naming conventions that you already know about, and with good reason: Without this convention, it would be difficult to tell the difference between a type variable and an ordinary class or interface name.

The most commonly used type parameter names are:

E - Element (used extensively by the Java Collections Framework)
K - Key
N - Number
T - Type
V - Value
S,U,V etc. - 2nd, 3rd, 4th types
[Effective Java.pdf]
 For example, the List interface has a single type parameter, E, representing its element type.
 For example, List<String> (read “list of string”) is a parameterized type
representing a list whose elements are of type String. (String is the actual type parameter corresponding to the formal type parameter E.)


En afegir l'operador de diamant <> que conté el tipus, reduïm l'especialització d'aquesta llista només al tipus Enter:
```
List<Integer> list = new LinkedList<>();
```
>Mètodes genèrics.
Escrivim mètodes genèrics amb una única declaració de mètode, i els podem cridar amb arguments de diferents tipus.
Tingueu en compte que la recomanació d'Oracle és utilitzar una lletra majúscula per representar un tipus genèric i triar una lletra més descriptiva per representar els tipus formals. A les col·leccions Java, utilitzem T per a tipus, K per a clau i V per valor
With generics, the type declaration contains the information, not the comment:

```
// Parameterized collection type - typesafe
private final Collection<Stamp> stamps = ... ;
```
From this declaration, the compiler knows that stamps should contain only Stamp instances and guarantees it to be true, assuming your entire codebase compiles without emitting  any warnings. When stamps is
declared with a parameterized type declaration, the erroneous insertion generates a compile-time error message that tells you exactly what is wrong:
it is legal to use raw types (generic types without their type 
parameters), but you should never do it. **If you use raw types, you lose all the safety and expressiveness benefits of generics.**

>Raw types.
A raw type is a name for a generic interface or class without its type argument:

```
List list = new ArrayList(); // raw type

List<Integer> listIntgrs = new ArrayList<>(); // parameterized type
```
**List<Integer> is a parameterized type of interface List<E> while List is a raw type of interface List<E>.**
**Els tipus en brut són difícils de treballar i poden introduir errors al nostre codi.**






# stop using for loops
**with: sets, maps, better use .stream()**, and .collect(Collectors.toSet())
**also use iterator**

[STOP USING FOR LOOPS](https://www.youtube.com/watch?v=-640IYSEnVE&ab_channel=Amigoscode)

# 10 BAD PROGRAMMING HABITS
[10 BAD PROGRAMMING HABITS](https://www.youtube.com/watch?v=lyx7HNufwXQ&ab_channel=Amigoscode)