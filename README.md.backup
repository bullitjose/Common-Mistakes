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

Una classe Box senzilla Comenceu examinant una classe Box no genèrica que opera amb objectes de qualsevol tipus. Només necessita proporcionar dos mètodes: set , que afegeix un objecte a la caixa, i get , que el recupera:

```
public class Box { 
    object object privat; 

    public void set(Object object) { this.object = object; } 
    objecte públic get() { objecte de retorn; } 
}


```
Una versió genèrica de la classe Box

**Una classe genèrica es defineix amb el format següent:**

```
nom de classe<T1, T2, ..., Tn> { /* ... */ }
```

La secció de paràmetres de tipus, delimitada per claudàtors angulars ( <> ), segueix el nom de la classe. Especifica els paràmetres de tipus (també anomenats variables de tipus ) T1 , T2 , ... i Tn .

Per actualitzar la classe Box per utilitzar genèrics, creeu una declaració de tipus genèric canviant el codi " public class Box " a " public class Box<T> ". Això introdueix la variable de tipus, T , que es pot utilitzar en qualsevol lloc de la classe.

Amb aquest canvi, la classe Box passa a ser:
```

/** 
 * Versió genèrica de la classe Box. 
 * @param <T> el tipus del valor que s'encaixa 
 */ 
public class Box<T> { 
    // T significa "Type" 
    private T t; 

    public void set(T t) { this.t = t; } 
    public T get() { return t; } 
}
```
 Una variable de tipus pot ser qualsevol tipus **no primitiu**que especifiqueu: qualsevol tipus de classe, qualsevol tipus d'interfície, qualsevol tipus de matriu o fins i tot una altra variable de tipus.
 
 
 
>Type Parameter Naming Conventions

By convention, type parameter names are single, uppercase letters. This stands in sharp contrast to the variable naming conventions that you already know about, and with good reason: Without this convention, it would be difficult to tell the difference between a type variable and an ordinary class or interface name.

The most commonly used type parameter names are:

E - Element (used extensively by the Java Collections Framework)
K - Key
N - Number
T - Type
V - Value
S,U,V etc. - 2nd, 3rd, 4th types

>Invocació i instància d'un tipus genèric
Per fer referència a la classe Box genèrica des del vostre codi, heu de realitzar una invocació de tipus genèric , que substitueixi T amb algun valor concret, com ara Integer :

```
Box<Enter> integerBox;
```
Podeu pensar que una invocació de tipus genèric és similar a una invocació de mètode ordinària, però en comptes de passar un argument a un mètode, esteu passant un argument de tipus ( Enter en aquest cas) a la pròpia classe Box .
Com qualsevol altra declaració de variable, aquest codi en realitat no crea un nou objecte Box . Simplement declara que integerBox mantindrà una referència a un " Box of Integer ", que és com es llegeix Box<Integer> .

Una invocació d'un tipus genèric es coneix generalment com a tipus parametritzat .

>El Diamant <>

Podeu substituir els arguments de tipus necessaris per invocar el constructor d'una classe genèrica per un conjunt buit d'arguments de tipus (<>) sempre que el compilador pugui determinar, o inferir, els arguments de tipus a partir del context. . Aquest parell de mènsules angulars, <>, s'anomena informalment el diamant . Per exemple, podeu crear una instància de Box<Integer> amb la instrucció següent:


```
Box<Enter> integerBox = new Box<>();
```

>Múltiples paràmetres de tipus

Com s'ha esmentat anteriorment, una classe genèrica pot tenir diversos paràmetres de tipus. Per exemple, la classe genèrica OrderedPair , que implementa la interfície genèrica Pair :
```

interfície pública Pair<K, V> { 
    public K getKey(); 
    public V getValue(); 
} 

classe pública OrderedPair<K, V> implementa Pair<K, V> { 

    clau privada K; 
    valor V privat; 

    public OrderedPair (clau K, valor V) { 
	this.key = clau; 
	this.value = valor; 
    } 

    public K getKey() { clau de retorn; } 
    public V getValue() { valor de retorn; } 
}
```
Les declaracions següents creen dues instàncies de la classe OrderedPair :

Pair<String, Integer> p1 = new OrderedPair<String, Integer>("Parell", 8); 
Pair<String, String> p2 = new OrderedPair<String, String>("hola", "món");

Com s'esmenta a The Diamond , com que un compilador Java pot inferir els tipus K i V de la declaració OrderedPair<String, Integer> , aquestes declaracions es poden escurçar utilitzant la notació de diamant:
```

OrderedPair<String, Integer> p1 = new OrderedPair <> ("Parell", 8); 
OrderedPair<String, String> p2 = new OrderedPair <> ("hola", "món");
```


 For example, the List interface has a single type parameter, E, representing its element type.
 For example, List<String> (read “list of string”) is a parameterized type
representing a list whose elements are of type String. (String is the actual type parameter corresponding to the formal type parameter E.)


En afegir l'operador de diamant <> que conté el tipus, reduïm l'especialització d'aquesta llista només al tipus Enter:
```
List<Integer> list = new LinkedList<>();
```
>Mètodes genèrics.
Escrivim mètodes genèrics amb una única declaració de mètode, i els podem cridar amb arguments de diferents tipus.
Tingueu en compte que la recomanació d'Oracle és utilitzar una lletra majúscula per representar un tipus genèric i triar una lletra més descriptiva per representar els tipus formals. A les col·leccions Java, utilitzem T per a tipus, K per a clau i V per valor.

>Tipus crus o Raw types.

Un tipus en brut és el nom d'una classe o interfície genèrica **sense cap argument de tipus**. Per exemple, donada la classe Box genèrica :

```
public class Box<T> {
   public void set (T t) { /* ... */ }
    //...
}
```

Per crear un tipus parametritzat de Box<T> , proporcioneu un argument de tipus real per al paràmetre de tipus formal T :
```
Box<Integer> intBox = new Box<>();
```
Si s'omet l'argument del tipus real, creeu un tipus brut de Box<T> :
```
Box  rawBox = new Box ();
```

Per tant, **Box és el tipus en brut del tipus genèric Box<T>** . Tanmateix, una classe no genèrica o un tipus d'interfície no és un tipus en brut.

>Wildcards o Comodins

En el codi genèric, el signe d'interrogació ( ? ), anomenat comodí , representa un tipus desconegut. El comodí es pot utilitzar en una varietat de situacions: com a tipus de paràmetre, camp o variable local; de vegades com a tipus de retorn. El comodí no s'utilitza mai com a argument de tipus per a una invocació de mètode genèric, la creació d'una instància de classe genèrica o un supertipus.

>Upper Bounded Wildcards o comodins amb limit superior
You can use an upper bounded wildcard to relax the restrictions on a variable. For example, say you want to write a method that works on List<Integer>, List<Double>, and List<Number>; you can achieve this by using an upper bounded wildcard.

To declare an upper-bounded wildcard, use the wildcard character ('?'), followed by the extends keyword, followed by its upper bound. Note that, in this context, extends is used in a general sense to mean either "extends" (as in classes) or "implements" (as in interfaces).

To write the method that works on lists of Number and the subtypes of Number, such as Integer, Double, and Float, you would specify **List<? extends Number>**. The term List<Number> is more restrictive than List<? extends Number> because the former matches a list of type Number only, whereas the latter matches a list of type Number or any of its subclasses.

>Unbounded Wildcards o Comodins il·limitats
El tipus de comodí il·limitat s'especifica mitjançant el caràcter comodí ( ? ), per exemple, List<?> . Això s'anomena llista de tipus desconegut . Hi ha dos escenaris en què un comodí il·limitat és un enfocament útil:

- Si esteu escrivint un mètode que es pot implementar mitjançant la funcionalitat proporcionada a la classe Object .
- Quan el codi utilitza mètodes de la classe genèrica que no depenen del paràmetre tipus. Per exemple, List.size o List.clear . De fet, Class<?> s'utilitza sovint perquè la majoria dels mètodes de Class<T> no depenen de T .

>Restriccions als genèrics

Per utilitzar els genèrics Java de manera eficaç, heu de tenir en compte les restriccions següents:

- No es poden instanciar tipus genèrics amb tipus primitius

    When creating a Pair object, you cannot substitute a primitive type for the type parameter K or V:
    
    ```
    Pair<int, char> p = new Pair<>(8, 'a');  // compile-time error
    ```
    
    You can substitute only non-primitive types for the type parameters K and V:
    ```
    
    Pair<Integer, Character> p = new Pair<>(8, 'a');
    ```
    
    Note that the Java compiler autoboxes 8 to Integer.valueOf(8) and 'a' to Character('a'):
    
    You cannot create an instance of a type parameter. For example, the following code causes a compile-time error:
    ```
    public static <E> void append(List<E> list) {
        E elem = new E();  // compile-time error
        list.add(elem);
    }
    ```
    
    As a workaround, you can create an object of a type parameter through reflection:
   
  ```  
    public static <E> void append(List<E> list, Class<E> cls) throws Exception {
        E elem = cls.newInstance();   // OK
        list.add(elem);
    }
    ```
- No es poden crear instàncies de paràmetres de tipus


- No es poden declarar camps estàtics els tipus dels quals són paràmetres de tipus
- No es poden utilitzar casts o instanceof amb tipus parametritzats
- No es poden crear matrius de tipus parametritzats
     You cannot create arrays of parameterized types. For example, the following code does not compile:
```
List<Integer>[] arrayOfLists = new List<Integer>[2];  // compile-time error
```
- No es poden crear, atrapar o llançar objectes de tipus parametritzats
- No es pot sobrecarregar un mètode on els tipus de paràmetres formals de cada sobrecàrrega s'esborren al mateix tipus en brut



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

> How to **(Items) maximize the benefits and minimize the complications with generics**, you tell the compiler what types of objects are permitted in each collection.
[Effective Java.pdf]

 >Item 28: Prefer lists to arrays
        
 >Item 29: Favor generic types
        
Generic types are safer and easier to use than types that require casts in client code. When you design new types, make sure that they can be used without such casts. This will often mean making the types generic. If you have any existing types that should be generic but aren’t, generify them. This will make life easier for new users of these types without breaking existing clients (Item 26).
       > Item 30: Favor generic methods
         The most commonly used type parameter names are:
    
  E - Element (used extensively by the Java Collections Framework)
  K - Key
  N - Number
  T - Type
  V - Value
   S,U,V etc. - 2nd, 3rd, 4th types
   
 Just as classes can be generic, so can methods. Static utility methods that operate on parameterized types are usually generic. All of the “algorithm” methods in Collections (such as binarySearch and sort) are generic.
         
    ```
         // Generic method
public static <E> Set<E> union(Set<E> s1, Set<E> s2) {
Set<E> result = new HashSet<>(s1);
result.addAll(s2);
return result;
}
     
   modify its declaration to declare a type parameter representing the element type for the three sets (the two arguments and the return value) and use this type parameter throughout  the method. The type parameter list, which declares the type parameters, goes between a method’s modifiers and its return type. In this example,**the type parameter list is <E>, and the return type is Set<E>.**
  
   ```
   // Generic method
public static <E> Set<E> union(Set<E> s1, Set<E> s2) {
Set<E> result = new HashSet<>(s1);
result.addAll(s2);
return result;
}
```

   > Item 31: Use bounded wildcards to increase API flexibility
      
 > Item 32: Combine generics and varargs judiciously
 
 >Item 33: Consider typesafe heterogeneous containers
   
   

# stop using for loops
**with: sets, maps, better use .stream()**, and .collect(Collectors.toSet())
**also use iterator**

[STOP USING FOR LOOPS](https://www.youtube.com/watch?v=-640IYSEnVE&ab_channel=Amigoscode)

# 10 BAD PROGRAMMING HABITS
[10 BAD PROGRAMMING HABITS](https://www.youtube.com/watch?v=lyx7HNufwXQ&ab_channel=Amigoscode)

