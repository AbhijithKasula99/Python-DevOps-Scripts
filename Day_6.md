# Day - 6

## Functions

- There are usually two types of functions in-built or pre-defined functions and user defined functions.

- To recognize a function they are always followed by a set of parantheses **()**. For example: **print()** and **len()**.

- Users can create their own function too by using a keyword called **def()**.

- Below is an example for creating our own function

```
# Create your own function

# First we must define the function

def greet():
    print("Hello")
    print("Have a nice day")

 # Just defining the code won't make it function running, we must call it too

greet()
```

- I visited a site called [Reeborg](https://reeborg.ca/index_en.html) and then that robot cannot turn right but it can turn left so we created a new function to make it turn right by using it's function that turns the robot left.

```
def turn_right():
    turn_left()
    turn_left()
    turn_left()
```

- Then there was a hurdle to solve and the solution is this:

```
def turn_right():
    turn_left()
    turn_left()
    turn_left()

# One jump
def jump():
    move()
    turn_left()
    move()
    turn_right()
    move()
    turn_right()
    move()
    turn_left()

# Repeating the jump 6 times
for step in range(6)
    jump()
```

- In the second hurdle the goal is placed randomly so we must make sure the robot checks before going to next hurdle so, we use while loop. **at_goal()** is already predefined.

```
def turn_right():
    turn_left()
    turn_left()
    turn_left()

# One jump
def jump():
    move()
    turn_left()
    move()
    turn_right()
    move()
    turn_right()
    move()
    turn_left()

while at_goal() != True:
    jump()
```

- Another way to write the while loop is by:

```
def turn_right():
    turn_left()
    turn_left()
    turn_left()

# One jump
def jump():
    move()
    turn_left()
    move()
    turn_right()
    move()
    turn_right()
    move()
    turn_left()

while not at_goal():
    jump()
```

- In the next hurdle everything is randoma and there are predefined functions so we can do it by having to use some predefined functions/conditions and those are:

1. front_is_clear()
2. wall_in_front()
3. at_goal()

```
def turn_right():
    turn_left()
    turn_left()
    turn_left()

def jump(): # Be careful while defining the jump() function
    turn_left()
    move()
    turn_right()
    move()
    turn_right()
    move()
    turn_left()

while at_goal() != True:
    if wall_in_front == True:
        jump()
    else:
        move()

```

- Till here there were walls of equal height now what if the walls are of variable heights and then there were some more predefined functions/conditions.

```
def turn_right():
    turn_left()
    turn_left()
    turn_left()

def jump():
    turn_left()
    while wall_on_right():
        move()
    turn_right()
    move()
    turn_right()
    while front_is_clear():
        move()
    turn_left()

while at_goal() != True:
    if wall_in_front():
        jump() # If there is a wall then it must turn left so jump() starts with that
    else:
        move()
```

- What if the robot had the ability to navigate itself around an unknown maze, this is how the code would look like:

```
def turn_right():
    turn_left()
    turn_left()
    turn_left()

while not at_goal():
    if right_is_clear():
        turn_right()
        move()
    elif front_is_clear():
        move()
    else:
        turn_left()
```

- There can be instances where the robot might not face a right wall at all and end up in an infinite loop and not reach the destination we need to figure out later.
