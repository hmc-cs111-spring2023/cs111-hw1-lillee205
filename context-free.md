# Context Free

##  Who is this programming language for?
This programming language seems to be for a general audience, but using its more
advanced features (the recursion aspects, for example) will require some
knowledge of CS concepts. The overall grammar seems understandable, though it
requires a lot of finagling with different parameters.

## What is easy to do in this language? Why is it easy?
It is easy to generate shapes; you don't need to have a drawing tablet or
anything in order to create art. You can just define a shape (square, for
instance) and have it appear on the page.

## What is hard to do in this language? Why is it hard?
It is hard to create shapes that go beyond the basics. To create more advanced
shapes, you need to build it using advanced shapes. As stated before, it's a lot
of playing with different numbers to see what works.

## How did you learn how to program in this language?
I looked at the provided examples (there were specifically two demo files that
gave a brief walkthrough on what different parameters do). I also looked at the
online documentation to see what I could do. 

## What is the underlying _computational model_ for this programming language? 
_We don't yet have a great definition of the term "computational model". 
For now, try to come up with the clearest, most concise explanation of what 
happens when a ContextFree program runs._

When a ContextFree program runs, it parses the text that you wrote in order to
generate shapes on a canvas. This text is in the form of different objects,
whose rules you define in relation to other pre-existing shapes. For example, if
I want to create a rectangle, I might create a line of squares. 

## What do you think is interesting about the ContextFree program you wrote?

It's kind of a Frankenstein monster. I created the general structure of the
"face" using shapes, scaling, and positioning. For the hair, I took inspiration
from the example art and played around with it to get the desired result. I also
think it's interesting how intuitively, I break up the face into different
"parts" and arrange them on the canvas.
