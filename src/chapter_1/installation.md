# Installation

For the majority of this book, we'll be using Node.js as our runtime, for a couple of reasons.

Node is simple above all else. Instead of needing to learn HTML, CSS, and dozens of other web technologies to execute JS in your browser, you only need one command in the terminal. It's an excellent tool to learn the basics of programming as a whole!

Node is also not a sandboxed environment; it has very few restrictions on the things that you can do with it, and even those can be bypassed. This also leaves some programs vulnerable to attack, which is why JS developers that use Node usually look through their external programs to see if they're insecure. All of this means that we can do many more things with Node than we would by sticking to the convention.

Finally, Node uses a modified version of a browser JS runtime under the hood, so we can rest assured that the concepts and programs we write can be run just about anywhere. Node uses V8 (Google Chrome's JS runtime environment) under the hood, which is also why it's incredibly fast!

To install Node, head over to [the Node website](https://nodejs.org/en/) and click "Install".

When you've gone through all the instructions, make sure to run `node -v` in your terminal.

If you get an error saying something like "Unknown command: node," try reinstalling it and trying again.
