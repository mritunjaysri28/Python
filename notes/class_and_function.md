Official Page: https://docs.python.org/3/library/functions.html
 
# Class
The first step in creating a class is giving it a name. 
create two classes: Circle and Rectangle. We need to determine all the data that make up that class, which we call attributes. Think about this step as creating a blue print that we will use to create objects. In figure 1 we see two classes, Circle and Rectangle. Each has their attributes, which are variables. The class Circle has the attribute radius and color, while the Rectangle class has the attribute height and width. Let’s use the visual examples of these shapes before we get to the code, as this will help you get accustomed to the vocabulary.

```python
class className:
    pass
```

# What is a Function?
You can define functions to provide the required functionality. Here are simple rules to define a function in Python:

Functions blocks begin def followed by the function name and parentheses ().
There are input parameters or arguments that should be placed within these parentheses.
You can also define parameters inside these parentheses.
There is a body within every function that starts with a colon (:) and is indented.
You can also place documentation before the body.
The statement return exits a function, optionally passing back a value.

```python
def functionName():
    pass
```

# Parametric Function
The input to a function is called a formal parameter.

A variable that is declared inside a function is called a local variable. The parameter only exists within the function (i.e. the point where the function starts and stops).

A variable that is declared outside a function definition is a global variable, and its value is accessible and modifiable throughout the program. We will discuss more about global variables at the end of the lab.


# Arbitrary Arguments
When the number of arguments are unknown for a function, They can all be packed into a tuple
```python
def printAll(*args): # All the arguments are 'packed' into args which can be treated like a tuple
    print("No of arguments:", len(args)) 
    for argument in args:
        print(argument)

#printAll with 3 arguments
printAll('Horsefeather','Adonis','Bone')
#printAll with 4 arguments
printAll('Sidecar','Long Island','Mudslide','Carriage')
```

# Arbitrary Keyword Arguments, **kwargs
Arguments can also be packed into a dictionary
```python 
def printDictionary(**args):
    for key in args:
        print(key + " : " + args[key])

printDictionary(Country='Canada',Province='Ontario',City='Toronto')
```

# Special Methods (Dunder methods)
Python special methods begin and end with a double underscore and are informally known as dunder methods. Dunder methods are the underlying methods for Python’s built-in operators and functions. You should avoid calling dunder methods directly, and instead implement the dunder methods in your class and then use the built-in functions that call them

# Constructor - ```__init__()```
```__init__()``` which is used to initialize the object. The inputs are data attributes. The term self contains all the attributes in the set. All classes have a function called ```__init__()```, which is always executed when the class is being initiated.
For example the self.color gives the value of the attribute color and self.radius will give you the radius of the object. We also have the method ```add_radius()``` with the parameter r, the method adds the value of r to the attribute radius. To access the radius we use the syntax self.radius.

# ```__str__()```
if return value is string, this function can use to control what need to be return
```python
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age

  def __str__(self):
    return f"{self.name}({self.age})"

p1 = Person("John", 36)

print(p1)
```

# ```__repr__()```
Return a string containing a printable representation of an object. if you pass the returned string of the object_name. ```__repr__()``` method to the ```eval()``` function, you’ll get the same value as the object_name
```python
class Person:
    def __init__(self, first_name, last_name, age):
        self.first_name = first_name
        self.last_name = last_name
        self.age = age

    def __repr__(self):
        return f'Person("{self.first_name}","{self.last_name}",{self.age})'

    def __str__(self):
        return f'({self.first_name},{self.last_name},{self.age})'


person = Person('John', 'Doe', 25)
# use str()
print(person)

# use repr()
print(repr(person))

```
