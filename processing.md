# Processing cheat sheet

## En tom processing-sketch:

```java
void setup() {
  size(640, 360);
}

void draw() {

}
```

## Rita en rektangel:

```java
rect(x,y,bredd,höjd);
```

x och y är koordinater för rektangelns övre vänstra hörn. 

Man kan ändra så att x och y är koordinater för rektangelns mittpunkt med

```java
rectMode(CENTER);
```

## Rita en cirkel eller oval:

```java
ellipse(x,y,bredd,höjd);
```

x och y är koordinater för cirkelns mittpunkt. 

## Ändra färg på det som ritas:

```java
fill(rött,grönt,blått);
```

rött, grönt och blått är tal mellan 0 och 255

## Rita en linje

```java
line(startx,starty,slutx,sluty);
```

## Ändra färg på linjen

```java
stroke(rött,grönt,blått);
```

## Skriva en text

```java
textSize(storlek); //till exempel 32 för ganska stor text
text("Det som ska skrivas",x,y);
```

## Ett slumptal mellan 0 och 255:

```java
(int)random(0,255);
```

## En kommentar

```java
//detta är en kommentar
```

## Infoga en bild

före void setup:
```java
PImage bild; //bild kan ersättas med lämpligt namn på bilden
```

efter void setup:
```java
bild=loadImage(filnamn);
```

efter void draw:
```java
image(bild,x,y);
```

Man kan skala om bilden med
```java
image(bild,x,y,bredd,höjd);
```

x och y är koordinater för bildens övre vänstra hörn. 

Man kan ändra så att x och y är koordinater för bildens mittpunkt med

```java
imageMode(CENTER);
```

## Ändra färg på bakgrunden

```java
background(röd,grön,blå);
```

## Göra någonting om en knapp är nedtryckt

```java
if (keyPressed) {
	det som står mellan krullparenteserna görs om en knapp är nedtryckt
}
//OBS om man vill göra någonting endast en gång när en knapp trycks ned är 
//det ofta enklare att använda metoden keyPressed() istället för variabeln keyPressed
```

## Göra någonting om en speciell knapp är nedtryckt

```java
if (keyPressed) {
	if (keyCode==UP) {
		det som står här görs om pil upp 
		är nedtryckt
	}
}
```

## Variabler

Ett exempel där färgerna rött, grönt och blått sparas i variablerna r, g och b:

```java
int r;
int g;
int b;

void setup() {
  size(640, 360);
  r=255; 
  g=0;
  b=0;
  background(r,g,b);
}

void draw() {
}
```

Variabler kan också innehålla decimaltal

```java
float x;
float y;
float z;

x=5.4;
y=3.3;
z=x+y; //z är nu 8.7
```

## Array

En array är variabel som kan innehålla många värden.

```java
int a; //en vanlig variabel
int[] nummer = new int[3]; //en array som kan innehålla 3 värden
nummer[0] = 90;
nummer[1] = 150;
nummer[2] = 30;
int a = numbers[0] + numbers[1]; // a är nu lika med 240
```

## Var hittar men krullparenteser på tangentbordet?

```
{	mac: shift-alt-8
}	mac: shift-alt-9
[	mac: alt-8
]	mac: alt-9
|	mac: alt-7
```

## Ett exempel som spelar ett ljud när man klickar

```java
import ddf.minim.*;

Minim minim;
AudioPlayer player;

boolean start;

void setup()
{
  size(512, 200);
  minim = new Minim(this);
  player = minim.loadFile("boing.mp3");
  //boing.mp3 måste ligga i samma map som pde-filen, eller i mappen data
  start=false;
}

void draw()
{
  background(0);
  if (start) {
      start=false;
      player.rewind();
      player.play();
  }
}

void mousePressed() {
  //vi använder metoden mousePressed() istället för variabeln mousePressed
  //för att bara starta ljudet en gång när musen klickas
  start=true;
}
```
