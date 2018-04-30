Property:

Datastructure **directly** show its data nature by datastructure.x ..etc.

Object just provide his **abstract manipulation interface** of data-nature.  like drawX,drawY is**poor** for abstract manipulation interface for a Graph.like drawPoint() is a good abstract manipulation interface.

**It helps the function or method only depend on the abstraction of the object which allow change in implementations smoothly.**

Usage:

Object is used in OO progrmming and datastructure is used in procedural programming.

Procedural programming is very descriptive when there is lots of procedural.

Object programming is very descriptive when there is lots of entity.

In a massive big system.Object and datastructure may coexist,but they never should be mixed to same item.**(like Data transfer object DTO and object and you shouldn't find a object that show his data-nature and abstract manipulation interface of data-nature to public in the same time.**

Adv:

Object  allow  you to add new object type easily,but need to take your more work when adding new function.

Datastructure is allow to add new function easily,but need to take massive work for you to add datastructure.

Rule:

Object function calling must follow **The Law of Demeter  aka (don't go party with your friend's friends(stranger))**

**The Law of Demeter means function or method only call direct entity(object itself and object passed in) function.**

**Which is an example of implementation of only know the abstract status of object.**

**Law of Demeter applys in function call.**

**method f of object C should only call **

**1.method of C,**

**2.Object create in f**

**3.object passed to f.but only directly call object method only.(x.getX().getY() is already know the implementation detail)(and talk to stranger)**