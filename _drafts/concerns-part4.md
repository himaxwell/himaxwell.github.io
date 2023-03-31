Hello and welcome back to part four of our "Concerns in Ruby" blog post series. Here's a quick recap of what we've covered so far:

1. In [part one](), we stated that we want to understand what concerns are and how to use them well with the end goal being to write good code.
1. We defined "good code" as code that can change inexpensively.
1. In [part two](), we discussed a number of clean coding principles and learned that message-based designs are inexpensively changeable.
1. Thus, message-based design is our goal: When creating software, we want to think about our code in terms of:
    - The messages that get sent and 
    - Who is responsible for responding to them.
1. In [part three](), we learned that when we include a concern in our class we are taking on a role and thereby enabling our class to respond to all of the messages that the concern understands.
1. We also learned that this is _not_ optional: Concerns enable duck typing in the classes that include them, which means these classes have taken on polymorphic behavior and must now adhere to a "behaves like a" contract.
1. We ended part three by stating that concerns are an error-prone implementation of the concepts of duck typing/polymorphism since they are an inherently complex concept and place so much of the onus of using them correctly on the individual developer. This left us asking if maybe there exists _something_ that will allow us to reap some of the same benefits as concerns without the drawbacks.

Spoiler: There is! And that _something_ is the topic of today's post.

## Dramatic Plot Twist

[Matrix red / blue pill meme]

In the Ruby community, you'll find a lot of pushback and general looking down the nose at anything that smacks of Java, PHP, or any language that competed with Ruby circa 2010. That's because so many Ruby programmers are refugees from other languages where the development experience was often truly awful.

You'll often read of developers discovering Ruby and in the process re-discovering their love of programming and computers in general. Most if not all other programming languages don't list "developer happiness" as one of their design goals like Ruby does, and it really shows once you start working with the language.

In their newfound zeal and enthusiasm, these developers often chuck memories of their pre-Ruby languages into the bin of bad experiences and move on, hoping never to look back. So you can imagine that, when something tingles the neurons of the bad old days, many Ruby devs have a knee-jerk response of scorn, disdain, or simply running away with their ears covered.

Sadly, this state of affairs prevents us from borrowing the good and leaving the bad from other languages. One of the major casualties of this mindset is the idea of "service classes."

## No Folder for Old Men

The fact that a standard Rails installation doesn't have an `app/services` folder by default speaks to the fact that service classes are quite often viewed as second-class citizens in Ruby. They are often viewed as too-Java-ish, and you'll find liberal use of concerns in most Ruby projects and in the Rails codebase itself.

But, as we've already seen, there are a lot of issues with concerns, and, perhaps controversially, I would state:

> Anything that a concern can do, a service class can also do...but probably **better**.

[shots fired meme]

Before we go any further though, let's define what a "service class" is:

> A service class is a:
> - Regular old class
> - That is composable with other classes
> - That has a single purpose denoted by an unambiguous name.

### Regular Old Class

There's nothing special or magical about service classes. Unlike concerns which are polymorphism in practice, they are not inherently tied to a particular object oriented programming paradigm, although they are free to make use of any and all paradigms as appropriate.

```
class UserNotifier
end
```

### Composable With Other Classes

Since a service class performs a function, it can be composed into any class that needs the service class's functionality. A service class can also be swapped out with any other class that implements the same public API, i.e., can respond to the same set of messages.

```
# Composition example here
class MyClass
  def initialize
    @user_notifier = UserNotifier.new
  end
end
```