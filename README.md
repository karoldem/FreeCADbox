Squares are everywhere, so I made a module, that can make squares. My motivation was to burn wooden boxes on laser and I wanted to make a method able to draw two matching edges.

[img]https://raw.githubusercontent.com/karoldem/FreeCADbox/main/images/obraz_2023-01-24_212630098.png[/img]





First I made method for making lines and it work as follows:
[code]k = greek(10000,20000,'x')
k.move(-15000)[/code]
I created first point at (10mm, 20mm) = (10 000 um, 20 000 um) and created line 15 mm long. Dimensions added manually for clarity.

[img]https://github.com/karoldem/FreeCADbox/blob/main/images/obraz_2023-01-25_004516541.png?raw=true[/img]





But the main purpose is to create line in relation to previous line:
[code]k.move(5000, leftPattern)[/code]
[img]https://github.com/karoldem/FreeCADbox/blob/main/images/obraz_2023-01-25_002647913.png?raw=true[/img]





And grande finale - in relation to second previous line. Said line will either zigzag or curl AKA will go in the same direction as previous parallel line or reverse AKA line with two previous will create either z or c.
[code]k.move(5000, zPattern)
k.move(5000, cPattern)[/code]
[img]https://github.com/karoldem/FreeCADbox/blob/main/images/obraz_2023-01-25_004150164.png?raw=true[/img]





You can also turn right with a negative number and turn left.
[code]k.move(-5000, rightPattern)[/code]
[img]https://github.com/karoldem/FreeCADbox/blob/main/images/obraz_2023-01-25_005107495.png?raw=true[/img]





Now you can create complex structures:
[code]k.teeth( 30000, 2, 7000, 5000, 4000, leftPattern)[/code]
[img]https://github.com/karoldem/FreeCADbox/blob/main/images/obraz_2023-01-25_012426239.png?raw=true[/img]





[size=150]What do you guys think about it?[/size]
