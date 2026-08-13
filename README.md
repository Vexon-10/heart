import math
import turtle

# Set up screen
screen = turtle.Screen()
screen.setup(width=800, height=800)
screen.bgcolor("black")
screen.title("Heart Animation")

# Set up turtle
t = turtle.Turtle()
t.speed(0)  # 0 is fastest
t.hideturtle()
t.color("#ffb6c1")
t.pensize(2)

# Draw heart shapes
for scale in range(11, 17):
    t.penup()
    for i in range(121):  # 120 steps to complete full loop
        angle = i * (math.pi * 2) / 120

        # Heart mathematical formula
        x = 16 * (math.sin(angle) ** 3) * scale
        y = (
            13 * math.cos(angle)
            - 5 * math.cos(2 * angle)
            - 2 * math.cos(3 * angle)
            - math.cos(4 * angle)
        ) * scale

        if i == 0:
            t.goto(x, y)
            t.pendown()
        else:
            t.goto(x, y)

# Write text in the center
t.penup()
t.goto(0, -10)  # Standard turtle uses (0,0) as exact center
t.color("white")
t.write("I love you", align="center", font=("Arial", 16, "bold"))

# Keep window open until clicked
screen.exitonclick()
