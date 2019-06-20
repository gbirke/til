# When to use Jest snapshot testing

There are different opinions on Jets snapshot testing: [Some people want to use 
it for 
everything](https://medium.com/@newyork.anthonyng/use-jest-snapshot-on-everything-4c5d4c88ca16), 
[some people have given up on 
it](https://medium.com/@tomgold_48918/why-i-stopped-using-snapshot-testing-with-jest-3279fe41ffb2), 
and [some people use it for specific use 
cases](https://codeburst.io/a-place-for-jest-snapshot-testing-ca1fc737c457).

After reading these articles and reflecting on them, I have formed the 
following opinion: Use snapshot tests to see if the markup of your component is 
rendered correctly for a given input (and derived input, like computed 
properties in Vue). If your template contains branching logic that's based on 
state, you *might* try to create the desired state in the 
"[arrange](http://wiki.c2.com/?ArrangeActAssert)" phase of your test *if* you 
don't gain more readability and clarity from explicitly expecting a certain 
markup state. All the event handling of your component should be tested with 
more specific unit testing code. Thsi will cleanly separate the concerns 
between view and controller.

For a more advanced team and setup, putting the components in a story book and 
testing them with [Chromatic](https://www.chromaticqa.com/compare/chromatic) 
looks preferable to me, because you're no longer dealing with markup diffs but 
with *image* diffs. 

