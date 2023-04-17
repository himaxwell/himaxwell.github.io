Hello and welcome back to the final part of our "Concerns in Ruby" blog post series. Here's a quick recap of what we've covered so far:

1. In [part one](), we stated that we want to understand what concerns are and how to use them well with the end goal being to write good code.
1. We defined "good code" as code that can change easily and inexpensively.
1. In [part two](), we discussed a number of clean coding principles and learned that message-based designs are easily and inexpensively changeable.
1. Thus, message-based design became our goal: When creating software, we want to think about our code in terms of:
    - The messages that get sent and 
    - Who is responsible for responding to them.
1. In [part three](), we learned that when we include a concern in our class we are taking on a role and thereby enabling our class to respond to all of the messages that the concern's role understands.
1. We also learned that this is _not_ optional: Concerns enable duck typing in the classes that include them, which means these classes have taken on polymorphic behavior and must now adhere to a "behaves like a" contract.
1. We ended part three by stating that concerns are an error-prone implementation of the concepts of duck typing/polymorphism since they are an inherently complex concept and place so much of the onus of using them correctly on the individual developer. This left us asking if maybe there exists _something_ that will allow us to reap some of the same benefits as concerns without the drawbacks.

Spoiler: There is! And that _something_ is the topic of today's post.

## Dramatic Plot Twist

[Matrix red / blue pill meme]

In the Ruby community, you'll find a lot of pushback and general looking down the nose at anything that smacks of Java, PHP, or any language that competed with Ruby circa 2010. That's because so many Ruby programmers are refugees from other languages where the development experience was truly awful.

You'll often read of developers discovering Ruby and in the process re-discovering their love of programming and computers in general. Most if not all other programming languages don't list "developer happiness" as one of their design goals like Ruby does, and it really shows once you start working with the language.

Thus, often, in their newfound zeal and enthusiasm, budding Ruby devs will chuck the memories of their pre-Ruby language experiences into the bin where they store bad childhood memories and exs and move on, hoping never to look back. So you can imagine that, when something tingles the neurons of "the bad old days," many Ruby devs have a knee-jerk response of scorn, disdain, or simply running away with their ears covered.

Sadly, this state of affairs prevents us from borrowing the good and leaving the bad from other languages. In the Ruby community specifically, one of the major casualties of this mindset that "code must never remind me of Java" is the use of "service classes."

## No Country for Old Men, Nor Folder for Service Classes

The fact that a standard Rails installation doesn't even have an `app/services` folder by default speaks to the fact that service classes are quite often viewed as second-class citizens in Ruby. They are considered too Java-ish, and, while you'll find liberal use of concerns in most Ruby projects and in the Rails codebase itself, most Ruby projects don't consider service classes a vital tool in their arsenal.

But, as we've already seen, there are _a lot_ of issues with concerns, and, perhaps controversially, I would argue:

> Anything that a concern can do, a service class can also do...but probably **better**.

[shots fired meme]

Before we go any further though, let's define what a "service class" is:

> A "service class" is a:
> - Regular old Ruby class
> - That:
>     - Is composable with other classes,
>     - Has a single purpose,
>     - And is denoted by an unambiguous name.

Most of the arguments against using service classes actually point to the failure of a given service class to adhere to the above definition. Let's consider why each of the above is important.

### Service Classes are Regular Old Classes

There's nothing special or magical about service classes. Unlike concerns which are polymorphism in practice, service classes are not inherently tied to a particular object oriented programming paradigm, although they are free to make use of any and all paradigms as appropriate.

```ruby
# This service class is just a regular old Ruby class!
class UserNotifier
end
```

### Service Classes are Composable With Other Classes

Since a service class performs a function, it can be composed with any class that needs its functionality. A service class can also be swapped out with any other class that implements the same public API, i.e., can respond to the same set of messages.

This composability is where service classes really shine. If done properly, it yields very flexible and easy-to-change designs, something that we've seen is a hallmark of good code.

```ruby
# Here we compose a service class with our class
# although we could compose any class that responds
# to the messages we want to send
class AccountDeactivator
  def initialize
    @user_deleter = UserDeleter.new
  end
end
```

### Service Classes Have a Single Purpose

This is probably the biggest mistake most developers make when creating service classes. But this issue is often not seen in isolation. Instead, it is almost always accompanied by a violation of the guideline that...

### Service Classes Use Unambiguous Names

How often have you seen classes like `UserManager` or `EmailHelper` or some similar `SubjectVerb` naming scheme? Often, these classes are catch-alls for any functionality remotely related to the `Subject`.

For example, an `EmailHelper` service class will often store configuration for connecting to a mail server, contain methods for sending emails, and possibly even provide validation logic for email-related tasks. This is a flagrant violation of the "single responsibility" clean coding principle, but it's surprisingly common to find when working with service classes.

However, the root issue is often not that a developer is trying to ignore single responsibility. In fact, most would argue that their service class _is_ single purpose ("It's focused on email functionality!"). The confusion arises due to bad naming hygiene. It's here that I'd like to remind readers of the famous saying:

> There are 2 hard problems in computer science: cache invalidation, naming things, and off-by-1 errors.

Naming things _is_ really hard. But it is oh so worth it to get the names you use in your code right! An example will help prove this point.

Compare a generic `EmailHelper` class to any of the following:
- `EmailSender`
- `EmailValidator`
- `UserEmailSender`

It's pretty obvious at a glance what the purpose of each of these classes is, and it's probably even safe to assume that the `UserEmailSender` class inherits from the `EmailSender` class and contains `User`-specific specializations of that more generic class.

But what did we change to gain this increased clarity? Just the name we used for our class, right? So simple!

We went from using generic and ambiguous names ending in `Helper` and `Manager` and used specific, action-oriented names, and each class's purpose immediately became clear. Using descriptive names also has the added benefit of focusing classes such that developers will (hopefully) pause and ask themselves questions like, "Does an email validation method really belong in the `EmailSender` class?"

If you think about it, the number of positive outcomes here compared with the amount of effort we put in is happily disproportionate, so please use descriptive names for your service classes!

### What This Blog Post Series Has Lacked...

...is the egregious, even _concerning_ use of puns.

Sorry - couldn't resist throwing at least one out there. Great restraint has indeed been exercised thus far, but we are fast-approaching the end, so let's get the puns and final thoughts out of the way, shall we?

The summary for service classes can really fall under two headings.

#### Heading 1: Why Service Classes are Often the Better Tool

In the code that we write, we should prefer the use of service classes to the use of concerns because when using service classes instead of concerns:

1. You don’t need to keep track of the Ruby call chain / inheritance hierarchy.
1. Dependency is more explicit.
1. Service classes can be used in places where all or part of their functionality is desired but where it doesn’t make sense for an object to play a role.
1. It’s very easy to make services that have a single responsibility.
1. It’s more difficult to misuse a single-purpose service class than it is to abuse concerns.

#### Heading 2: Service Class Best Practices

1. Use specific, action-oriented names and avoid ambiguous words like “manager”, “helper”, or “service”.
1. Adhere to common class naming conventions.
    - “Repository” for classes managing object CRUD.
    - “Factory” for classes that create other objects.
1. Ensure the service class name matches the name of the object it services. 
    - I.e., don’t have a model called `Person` but manage its CRUD with a service class called `UserRepository`.
1. Keep service classes single purpose, and don’t be afraid of having a lot of service classes of varying sizes. If you name them clearly, it won't be an issue.

### Bringing it All Home

At the end of the day, concerns are a powerful way to allow your classes to play a role or to create inscrutable code...probably both. With great power comes great responsibility and all that.

That being said, a single-purpose, well-named service class is often the cleaner approach. And as a bonus, service classes are 100% Ballmer–approved:

[Gif here]

### Also...

I can't recommend this book enough:

[POODR image + link]

It has informed much of the thinking in this post, especially around the importance of using message-based software designs. Thanks so much for an excellent book Sandi!

### And Thank You...

...for reading this far. Hopefully this series has proven thought-provoking if not helpful.

We've gone far and covered a lot, but at the end of the day, it all pretty much boils down to:
- **Choosing the best tool for the job**, whether that's a concern or a service class.
- **Keeping your thinking flexible**, because there's always more to learn and refinement is an incremental process.
- **Always being humble and kind**, because that's the type of person that we all want to work with.