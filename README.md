
# Parallax Effect ⭐🌟🌠

A quick example of how to recreate  a parallax effect with basic technologies, HTML & CSS.

More specifically, the Parallax Effect is a difference in the apparent position of an object when viewed along two different lines of sight. The Parallax it's measured by the semi-angle of inclination between those two lines.

In other words: 

### when we have objects in the same plane with different sizes and moving at different speeds, it will give depth to the plane. ###

Such an effect can be recreated on a web page.

To do that, we have to follow a certain structure. Let's get into it.



## Structure

To begin with, we have to set our link tag to our index.html file:

```
...
<link rel="stylesheet" href="style.css">
...
```
Implementing that line of code will be the communication point to receiive orders from our style file.

After that, we will need to set our structure for the stars that will reproduce the Parallax effect in the body of our HTML file.

```
<section class="wrapper">
    <div id="stars"></div>
    <div id="stars2"></div>
    <div id="stars3"></div>
</section>
```
For the structure, i decided to use a section which will occupy the entire screen, and it will be classified with the ```.wrapper``` class. 

Inside of this ```wrapper```, we will set our stars layers, which are contained each layer star with a ```div``` tag and identified with ```#stars```, ```#stars2``` and ```#stars3``` respectively.   

Once we have this structure set, we can work with CSS.

## Working with CSS
To obtain the results we want in our section, which is the stars container, we need to first tell to our HTML file the following properties.

```
html{
    height: 100%;
    overflow: hidden;
    background: radial-gradient(ellipse at bottom, #4a1b88 0%, #a275b4 100%);
}
```
I gave a height to the file that equals the entire height's screen to not get any space or spot with stars missing.

I decided to set the background with a light purple tone, one of my favourite colours.

```
#stars{
    width: 1px;
    height: 1px;
    background: transparent;
    animation: animStar 50s linear infinite;
    box-shadow: 779px 1331px #fff, 324px 42px #fff, 303px 586px #fff,
    1312px 276px #fff, 451px 625px #fff, 521px 1931px #fff, 1087px 1871px #fff,
    ...
 }
```

``` 
#stars:after{
    content: '';
    position: absolute;
    top: 2000px;
    width: 1px;
    height: 1px;
    background: transparent;
    box-shadow: 779px 1331px #fff, 324px 42px #fff, 303px 586px #fff,
    1312px 276px #fff, 451px 625px #fff, 521px 1931px #fff, 1087px 1871px #fff,
    ...
}
```

This is the main attributes for our stars. Each one of the box shadow values are separated by commas, and each of those represent a star respectively.

The icing on the cake is the animation property. It is responsible to make our stars move downwards. In this use case, i decided to make our stars make a linear move from point A (their position, counted as 0px) to point B ( -2000px) in a  50 seconds span. You can check that order in this @keyFrame.

```
 @keyframes animStar{
     from {
         transform: translateY(0px);
     }
     to{
         transform: translateY(-2000px);
     }
 }
```

You can add as many stars as you want.

Hope you liked it 👽 Feel free to download this effect and test it!

Best regards,

Mik3Tab