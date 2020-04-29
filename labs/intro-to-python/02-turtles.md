#### GISC 425 T1 2020
# It's turtles all the way down
Right. So the API documentation for `turtle` is available [here](https://docs.python.org/3/library/turtle.html). That is where you should look for information on things that are unclear.

For now, I am going to provide a supplement to Chapter 4 in [_Think Python_](https://greenteapress.com/wp/think-python-2e/).

## The `turtle` module
Before we start we have to import the `turtle` module.
```python
import turtle
```

To 'fire it up' we make a turtle. We'll call ours something more local.
```python
kiwi = turtle.Turtle()
```

You should see a blank window appear with a little black triangle at its centre. This is `kiwi` our first `Turtle` to whom we can issue commands using function calls that will cause her/him/it (?!) to draw things in the window. The `fd(x)` function causes the `Turtle` object asked to execute it to move `x` units forward. There is also a `bk(x)` command to cause a `Turtle` to move backwards.
```python
kiwi.fd(100)
```

We can also ask a `Turtle` to change direction with the `right(x)` or `left(x)` function which causes the turtle to turn in the appropriate direction through an angle of `x` degrees. These functions can also be abbreviated as `rt(x)` or `lt(x)`.
```python
kiwi.right(90)
```

Now if we issue a forward command, the line will get drawn at an angle to the previous one.
```python
kiwi.fd(100)
```

That's enough to get the general idea. It is also useful, before continuing to be able to reset the screen and send `kiwi` back to her start location.
```python
kiwi.reset()
```

## Simple repetition
So... using what you already know, make `kiwi` draw a square.

The book tells you what you most likely wrote. It probably involved some repetition, which even allowing for copy and paste is pretty tedious to deal with.

Thankfully, much of programming is all about repetition (usually called *iteration*), so we have a construct in Python that allows us to repeat actions many times. For example

```python
# Simple repetition
for i in range(4):
    print("Here we go again")
```

With that in mind, rewrite your square drawing code to use a `for` loop. Note that we'll look at iteration more closely in a couple of weeks.

## Exercises from section 4.3
These are taken directly from _Think Python_. They won't make much sense this week (we get to functions next week), but it is worth looking at them now, and revisiting them in the next while as you learn more about Python.

1. Write a function called `square` that takes a parameter named `t`, which is a turtle. It should use the turtle to draw a square.

   Write a function call that passes a turtle as an argument to `square`, and then run the program again.

   Here's the outline, to get you started:

```python
def square(t):
    print("Replace this print statement with code to draw a square")

## and here's a line of code to run the function
square(kiwi)
```

2. Add another argument, named `length`, to `square`. Modify the function body so that the length of the sides is `length`, and then modify the function call to provide a second length argument. Run the program again. Test your program with a range of values for length.

   Again here's a function header

```python
def square(t, length):
    print("You know what to do")
```

3. Make a copy of the `square` function code and change the name to `polygon`. Add another parameter named `n` and modify the body so it draws an n-sided regular polygon. Hint: The exterior angles of an n-sided regular polygon are 360/n degrees.

   No clues this time...

### If you get into this turtle thing, try this

4. Write a function called `circle()` that takes a turtle, `t` , and radius, `r` , as parameters and draws an approximate circle by calling `polygon` with an appropriate length and number of sides. Test your function with a range of values of `r`.

   Hint: figure out the circumference of the circle and make sure that length * n = circumference.

5. Make a more general version of circle called `arc()` that takes an additional parameter `angle`, which determines what fraction of a circle to draw. `angle` is in units of degrees, so when `angle=360`, `arc` should draw a complete circle.

## Read the book!
The book spells out nicely how to complete these tasks in sections 4.4 to 4.7 and I suggest that you work through those while working on this material.

## Clean up
To clear the graphics window:
```python
turtle.done()
```