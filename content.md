# What, why, and how

## What is our goal?

The ability to handcraft a web page (with HTML & CSS) together with the ability deploy it to a fast, reliable hosting service (like GitHub Pages) is a pretty powerful thing. You can now do things like:

- Design a personalized résumé and share it with the world.
- Publish an informational website for an organization.
- Make a landing page for a startup.

But our real goal in this course is to create _interactive_ web **applications**, not just _informational_ web **sites**.

With informational (i.e. **static**) web sites, when someone visits a URL (i.e. sends an HTTP request), we respond with the same, unchanging HTML file — no matter who they are or when they sent the request.

With an interactive web application, when someone sends us an HTTP request, we respond **dynamically**. We might look up some information about the user and use that to calculate something interesting for them; we might use an API to get the current weather or send a text message or generate an image with AI; an _application_ can do anything!

And, crucially, the HTML that we respond will be unique _to that particular request_, at that particular moment in time. If the user sends a request for the same URL a minute later, the HTML that we respond with might be quite different. For example, in a social network, if one of the user's friends made a new post during that minute, the HTML for the user's homepage will be different.

If the HTML that we're responding is different from user to user and moment to moment, then we clearly can't handcraft it in real-time. (If that were the case, the developers at Twitter would have to write hundreds of millions of HTML pages per day!)

Instead, we have to  _automate the writing of the unique HTML responses_. In order to automate anything with a computer, we have to **learn to program.** In other words, we have to learn how to write instructions that the computer can repeatably follow to reliably and quickly do some work that we otherwise would have had to do manually.

There are two important parts to that:

- We must learn a language that the computer undertands, so that we can tell it our instructions. This is a huge undertaking, like learning any foreign language!
- Even harder: we must figure out how we would do the task manually. If we haven't figured out how we would do that task manually, we have no hope of instructing someone else how to do it (let alone a dumb computer, and using a foreign language we barely know).

In the following lessons, we will tackle both of these things. We'll learn the fundamentals of the Ruby programming language, and we'll start practicing computational thinking.

Then, we'll be in a good place to teach the computer how to generate dynamic, unique HTML pages in response to various HTTP requests — in other words, we'll be in a good place to build web apps!

## Why Ruby?

There are many programming languages we could have chosen — Python, JavaScript, Go, dozens of others — but Ruby has a lot of advantages for beginners:

### Developer happiness 

Here's a quote from Yukihiro Matsumoto (a.k.a. "Matz"), the creator of Ruby:

> Often people, especially computer engineers, focus on the machines. They think, "By doing this, the machine will run faster. By doing this, the machine will run more effectively. By doing this, the machine will something something something." They are focusing on machines. But in fact we need to focus on humans, on how humans care about doing programming or operating the application of the machines.
>
> — Yukihiro Matsumoto, [The Philosophy of Ruby](https://www.artima.com/intv/ruby4.html)

Matz's focus when he designed Ruby was on "developer happiness", which was pretty bold back in 1995 when Ruby was first released. Optimizing for human readability rather than computer readability meant paying a cost in terms of performance, and computers were slow back then; but Matz didn't care. He wanted to create a language that he _enjoyed_ reading and writing.

By the mid-2000s, computers had become fast enough to run Ruby just fine for web apps. And by now, computers are unbelievably faster than they were 20 years ago, _and_ Ruby has gotten much more performant at the same time. So we beginners can have the best of both worlds — the readability of Ruby and plenty of performance to build web apps (if Ruby was fast enough 15+ years ago for Twitter v1 or Airbnb v1, then it's plenty good for your apps now).

<aside markdown="1">
From a business perspective, servers are very cheap while developers are _very_ expensive; so you should pick the language that makes developers the most productive.
</aside>

Besides, the hard part is learning the basic concepts of programming the first time. Once you've learned them, it's much easier to translate them into the syntax of another language. If you decide to pursue software development, you'll end up learning at _least_ half-a-dozen languages. Whatever challenge is thrown your way, you'll choose the right tool for the job.

So the important thing when you choose your _first_ language is to choose one that is most conducive to learning. I think that, for most learners, Ruby is that language.

### Ruby on Rails and other libraries 

People often ask "What's the best language for Task X?"; where "Task X" might be "web apps", "data analysis", "game programming", or any number of things.

Depending on the task, sometimes the technical features of a particular language is particularly well-suited to it; but that is very rare. In general, any programming language can do anything that any other programming language can.

<aside markdown="1">
Unless maybe the owner of a platform only allows a particular language. For example, Apple only allows Swift, Objective C, and JavaScript to run on iOS.
</aside>

However, there's another, more important consideration: which language has the largest **community** of developers doing Task X?

More community means that other people have already solved many of the problems you'll face, so there might be code out there that you can borrow instead of having to write it all yourself. Pre-written code that you can use are generally known as **libraries** or **packages**. In Ruby, we call them **gems**.

Also, if there's a big community doing Task X in a given language, then there will be more blog posts, more answers when you Google a question, etc.

So when you're choosing which language to use for a particular job, you should see what other people are already using for that job.

For example, Python and Ruby are very similar languages in terms of their technical features and performance profile. However, by some historical accident, Python seems to have gathered more of the scientific/data analysis/machine learning community around it, so more open-source libraries in those areas have been developed and shared in Python than in Ruby; and so now Python is the go-to language for those tasks.

On the other hand, for rapid development of database-backed web applications, Ruby has a huge and thriving community. In particular, there is an open-source library for building web apps called **Ruby on Rails** ("Rails", for short) that makes small teams or even solo developers incredibly productive. The existence of Rails alone makes the Ruby language a good choice for both startups and beginners.

<aside markdown="1">
Here's a [longer blog post](https://devbrett.com/2019/03/why-i-believe-rails-is-still-relevant-in-2019.html) on why Ruby on Rails is still a good choice for building web apps.
</aside>

The philosophy of Rails is "convention over configuration" — it makes a lot of decisions on your behalf, and if you go with the flow, then things "just work". (If you want to fiddle with settings, then of course you can, to your heart's content; but you don't _have to_ spend hours or days doing so before anything will even show up, like you do in most other frameworks.) You can focus on building the unique features of _your_ application, not on plumbing that's common to all applications.

There are a lot of other powerful, easy-to-use Ruby libraries that have philosophies similar to Rails. Ruby seems to have gathered a community of developers around it who are focused more on  _creating value for our users_, and focused less on [bike shedding](https://en.wiktionary.org/wiki/bikeshedding) over technical details.

<aside markdown="1">
I, personally, agree with [this author](https://mcfunley.com/choose-boring-technology) who prefers boring technologies over cutting-edge ones.
</aside>

### MINASWAN 

The programming world at large can be pretty competitive and harsh, but I've found that the Ruby community is very inclusive and welcoming, which is a relief for beginners. Maybe this can also be traced back to Matz; from [his Wikipedia page](https://en.wikipedia.org/wiki/Yukihiro_Matsumoto):

> His demeanor has brought about a motto in the Ruby community: "Matz is nice and so we are nice," commonly abbreviated as MINASWAN.

### Heroku and other integrations 

Another way in which the ergonomics of Ruby excels is the amount of tooling that exists around it. For example, [Heroku](https://heroku.com) was the first "hosting platform-as-a-service", a layer on top of Amazon Web Services that makes it incredibly easy to deploy applications to an industrial-grade infrastructure. Something that would have required a team of expert systems administrators, we can now do with just one click; and we can focus instead on building features for our users.

Rails was the first platform that Heroku supported, and Rails developers are still Heroku's primary users. There are many other services, everything from performance monitoring to error reporting to email delivery to A/B testing to analytics, that offer tight integrations with Ruby and/or Rails and make using them hyper-productive for small teams, solo developers, and therefore also for us beginners.

<aside markdown="1">
There are multiple great platform-as-a-service options now, in addition to Heroku. In this course, we'll learn how to deploy to a few of them, not just one.
</aside>

## How to use this text

To go from _complete beginner_ to _full-stack web developer_ is huge task. In order to make it as approachable as possible, and hopefully more enjoyable than a typical textbook, we've built the interactive learning platform that you're looking at now. Here's how to use it:

### Readings

There will, of course, be a lot to read.

- The first time you read a lesson, please read it carefully and thoroughly — try not to skim.
- Any time something is confusing, or you're curious about different ways of doing something, or any other thought pops into your mind — please jot it down so that we can discuss it on the forum, during office hours, or in class.

    Remember: "Questions are places in your mind where answers fit. If you haven’t asked the question, the answer has nowhere to go." [— Clay Christensen](https://twitter.com/claychristensen/status/231411154050748416?lang=en)

### Quiz questions

From time to time, you will encounter quiz questions within the lessons. Explore the question types below:

#### Choose the best option

For "choose the best option" questions, you can only select one response. Select the best one to get full credit.

- HTML is good for...
- Formatting content so that a user's browser can display it in an accessible, pleasing way.
  - Yes!
- Generating dynamic, unique responses to each HTTP request.
  - Not quite. That's why we need to learn Ruby!
{: .choose_best #html_is title="HTML is for?" points="1" answer="1" }


#### Choose all correct options

For "choose all correct options" questions, you can select multiple responses. Select all that apply. You get partial credit for each correct response you select. If any of the responses you've selected are incorrect, then you get zero credit.

- What is Ruby on Rails?
- a programming language
    - The name can be confusing, but no, Ruby on Rails is not a language. It's a _library_ (or a bunch of pre-written code) that is written in the Ruby language.
- a gem
    - Yes! In Ruby, we call pre-written code that we borrow "gems".
- a library
    - Yes! This is a more general, non-Ruby way of saying "pre-written code that we can borrow".
- a package
    - Yes! This is a more general, non-Ruby way of saying "pre-written code that we can borrow".
{: .choose_all #rails_is title="What is Ruby on Rails?" points="2" answer="[2,3,4]" }

#### Free text

For "free text" questions, you can type anything into the box.

- Which programming language will we focus on first?
- Ruby
  - That's right!
- any
  - Not quite.
{: .free_text #what_language_are_we_learning title="What language are we learning?" points="1" answer="1" }

### Interactive code blocks

#### Regular code blocks

We will have lots of examples of code in the readings. These are called "code blocks", and you'll see them all over the internet. For example:

```ruby
x = "Hello"
y = "World"
z = x + y

pp z
```

That code block is not interactive — you can only read it. 

#### Runnable code blocks

Some of our code blocks, however, are _runnable_ — you can run the code within and see the output. Just running them once is enough to get full credit. **You must run each of them to get credit**. Try clicking the "Run" button below this block:

```ruby
x = "Hello"
y = "World"
z = x + y

pp z
```
{: .repl #first_runnable_code_block title="First runnable code block" points="1"}

It will take a moment, but then the output of the program in the pane on the left (called the **editor**) will be displayed in the pane on the right (called the **terminal**) 🎉 

Most importantly, you can _change_ the code and re-run it to see how the output changes. You should always be:

- Thinking, "What if I changed it like _this_? What would it do then?"  
- Predict what you _think_ will happen.
- Try it, run it, compare the actual behavior to the behavior you predicted, and learn!

You can press "Reset" to get the editor back to its original state.

#### Graded code blocks

Some runnable code blocks are graded. We will assign you a task, and test to see whether the code you've written accomplishes that task. In order to get credit, you will need to:

- Modify the code in the editor.
- Press "Run" to check your output.
- For each of the "specs" or "tests", which are below the graded code block, press "Run" to see whether your code passes that specific test.

In graded code blocks, pressing "Reset" gets the editor back to its original state, and also resets your progress on the tests — so be careful with it.

For example: your task below is to modify the program so that it prints "Hello, world!" in the terminal. We haven't learned any Ruby yet, so I'll tell you how to do it — replace the contents of the editor with this code:

```ruby
pp "Hello, world!"
```

Now, in the graded code block below, modify the program so that it prints "Hello, world!" in the terminal.

```ruby
pp "change me :)"
```
{: .repl #first_graded_code_block title="First graded code block"}

```ruby
describe "First graded code block" do
  it "should print 'Hello, world!'" do
    path = "/tmp/code.rb"
    expect { require_relative(path) }.to output(/Hello, world!/).to_stdout, "Expected output to be 'Hello, world!', but it was something else."
  end
end
```
{: .repl-test #first_graded_code_block_1 for="first_graded_code_block" title="First graded code block should print 'Hello, world!'" points="1"}

Click "Run" on the test to make sure it passes. If the tests fail, you'll see a bunch of output that looks like this:

![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1687363037/graded-code-block-test-fails_efx6ga.png)

This output is not particularly beginner-friendly, but it is what the output of an automated test looks like in the real world, and developers spend all day reading output like this. In fact, this is what the the raw output from our `rake grade` command in your Codespace projects looks like; we just turn it into a [beginner friendly format in our Grades interface](https://learn.firstdraft.com/lessons/125-using-rake-grade#grades-within-an-app-assignment-rake-grade). If you click on the "View" button above, you will see something similar to the "Examine test" button in Grades when you visited the `rake grade` build report. This is the real Ruby code that runs to test your code!

(We're working on making the graded code block results here more readable — stay tuned.)

If the test passes, you should see output like this:

![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1687363106/graded-code-block-test-passes_yyrzhe.png)

Nice!

#### Do, or do not

_Do_, or do not. There is no  _read_.

If you're just _reading_, you won't be successful at learning programming; you have to _do_ in order to build up some muscle memory. _Practice is crucial._

Please use the runnable code blocks to experiment often, and think up questions!

---

## Onwards

Okay! With the "what", "why", and "how" out of the way, let's finally dive into Ruby!

**When you are done here, close the window and return to Canvas for the next lesson in the series.**

----
