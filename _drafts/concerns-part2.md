They tell us to write code that:
1. Has a single responsibility,
2. Is loosely coupled,
3. Relies on public interfaces, and
4. Makes appropriate use of composition, inheritance, and polymorphism.

Let's consider each of these in turn, and we're actually going to start with the last bullet point:

### Make Appropriate use of Composition, Inheritance, and Polymorphism

#### Inheritance
Inheritance can be defined as an "is a" relationship and is useful when we need to relate objects in obvious hierarchies.

[TODO: image here]

#### Composition
Composition can be thought of as a "has a" relationship, and we should reach for this tool when we need the functionality of an object but it doesn't make sense for use to be a relative of that object.

[TODO: image here]

#### Polymorphism
We can think of polymorphism as a "behaves like a" contract, something we saw earlier when discussing concerns and said that they facilitate behavior sharing.

[TODO: image here]

### Write Code that Has a Single Responsibility
We could write an entire series of blog posts on any of these concepts, but in short we can write single responsibility code by:
- Depending on behavior, not data or data structures.
- Ensuring both classes and methods have a single responsibility (i.e., separating iteration and action is a great way to accomplish this in your methods!)
- Isolationg our code such that it can change without consequence and be reused without duplication.

At the end of the day, we can achieve single responsibility by having a Q&A with our code, asking it, "What do you do?" until we get an answer that indicates our code is indeed focused on a single responsibility.

### Write Code that is Loosely Coupled
We achieve this by having our code only depend on things that change less often than we do. Examples of these types of things include public interfaces and APIs. This leads nicely to...

### Program to an Interface, not an Implementation
Restaurants are a great example of this. Rather than popping into the kitchen to help the chef make your food, (most) restaurants provide a handy interface to their kitchen called a menu. Customers communicate with the kitchen via this shared interface, sending a message of their desired menu item and (hopefully!) receiving it as-ordered from the kitchen.

[TODO: image here]

When programming to an interface, what we are in effect doing is asking for what we want, not telling how to do it.

But this fact highlights the importance of interfaces as the interface determines what messages can be responded to.

For example, the Chinese restaurant most likely does not list "breadsticks" as one of the messages that it knows how to respond to, any more than your local Olive Garden can respond to a request for fortune cookies.

### The Fundamental Design Question
Applying this mindset to our code, we can think of classes and methods much like restaurants that only understand the items listed on their menus.

Interestingly, this more than just a fun exercise. In her amazing book _Practical Object-Oriented Design in Ruby_, Sandy Metz writes:

> This transition from class-based design to message-based design is a turning point in your design career. The message-based perspective yields more flexible applications than does the class-based perspective.
>
> Changing the fundamental design question from, "I know I need this class, what should it do?" to, "I need to send this message, who should respond to it?"
is the first step in that direction.

Let me highlight that last bit, just so we don't miss it:

> "I need to send this message, who should respond to it?"

To help us solidy this mindset, let's borrow a meme, but first some context:

[TODO: video link here]

Steve can help us out here:

[TODO: image here]

Going back to our restaurant example, if we want pizza and the restaurant can respond to the "pizza" message, then that's all we really care about!

And perhaps this emphasis on behavior seems familiar:

[TODO: image here]

Going back to our family fun park example:

[TODO: image here]

These objects behave like a `Bookable`...

I.e., we can treat these objects like `Bookables`...

I.e., we can send them `Bookable` messages and they know how to respond!

In other words...

```
Sending & Responding to Messages
=
Polymorphism!
```

Once again, the only thing that a consumer cares about is whether or not an object responds to the message it wants to send, which leads to the famous saying:

> If it walks like a duck and talks like a duck, you can treat it like a duck!

This is a concept known as "Duck Typing" aka. polymorphism in practice:

> A "duck type" defines an interface or role that responds to a given set of messages and is:
>
> - A central location for logic
> - Adoptable by any object that needs to play the role

Does the above sound familiar to anyone...?

Remember earlier when we said that:

> A well-designed concern reaps the benefits of shared **code** while minimizing dependency

Well, here's another way of saying the same thing:

> A well-designed concern reaps the benefits of shared **a shared role** while minimizing dependency

Because, you see, a concern allows a class to play a role. And any class that includes a concern can now respond to all messages that the concern (role) understands.

In other words, classes that include a concern take on duck type (aka. polymorphic) behavior!

### So...?
Remember earlier when we took a detour? It was to get here, where we can say that a concern allows a class to play a role. This means that the class including a concern can now respond to all of the messages that the concern's role understands.

But for this insight to pack its full punch, we needed to understand why messages are so important because recall that message-based thinking is what allows us to write flexible applications that can easily adapt to change.

### And the all lived...
It would be nice if we could end the story here, but if you've been working in software for any length of time and had to work with concerns, then you know that there's more to the story.

To help illustrate, here is some real-world footage of developers trying to use concerns:

[TODO: image here]

### Finding the Footguns
Recall that earlier when discussing the importance of messages, we said that it's a good idea to ask, "Who is responsible for responding to this message?" [TODO]

Well consider this diagram:

[TODO: image here]

Above, we can see how a message-based view of things pretty quickly uncovers the latent complexity in this architecture. Also recall when we compared the diagram of inheritance to that of a concern and how we said that the relationship/dependency created by using a concern is much less explicit than that created when using inheritance. And that leads us to our first footgun:

> Footgun #1: Using concerns increases the complexity of an application.

### It Doesn't End There...
Consider this diagram:

[TODO: image here]

All is well and good until the junior on the team gets a ticket to allow users to be deleted and now our code looks like this:

[TODO: image here]

To summarize this problem:

[TODO: image here]

> Footgun #2: Concerns are misused when they are included for their functionality and not because we want our class to play a role. I.e., only include a concern in your class if you want your class to respond to all of the messages that that concern's role understands!

### TL;DR
You're probably surprised to read this in a blog post about concerns, but really the TL;DR from my years in the industry is:

> Don't use concerns.

I'm not saying that polymorphism/duck typing is bad, but rather that concerns are an error-prone implementation of these concepts.

So, seriously….

> Don’t use concerns!

If you have to use them...try something else first!

OK, if you must...

[TODO: image here]

We here at Maxwell have come up with this handy template we have our developers fill out any time they want to use a concerns:

What could possibly go wrong...

[TODO: image here]

Or...
 