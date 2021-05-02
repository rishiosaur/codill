# Runtimes

Chances are, you've already interacted with JavaScript in some way, shape or form. As was stated in the
[introduction](../introduction.md), JS is usually used in web programming; many websites use JavaScript to allow
user interaction, rich updating, and so on. To run the JavaScript that developers write for their websites, your
browser also includes what's known as a JavaScript _runtime_ environment.

A runtime environment is nothing more than a place that code can run. However, there are many moving parts to a runtime environment. These pieces of a given runtime change based on the language, but we will discuss that more extensively in [Chapter 6](). In essence, a runtime holds all the bits and pieces that you need to execute a program: standard libraries, an executor, and so forth. Don't worry if those words confuse you right now—it's perfectly normal.

> Each browser has their own proprietary JavaScript runtime environment:
>
> - Google Chrome uses a runtime known as **V8**, which is written in C++ and open source.
> - Mozilla Firefox executes Javascript through its **SpiderMonkey** environment
> - **JavascriptCore** is what Safari uses, and its adoption has influenced the way that JavaScript has been shaped through the ages.
> - Before Microsoft Edge came, Internet Explorer used **Chakra**.

Behind the fancy names, each of these 'runtimes' do the exact same thing in each browser: give JS programs a space to run.

However, browsers are just one possible application of JS; as we investigated earlier, it can also be used to write things like servers, interact with your computer's file system, create blockchains, among thousands of other possibilities. Browsers can't do these things because they are sandboxed.

> In programming, 'sandboxing' is a colloquial term for isolating an environment. In real life, sand from a sandbox can get everywhere—you wouldn't want it getting on any of the playground equipment, would you? When you go to a website, the JS code that is run can be similarly damaging; if it is given access to, say, the file system, then who knows what developers could do with a simple link?
>
> In the same way that physical sandboxes are built away from other places, browser runtime environments are sandboxed (they restrict certain features) to make sure that the JS that is run can't do anything malicious.

If we do need access to the full computing power of a machine, then we need to go lower. JavaScript can also be run in the terminal through runtimes like Node.js!

For instance, you can't access the file system through a browser webpage because of security & sandboxing. On the other hand, because Node.js is a lower level developer tool by nature and doesn't have restrictions, it allows JS code to use more functions.

> "Low level" in programming means the level of abstraction that something provides. For instance, JS can't directly interact with a computer's RAM because it is a _high level_ language. Something like C or Rust, on the other hand, are lower level languages, and they _can_. Node is a lower level JavaScript runtime; it has more system privileges.
