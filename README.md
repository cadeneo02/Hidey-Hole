# Hidey-Hole
Game developed with team of three, player locates hidden circle on screen with progressive play difficulty. Here is the code for the game:

    from graphics import * 
    import random, time

    def getPlayerClick(point, prompt, win):
        text = Text (Point(point.getX(), 450), prompt)
        text.setFill('pink')
        text.draw(win)
        usrClick = win.getMouse ()
        usrClick.draw(win)
        text.undraw()
        return getShift(point, usrClick)

    def makeHole(point, radius, win):
        for i in range(3):
            holepti = random. randrange (20,580)
            holept2 = random. randrange (60,300)
            hole = Circle(Point(holept1,holept2), 80)
            hole.setFill('red')
            hole.setOutline('red')
            hole.draw(win)
            while True:
                usrClick = win.getMouse()
                if calcDistance(hole, usrClick):
                    print('Good Job!')
                    break
            
                else:
                    print('Try again')
                    xp1 = Line (Point (516,480) ,Point (522,460))
                    xp1. setOutline('red')
                    xp1. draw(win)
                    xp2 = Line (Point (516,460),Point (522,480))
                    xp2. setOutline( 'red')
                    xp2. draw(win)
                    break
            hole.undraw()

    def calcDistance(hole, point) :
        center = hole.getCenter ()
        distance = ((point.getX() - center.getX()))**2 + ((point.getY() - center.get

        return distance ‹ hole. radius
    
    def main():
    win = GraphWin( 'Hidey-Hole', 600, 500)
    win.yUp()

    win.setBackground ('black')

    sep = Line(Point (0,400) ,Point (600,400))
    sep. setOutline ('blue')
    sep.draw(win)

    attText = Text (Point (550,490), 'ATTEMPTS')
    attText.setFill('purple')
    attText.draw(win)
    line = Line (Point (515,485) ,Point (585,485))
    line. setOutline('purple')
    line.draw(win)

    prompt = ('Guess where the hole is!\n Click once below the blue line to make
    radius = 80
    center = Point (win-getWidth ()/2, win.getHeight ()/2)
    Hole = makeHole(center, radius, win)

    win. close ()

    main ()
