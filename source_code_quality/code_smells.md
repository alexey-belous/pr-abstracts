# Code smells

## Code duplicates
Code should be moved into one place and called from other places instead of duplication.

## Long method
If you have to write comments for parts of some method, it'd better to divide such method on smaller methods with meaningful names.

## Big class
Big classes usually takes a lot of responsibilities, therefore, they can be divided into a smaller classes.

## Long list of parameters
It's better to send object, that groups a big amount of parameters instead of have a bit list of parameters in a method.

## Divergent modifications
Actually, it should be handled by Single responsibility principle of SOLID, that tells, that there should only one reason to change the class. In other cases class should be divided.

## Groups of data
Fields, that are usually defined together in the several classes must be united into dedicated class.

## "Switch" operator
Switch operators usually can be replaced by polymorphism or another design patters.

## Parallel inheritance hierarchies
It's when creation a new class in one hierarchy leads to creation of a new class in another hierarchy.

## Lazy-class
Class that doesn't provide a profit of its usage anymore, or was created for a change, that was declined. Fixes: "Collapse hierarchy" or "Inline class".

## Over Engineering

## Chains of messages
It's when one class is depend on structure of other classes. In this case the structure must be incapsulated.

## Mediator
When some class delegates all its functionality to another class. In this case mediator must be removed.

## Comments
Comments in code are usually indicates, that code should be refactored. And after refactoring comments may become useless.