# Hit_it
from Sprite import Sprite

    t_size = 20
    s_width = 200
    s_height = 180
    total_score = 0
    player = Sprite(0, -100, 10, 'circle', 'orange')
    enemy1 = Sprite(-s_width, 0, 15, 'square', 'red')
    enemy1.set_move(-200, 0, 200, 0)
    enemy2 = Sprite(s_width, 0, 15, 'square', 'red')
    enemy2.set_move(200, 70, -200, 70)
    goal = Sprite(0, 120, 0, 'triangle', 'green')
    scr = player.getscreen()
    scr.listen()
    scr.onkey(player.move_up, 'Up')
    scr.onkey(player.move_down, 'Down')
    scr.onkey(player.move_left, 'Left')
    scr.onkey(player.move_right, 'Right')
while total_score < 3:
    enemy1.make_step()
    enemy2.make_step()
    if player.is_collide(goal):
        player.goto(0, -100)
        total_score += 1
    if player.is_collide(enemy1) or player.is_collide(enemy2):
        goal.hideturtle()
    break
