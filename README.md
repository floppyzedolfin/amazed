# Amazed
A project that bewilders you.

This program was written with the writing of a chapter of our book in mind.
We needed to generate mazes as PNG images, so we wrote a program to do it for us.

You can run this program this way:

```bash
go run main.go 100 200
```

This will generate a maze as an RGBA PNG image.

In this maze, the walls are {0, 0, 0, 255}, and the paths are {255, 255, 255, 255}.
All th pixels of the edge are black, except two: the entry, with value {0, 255, 0 ,255}, 
and the exit, with value {255, 0, 0, 255}.

The goal of the game is to find your way from the entrance to the exit. 
This  problem has a unique solution.

![example.png](doc%2Fexample.png)

The maze has a "complexity" of length + width of the generated image, which means that 
the full path from entrance to exit is at least as the sum of the sides (the exit isn't 3 turns away from the entrance).

# Who can use this?

This was primarily written to be used by computers. Unless you've got excellent eyes, that is.
The entrance, on top of being green, is precisely at pixel {0, height / 2} - at the middle of the left side.
The exit can be anywhere, as long as it is on the edge of the image.

# Known bugs

There is a slight "chance" that the image generation will fail. It's random.
If the randomness decides to create a "comb", where every branch will only extend to the edge,
and not branch itself, the required complexity wouldn't be hit.
Just regenerate the image.

# Limitations

I ran it on a 10k x 10x grid, and it generated an image. I wouldn't push it farther.
