---
title: "Checkoff 1"
language: "en"
previous: "4nov.html"
next: "gameIdeaDiscuss.html"
---

<center><h1>Checkoff time!</h1></center>
<center><img src="https://media1.tenor.com/images/5998dc6b4576b29ba1d61a084f3d79d0/tenor.gif?itemid=5772115" alt="catto"/></center>

We went to DSL just in time before the previous group finished. We did the checkoff with prof Oka, and here are several things that prof pointed out to us.
- We separated our adder module into 2 (adder part 1 and part 2), and we could have made another module called adder that consist of both adder module.
- We had created an alu without the output of z, v, and n from the adder, so we had to add it to our alu module declaration input and output list.
- As we had a finite state machine to do the automated testing, our design made it so that we can't generate a wrong output "on the spot", so prof suggested to create another module where the output of the alu will be passed to it, and it can depend on say, a switch, to indicate whether we want to "force" a wrong output or not

Immediately after the checkoff finished, we did 2 of the 3 points above, which are combining the adder module and making the z, v, and n the output of our alu.

And then we had lunch and get ready to die from our 50.001 midterms...

<center><img src="https://media0.giphy.com/media/z1bMHX8k9Z3yg/giphy.gif" alt="catto"/></center>