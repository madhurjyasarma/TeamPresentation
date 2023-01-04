# TeamPresentation - S.O.L.I.D.
## Java Code, PPT and Explaination in the repo.
## Team Members - Madhurjya Goutam sarma, Chandan kumar, Sourav Mittal, Jayesh Pagare


SOLID is an acronym that stands for five design principles intended to make software designs more understandable, flexible, and maintainable:

Single Responsibility Principle: A class should have only one reason to change. This means that a class should have a single, well-defined responsibility, and that responsibility should be entirely encapsulated by the class.

Open-Closed Principle: Software entities (classes, modules, functions, etc.) should be open for extension but closed for modification. This means that you should be able to add new functionality to a class without changing its existing code.

Liskov Substitution Principle: Subtypes must be substitutable for their base types. This means that if a class is derived from another class, it should be able to be used in the same way as the base class without causing any issues.

Interface Segregation Principle: Clients should not be forced to depend on interfaces they do not use. This means that a class should not implement interfaces that contain methods that the class does not use.

Dependency Inversion Principle: High-level modules should not depend on low-level modules. Both should depend on abstractions. This means that you should depend on abstractions, rather than on concrete implementations.

These principles can help you design software that is more flexible, maintainable, and easy to understand.

### Single Responsibility Principle
```
class Circle:
    def __init__(self, radius):
        self.radius = radius
    def calculate_area(self):
        return 3.14 * self.radius * self.radius
    def calculate_circumference(self):
        return 2 * 3.14 * self.radius
# This class has a single responsibility: to represent a circle and provide methods
# for calculating the area and circumference of the circle.
```

### Open-Closed Principle
```
class Shape:
    def area(self):
        pass
class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    def area(self):
        return self.width * self.height
class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    def area(self):
        return 3.14 * self.radius * self.radius
# The Shape class is open for extension (you can create new shapes by subclassing
# the Shape class) but closed for modification (you don't have to change the Shape
# class itself to add new shapes).
```

### Liskov Principle
```
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height
    def area(self):
        return self.width * self.height
class Square(Rectangle):
    def __init__(self, side_length):
        self.width = side_length
        self.height = side_length
    # This method violates the Liskov Substitution Principle because it changes
    # the behavior of the area method inherited from the Rectangle class.
    def area(self):
        return self.width * self.width
# If you have a function that expects a rectangle and you pass it a square, the
# function will not work as expected because the square's area method has a different
# behavior than the rectangle's area method.
```

### Interface Segregation Principle
```
class Shape:
    def area(self):
        pass
    def perimeter(self):
        pass
class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    def area(self):
        return 3.14 * self.radius * self.radius
# The Circle class is forced to implement the perimeter method, even though a
# circle does not have a perimeter. This violates the Interface Segregation Principle.
```

### Dependency Inversion Principle
```
class Circle:
    def __init__(self, radius):
        self.radius = radius
    def area(self):
        return 3.14 * self.radius * self.radius
class ShapeCalculator:
    def __init__(self, shape):
        self.shape = shape
    def calculate_area(self):
        return self.shape.area()
# The ShapeCalculator
```
