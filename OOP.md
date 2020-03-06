#### Some basic programming concepts in OOP

* The abstraction is simplifying complex reality by modeling classes appropriate to the problem. 

* The polymorphism is the process of using an operator or function in different ways for different data input. 

* The encapsulation hides the implementation details of a class from other objects. 

* The inheritance is a way to form new classes using classes that have already been defined.

An instance is a specific object created from a particular class.

* It is a convention to give classes a name that starts with a capital letter.

Inside a class, we can define attributes and methods. Technically, attributes are variables and methods are functions defined inside a class.
	An attribute is a characteristic of an object. This can be for example a salary of an employee. 
	A method defines operations that we can perform with our objects. A method might define a cancellation of an account.

A special method called __init__() is used to initialize an object.
* Attributes are set in the __init__() method.
Each method in a class definition begins with a reference to the instance object. It is by convention named self. There is nothing special about the self name. 
The second parameter is the argument. The value is passed during the class initialization.
``` python
def __init__(self, name):
  self.name = name
```
The attributes can be assigned dynamically, not just during initialization. This is demonstrated by the next example.
``` python
class Person:
    pass

p = Person()
p.age = 24
p.name = "Peter"

print("{0} is {1} years old".format(p.name, p.age))
```
Class object attributes are same for all instances of a class. The attribute is defined outside any method name in the body of a class.

Methods are functions defined inside the body of a class. They are used to perform operations with the attributes of our objects.

In Python, we can call methods in two ways. There are bounded and unbounded method calls.

Bounded method call. The Python interpreter automatically pairs the m instance with the self parameter.
```python
print(m.getName())
```
Unbounded method call. The instance object is explicitly given to the getName() method.
```python
print(Methods.getName(m))
```
#### Python inheritance
Inheritance is a way to form new classes using classes that have already been defined. The newly formed classes are called derived classes, the classes that we derive from are called base classes.  The derived classes (descendants) override or extend the functionality of base classes (ancestors).
```python
# In this example, we have two classes: Animal and Dog. The Animal is the base class, the Dog is the derived class. The derived class inherits the functionality of the base class. It is shown by the eat() method. The derived class modifies existing behaviour of the base class, shown by the whoAmI() method. Finally, the derived class extends the functionality of the base class, by defining a new bark() method.
# inheritance.py

class Animal:

    def __init__(self):
        print("Animal created")

    def whoAmI(self):
        print("Animal")

    def eat(self):
        print("Eating")

# We put the ancestor classes in round brackets after the name of the descendant class.
class Dog(Animal):
# f the derived class provides its own __init__() method and we want to call the parent constructor, we have to explicitly call the base class __init__() method with the help of the super function.
    def __init__(self):
        super().__init__()
          print("Dog created")

    def whoAmI(self):
        print("Dog")

    def bark(self):
        print("Woof!")

d = Dog()
d.whoAmI()
d.eat()
d.bark()
```
#### Python polymorphism
Polymorphism is the process of using an operator or function in different ways for different data input. In practical terms, polymorphism means that if class B inherits from class A, it doesn't have to inherit everything about class A; it can do some of the things that class A does differently. Polymorphism is mostly used when dealing with inheritance.
```python
# polymorphism.py
# Here we have two species: a dog and a cat. Both are animals. The Dog class and the Cat class inherit the Animal class. They have a talk() method, which gives different output for them.
class Animal:
    
   def __init__(self, name=''):
       
      self.name = name

   def talk(self):
       
      pass

class Cat(Animal):
    
   def talk(self):
       
      print("Meow!")

class Dog(Animal):
    
   def talk(self):
       
      print("Woof!")

a = Animal()
a.talk()

c = Cat("Missy")
c.talk()

d = Dog("Rocky")
d.talk()
```

