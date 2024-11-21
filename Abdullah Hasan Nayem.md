- 👋 Hi, I’m @Abdullahhasannayem
- 👀 I’m interested in programing  ...
- 🌱 I’m currently learning python programing ...
- 💞️ I’m looking to collaborate on mess men business ...
- 📫 iam a student of computer science  ...
- 😄 my Dream is a start profession on Engineering ...
- ⚡ Fun fact: iam a simple happy boy...

<!---
Abdullahhasannayem/Abdullahhasannayem is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import turtle
import random
import time

# Screen setup
screen = turtle.Screen()
screen.title("Love & Name Rain")
screen.bgcolor("black")
screen.setup(width=800, height=600)
screen.tracer(0)

# Draw Love Emoji
def draw_love():
    turtle.speed(2)
    turtle.penup()
    turtle.goto(0, -150)
    turtle.pendown()
    turtle.color("red")
    turtle.begin_fill()
    turtle.setheading(45)
    for _ in range(2):
        turtle.circle(100, 180)
        turtle.right(90)
    turtle.goto(0, -150)
    turtle.end_fill()

    # Draw 'M' at the middle point
    turtle.penup()
    turtle.goto(0, 30)
    turtle.color("white")
    turtle.write("M", align="center", font=("Arial", 24, "bold"))
    turtle.hideturtle()

# Rain System
class NameRain:
    def __init__(self):
        self.raindrops = []

    def create_raindrop(self):
        drop = turtle.Turtle()
        drop.color("cyan")
        drop.penup()
        drop.hideturtle()
        drop.goto(random.randint(-390, 390), 300)
        drop.write("Abdullah Hasan Naim", align="center", font=("Arial", 14, "bold"))
        self.raindrops.append(drop)

    def move_raindrops(self):
        for drop in self.raindrops:
            x, y = drop.position()
            if y > -300:
                drop.clear()
                drop.goto(x, y - 30)
                drop.write("Abdullah Hasan Naim", align="center", font=("Arial", 14, "bold"))
            else:
                drop.clear()
                self.raindrops.remove(drop)

# Draw the love emoji
draw_love()

# Start the rain system
rain_system = NameRain()
start_time = time.time()

while True:
    screen.update()
    if time.time() - start_time > 0.5:  # Create a new raindrop every 0.5 seconds
        rain_system.create_raindrop()
        start_time = time.time()
    rain_system.move_raindrops()
    time.sleep(0.1)

turtle.done()
