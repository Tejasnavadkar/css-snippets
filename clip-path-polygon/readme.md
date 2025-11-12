here i learn about clip-path property in css to provide custome shapes to elements
clip path provides multiple functions which performs different actions eg : - 

- clip-path: polygon(),
- clip-path: circle(),
- clip-path: ellipse(),
- clip-path: inset(),
- clip-path: path()
and many more

1 - polygon()

![alt text](./assets/image-7.png)

syntax:-

clip-path: polygon(x1 y1, x2 y2, x3 y3, ...)

![alt text](/assets/image-8.png)

-webkit-clip-path: polygon(x1 y1, x2 y2, x3 y3, ...) kya hota hai?

clip-path kisi bhi element ki shape cut kar deta hai. Matlab element normally rectangle hota hai, but clip-path se tum uski custom shape create kar sakte ho.

polygon() means tum shape ko points ke through define kar rahe ho.
Har point ek coordinate hota hai: x% y%

Examples:

1- polygon(0% 0%, 100% 0%, 80% 50%, 100% 100%, 0% 100%) // (top left(x and y), top right(x and y), middle right(x and y), bottom right(x and y), top left(x and y)) 

top left se start hoga

here we set 5 points 

![alt text](/assets/image-9.png)

2- clip-path:polygon(0% 0%, 70% 0%, 100% 50% , 70% 100%, 0% 100%, 20% 50%)

![alt text](/assets/image-10.png)

3-clip-path:polygon(20px 50%, 0% 0%, 100% 0%, 100% 100%, 0% 100%)

 <!-- polygon(
    20px 50%,
    0% 0%,
    calc(100% - 20px) 0%,
    97% 50%,
    calc(100% - 20px) 100%,
    0% 100%
  ); -->

![alt text](/assets/image-17.png)

Ye bol raha hai:

Start karo 20px from left, middle height (50%)

Fir top-left corner

Fir top-right

Fir bottom-right

Fir bottom-left

Iska result hai ek shape jo left side se thoda cut jaisa dikh raha hai (stepper ka pointed effect).
Basically tum rectangles ko arrow / angled look de rahe ho.

Why used here?
Because stepper ka design continuous ribbon jaisa hai jisme har step ek chevron (▶️ jaisa) shape me dikhna chahiye.


2 - clip-path:circle(50px at right top) circle appear at right side top side

![alt text](/assets/image-16.png)


3- clip-path:ellipse()

ellipse is very similar to circle but more flexiable, it let you crop elements in ovul shape


![alt text](/assets/image-1.png)

![alt text](/assets/image-2.png)


4 - inset shape (clip-path:inset())
lets you crop the rectangular area from an element
![alt text](/assets/image-3.png)

syntax :-

![alt text](/assets/image-4.png)

eg-1:- clip-path: inset(20px 30px 40px 10px round 10px); /*here inset(top,right,bottom,left round 10px rounded)*/
![alt text](/assets/image-6.png)

eg-2:-clip-path: inset(20px 30px round 28px 0); /*here inset(toprigth bottomleft round 28px 0(other two regular edges))*/
![alt text](/assets/image-5.png)


5- path (clip-path:path())

![alt text](/assets/image-11.png)

A for curv
![alt text](/assets/image-12.png)

eg-.path{
clip-path:path("M 10,40 L 70,40 A 10,10 0,0,0 80,30 L 80,10 A 10,10 0,0,1 90,0 L 140,0 A 10,10,0,0,1 150,10 L 150,190 A 10,10,0,0,1 140,200 L 10, 200 A 10,10,0,0,1 0,190 L 0,50 A 10,10,0,0,1 10,40 Z")
} 
/* 
here M means start and z means end
here A 10,10 0,0,0 means concave curv and A 10,10 0,0,1 for convax curv that means rounded border 
  */

1 = convex
![alt text](/assets/image-14.png)

0 = concave

![alt text](/assets/image-15.png)


 result :-
 
 ![alt text](/assets/image-13.png)



yt-tutorial - https://www.youtube.com/playlist?list=PLrEX5wDo7gnHccTJxhoVBIzC18kdRzOO5
clip-path generator tool :- https://unused-css.com/tools/clip-path-generator
tool-2 :- https://bennettfeely.com/clippy/
