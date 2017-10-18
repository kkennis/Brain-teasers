# Quad Ruby Meets Samuel Beckett

## Learning Competencies

* Model a simple (albeit absurd and French) system of rules.
* Recursion 
* Art! Culture!

## Summary

[Samuell Beckett](http://en.wikipedia.org/wiki/Samuel_Beckett) was a Nobel-prize-winning author, poet, and playwright most famously known for works like *[Waiting for Godot](http://en.wikipedia.org/wiki/Waiting_for_Godot)* and *[Endgame](http://en.wikipedia.org/wiki/Endgame_%27play%28)*. Born in Ireland in 1906, he spent most of his adult life living in Paris, France, including time as a courier for the [French Resistance](http://en.wikipedia.org/wiki/French_Resistance).

"Where could this possibly be going?" you're asking yourself. Buckle up.

In 1981 Beckett wrote and broadcast his play *[Quad](http://en.wikipedia.org/wiki/Quad_%27play%28)*. Here's a [video](https://www.youtube.com/embed/GMnKDGfpV7c?rel=0), which starts a bit into the play.

*Quad*'s set consists of a small square stage. There are four actors, dressed in different-colored robes: white, blue, red, and yellow.

The stage begins empty and *white* enters. As the play progresses, actors enter and exit one at a time. But the stage directions have an interesting property: each combination of actors appears on the stage once and only once throughout the play, and the play ends once the final actor is on the stage.

We're going to write a method `beckettDirections` which takes as its input an array of (unique) actors and returns a list of stage directions to create a *Quad*-like play with those actors. Rather than reporting on who entered or who left, we'll report on who is on the stage at that moment in time.

### Example Return Values

Here are some examples of what `beckettDirections` should return:

```javascript
# The play "ends" when the last remaining actor is on stage, so that actor never exits
beckettDirections(['red'])
  # => [[], ['red']]

# The play ends when "elaine" is the last actor on the stage
beckettDirections(['jasper', 'elaine'])
  # => [[], ['jasper'], ['jasper', 'elaine'], ['elaine']]

# The play ends when "melon" is the last actor on the stage
beckettDirections(['apple', 'pear', 'melon'])
   # => [[],
   #     ['apple'],
   #     ['apple', 'pear'],
   #     ['pear'],
   #     ['pear', 'melon'],
   #     ['apple', 'pear', 'melon'],
   #     ['apple', 'melon'],
   #     ['melon']]
```

## Releases

### Release 0 : Extracting Patterns

Before you start coding, sit down and try to extract patterns from the sequences above. Don't be afraid to use pen and paper, or pull out colored index cards and use them to represent which actors are on stage at a given time.

If you don't see the pattern it will be impossible to implement it in Ruby. This problem is easiest to solve recursively. Can you see how we can get the stage directions for three actors from the directions for two? How we get the directions for two actors from one?

Keep in mind the labels for the actors are arbitrary. The stage directions for `['tim', 'frank']` will be the same as the stage directions for `['linda', 'sue']`, modulo our labeling.

Here's a [video](https://www.youtube.com) that might make the pattern clearer (watching in full screen plus 1080p is best):

<iframe width="780" height="440" src="https://www.youtube.com/embed/8ueegfo7VkU?hd=1&amp;showinfo=0" frameborder="0" allowfullscreen style="margin: 0 auto;display: block;"></iframe>

###Release 1 : Implement `beckettDirections`

Remember the precise requirements. `beckettDirections` should return a list of arrays such that

1. Every subset of the input array is in the list exactly once–two arrays that differ only by their ordering count as the same actors being on stage, for our purposes.
2. Consecutive arrays in the list differs by *either* the addition or removal of a single element, representing an actor either entering or leaving the stage, respectively.

#### Fun Facts!

For people who actually watched that whole video, you might object that in the actual play the same actors *do* appear on stage at the same time. In addition to the requirements above, Beckett also wanted the actor exiting the stage to be the one who had been on the stage the longest (first-in, first-out). It turned out that this was impossible after listing out all possible 4-actor stagings, so one of the requirements had to go.

Beckett chose to remove the requirement that the same set of actors never appear on stage twice rather than the requirement that the actor exiting the stage be the "oldest" actor. In the interest of giving you a solvable challenge, we'll be removing the former requirement.

For 5, 6, 7, and 8 actors there are actually (many) stage directions which satisfy all of Beckett's requirements! They're hard to find without the aid of a computer, though. The first such set of stage directions for 7 actors took months of computing time, for example.

If only Beckett were a programmer!


<!-- ##Optimize Your Learning -->

