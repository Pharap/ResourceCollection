# Program Architecture

## Objects Should Not Draw Themselves

Generally objects shouldn't know how to draw themselves.
Generally there should be dedicated objects or functions responsible for drawing other objects.

By making another object responsible for rendering,
it is possible to choose different rendering strategies,
thus producing more flexible code.

Concrete questions with concrete answers:

* [An answer to "Should actors in a game be responsible for drawing themselves?"](https://gamedev.stackexchange.com/a/14138)
* [What's wrong with the architecture of a game object drawing and updating itself?](https://stackoverflow.com/questions/3000525/whats-wrong-with-the-architecture-of-a-game-object-drawing-and-updating-itself)

For a more abstract look at the problem:

* [An answer to "Should every object know how to present/draw themselves?"](https://softwareengineering.stackexchange.com/a/314183)

One _potential_ exception to this rule is in GUI programming where controls within the GUI might be responsible for drawing themselves,
but this is an _exception_, not the rule, and it's not always true, it depends on the circumstances.

## Inheriting To Avoid Code Duplication Or To Inherit Functionality is Generally Bad

The point of inheritance is not to facilitate code reuse through inheriting a parent class's code.
The intent of inheritance is to facilitate "[subtype polymorphism](https://en.wikipedia.org/wiki/Subtyping)" and consequently "[Liskov substitution](https://en.wikipedia.org/wiki/Liskov_substitution_principle)".

Inheritance does facilitate code reuse, but not directly via inheriting a parent class's code.
It facilitates code reuse by allowing algorithms to be written for a particular interface (embodied by the parent class),
so that child objects inheriting the parent can then be passed to the function implementing that algorithm.

* [An answer to "Code Smell: Inheritance Abuse"](https://softwareengineering.stackexchange.com/a/12446)
