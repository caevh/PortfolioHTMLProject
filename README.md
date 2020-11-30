The first step of the intial setup, is to create a To-do list.
1. Build the project
    - Create a folder structure
    - adding files
    - Connecting files

2. Navbar
    - 2 links and a name

3. Portfolio item grid
    - images
    - titles 
    - description
    - animations
    - javascript

4. About page
    - image
    - split column layout
    - content

- Next, we will create the basic file and folder set up.  
- This will include the basic HTML we know we'll need. 
* * *

The next step is to add styling.
- The first step is to go to the index.html and add a `<div>` tag.
	- A `div` tag doesn't do anything particularly. It is used to group your site and allows you to put things into different parts of your site.
   - In the `div` tag, I have created a class called placeholder. We will use this class to single out certain pieces/elements of the site. 
- Next, I crealte a link element `<link rel="stylesheet" href="/css/styles.css">` between the two `<head>` tags that links to my CSS styles. 
- I now edit the CSS file to see if it is set up correctly with the placeholder.
	- Within the file, I use a `.` this is because I am adding styles for a class. If I was adding styles for an id, I would use a `#`.
- Example of CSS and index.html at his point

CSS 
```
.placeholder {
    background-color: black;
}
```

index.html
```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8"/>
    <title>Page Title</title>
    <link rel="stylesheet" href="/css/styles.css">
</head>
<body>
    <div class="placeholder">
        I'm in a div
    </div>
</body>
</html>
```
* * * 

The final step of setup is to create the images I will be using. 
- To do this, I create a separate images folder where all the images will be saved to. 

* * *

**Editing the HTML, ready for the CSS styling**
- Now we know our placeholders and CSS is working how intended, we can delete the HTML code. 
- We will begin work on creating the navbar. 
- The first thing I'm going to do is create the basic home, and about links, we will have at the top. 
	- To do this, I create two `<a>` tags. `<a>` tags are used to create hyperlinks. 
	- Our tags will look like this; 
	```
	<a href="index.html">Home</a>
    <a href="about.html">About</a>
	```
	- The first tag links to the index.html file, second the about.html file. 
- Next, I will have my name in the navbar so, I will create a `<div>` tag with my name inside. For now, this will be displayed under the home and about links, but it will be repositioned. 
- We will then put all that code we have written inside of a `<div>` tag with the class "container". 
- Next, I create another `<div>` tag with the class "nav-wrapper" with all the links inside of it. 
- We're now going to create two more divs to allow us to put the links on one side of the page and our name on the other. 
- The reason for all the divs is to group the code so we can manipulate certain parts to do certain things. 
- After this, we will add three more `<div>` tags. One goes around the first link, one around the About link, and the third around the name on the right side. 
- The index.html code up to this point;

**index.html**
```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8"/>
    <title>Page Title</title>
    <link rel="stylesheet" href="/css/styles.css">
</head>
<body>
    <div class="container">
        <div class="nav-wrapper">
            <div class="left-side">
                <div class="nav-link-wrapper">
                    <a href="index.html">Home</a>
                </div>
                <div class="nav-link-wrapper">
                    <a href="about.html">About</a>
                </div>
            </div>

            <div class="right-side">
                <div class="brand">
                    <div>HARRY CAVE</div>
                </div>
            </div>
        </div>
    </div>
</body>
</html>

```
* * *

**Adding Styling**
- First, we're going to start with the "nav-wrapper class". 
	- The first styling we will use is flex. The way flexbox works is, it takes your wrapper divs and positions them next to each other. Flex will only move the name next to the links. Flexbox will not move both the links next to each other. The reason for this is flex moves only the child `<div>` tags. Even though our code has lots of `<div>` tags inside of the nav-wrapper div, only two of them are actually child elements to the nav-wrapper div. Those two elements are 
		- `<div class-"left-side">` and `<div class="right-side">`  
		- The other elements are within the two elements stated above. 
- Next, we will use `justify-content` with `space-between`. What this does is space the two divs as far away from each other as it can. 
	- I then add padding to the two elements to move them into the screen. 
- We will now add styles to the `left-side` class
	- We will use flex again to get the home and about links next to each other.
- Next, we will use CSS to traverse down a tree. It looks like this 
- first
		- `.nav_wrapper > .left_side`
			- We're telling it to start with the `nav-wrapper` class and apply all the styles in it to the `left-side` class too.
	- next,
		- `.nav_wrapper > .left_side > div`
			- Here we're telling it to go down to the `left-side` and then I want you to grab `divs` inside of there. 
		- How will this work in the HTML code?
			- It is going to look at the `nav-wrapper` then, it is going to go down to the `left-side` class, then it is going to grab any `divs` inside of there, and whatever style is given is going to be placed on those `divs`. 
		- So the styles that we change in `.nav_wrapper > .left_side > div` will essentially effect both the `<div class="nav-link-wrapper">` inside the `left-side` div. 
	- We then add `margin-right` and `font-size` into the style. as well as making both the links full caps with `text-transform`
- Next, we add styles explicitly for `nav-wrapper` divs. These are `height`, `border-bottom` and `transition`. These will be used to add animation to our links. 
- Next, we style `nav-wrapper` again but explicitly mention the `a` tags. `.nav-link-wrapper a`. This tells the CSS to only grab the `a` links inside of the specified class. 
	- Inside we add `color`, `text-decoration` and `transition`. This changes the colour and removes the underline. We will add one back later.
- Now, we will add a hover state to our links. To do this we use `.nav-link-wrapper:hover`. This is known as a sudo-state and will check for when hovering occurs. When that does occur, we will change the `border-bottom`.
	- Further building on the hover state, add a `.nav-link-wrapper a:hover`
The navbar is now finished other than a few things we will add later. 

The finished index.html code and styles.css code should look like the below at this point.

**index.html**
```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8"/>
    <title>Page Title</title>
    <link rel="stylesheet" href="/css/styles.css">
</head>
<body>
    <div class="container">
        <div class="nav-wrapper">
            <div class="left-side">
                <div class="nav-link-wrapper">
                    <a href="index.html">Home</a>
                </div>
                <div class="nav-link-wrapper">
                    <a href="about.html">About</a>
                </div>
            </div>

            <div class="right-side">
                <div class="brand">
                    <div>HARRY CAVE</div>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```
**styles.css**
```
.nav-wrapper {
    display: flex;
    justify-content: space-between;
    padding: 38px;
}

.left-side {
    display: flex;

}
.nav-wrapper > .left-side > div {
    margin-right: 20px;
    font-size: 0.9em;
    text-transform: uppercase;
    
}

.nav-wrapper {
    height: 22px;
    border-bottom: 1px solid transparent;
    transition: border-bottom 0.5s;
}

.nav-link-wrapper a {
    color: #8a8a8a;
    text-decoration: none;
    transition: color 0.5s;
}

.nav-link-wrapper:hover {
    border-bottom: 1px solid black;


}
.nav-link-wrapper a:hover {
    color: black;
    

}
```
* * *  

