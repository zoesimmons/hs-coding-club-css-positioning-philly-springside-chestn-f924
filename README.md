# iPhone Organizer 

<img src="https://s3.amazonaws.com/after-school-assets/iphone-correct.png" alt="correct iphone" align="right" height="300" hspace="10">

Everyone always has specific places where they like their apps to go on their phone. It's muscle memory to get to them, and we take that layout for granted. But how confused would you be if someone rearranged your apps?

Fortunately for us, we can use CSS positioning to put our apps back in their original spots, just like in this iPhone!

When you look at the site in the browser, you'll notice the icons are all clumped together to the left of the iPhone. They're not even on the screen! Our job is to move the icons to their appropriate spots, just like in this image to the right.

## Let's Get Started

### Absolute Positioning

#### Step 1:

Open this lesson by clicking `Open` at the top of this page. You'll want to have `index.html`, `css/absolute.css` and `css/relative.css` open in the Nitrous text editor, as well as the browser. Take a look at the `How To: Open A Lab` for a refresher on how to get this done!

#### Step 2:

Make sure your browser, with `index.html` open in the browser, is the full width of your computer screen, and not minimized at all. We're basing these instructions off a 13 inch computer screen. Because we're going to start with _absolute_ position, it is all determined by the width of our browser window (and our computer window). The dimensions provided in the code won't work if you browser is a different width. You can either shrink your browser window or play with the dimensions we provide.

You're going to code your solution in `css/absolute.css` and `css/relative.css`. Go ahead and open that file in Nitrous, as well as `index.html`. You'll want to familiarize yourself with the code there. 

#### Step 3:

Take a look at the code in `index.html` in the Nitrous text editor. You should notice several things:

+ The app icons are grouped into threes

+ Each icon group is in their own `div`

+ The three divs are also in a single `div` with the id `iphone`

If you look at the site in the browser, you'll notice the icons are all clumped together near the top left corner of the iPhone. They're not even on the screen! Our job is to move the icons to their appropriate spots on the screen.

### Step 4:

Let's start with the first row of icons (Snapchat, Weather, and Angry Birds). First, we need to move the group, and then we can space each image individually.

In our `css/absolute.css`, copy and paste the code below.

```css
#first-three{
  position: absolute;
  top: 300px;
  left: 620px;

}
```

We use `#first-three` as our CSS selector, which is a `div` that contains three images - the app icons we're moving. 

The first property we set is `position`. This property can have several different values, but the most important two to know are `absolute` and `relative`. 

`absolute` means that an element's position is defined specifically. It's like telling someone, go stand in the top left corner of the room, 10 feet from the left wall, and ten feet from the top wall. No matter the size of the room, you always have to stay 10 feet from the top and the left. 

`relative` means that the placement of an element is relative to other elements. It's like saying stand 10% of the length of the room away from the top, and 15% of the width of the room away from the left of the wall. If the room shrinks, so do those percentages and thus your placement.

We set `position: absolute;` for now, which means the position of this `div` containing the three icons is never going to move. We the set `top: 300px`, meaning the images are going to be 300 pixels away from the top of the page. We also set `left: 620px;` meaning the images are going to be 620 pixels from the left side of the page.

#### Step 5: 

We want to go ahead and use the same CSS for the other two divs of images. Copy and paste the following code in `css/absolute.css`:

```css
#second-three{
  position: absolute;
  top: 400px;
  left: 620px;
}

#third-three{
  position: absolute;
  top: 500px;
  left: 620px;
}
```
If you look at this code, you'll notice the distance from the left side of the page stays the same, but the distance from the top increases by 100 pixels for each one. If we want the second set of icons to be below the first set, they need to be farther from the top.

Save your changes, and refresh in the browser. Finally we have all the icons on the screen!

#### Step 6: 

Now we need to space the icons away from each other appropriately. You'll remember from the box model, that `margin` governs the space between elements. We can set `margin-left` and `margin-right`.

Let's space out Snapchat, Weather, and Angry Birds. Copy the following code and paste it in `css/absolute.css`:
```css

#snapchat {
  margin-right: 20px;
}

#weather {
 margin-right: 20px;
 margin-left: 20px;

}

#angry-bird {
  margin-left: 20px;
}

```

We already have Snapchat where we want it on the left, we just need space on the right, so we set `margin-right: 20px`. The weather app needs space on both the left and the right, so we set both `margin-left` and `margin-right`. Angry Birds only needs margin on the left, `margin-left: 20px`.

Save and refresh in the browser!

#### Step 7:

Let's fix the last 6 icons. Copy and paste the following into your `css/absolute.css`:

```css
#facebook {
  margin-right: 20px;
}

#mail {
 margin-right: 20px;
 margin-left: 20px;

}

#spotify {
  margin-left: 20px;
}
#twitter{
  margin-right: 20px;
}

#vsco {
 margin-right: 20px;
 margin-left: 20px;

}

#youtube {
  margin-left: 20px;
}
```

#### Step 8:

Save, refresh in the browser and see your perfectly laid out icons! But now try and shrink the browser. What happens? Your site might look something like this: 

<img src="https://s3.amazonaws.com/after-school-assets/absolute-bad.png" alt="dangers of absolute positioning" align="right" height="300" hspace="10">
>

### Relative Positioning

This is where relative positioning becomes really powerful, without setting absolute locations for our HTML elements, our page can become responsive, which means it will look good no matter the size of our webpage.

#### Step 1:

First, we need to comment out our code in `css/absolute.css`. Select all of the text in that page, and then hold down the `command` key on the keyboard and the `/` key on the keyboard at the same time to comment out the code. Save that file.

You'll be coding your soltuion in `css/relative.css`.


#### Step 2:
You'll notice in `index.html`, that the `div` with the id `images` is the parent of the three different divs that make up each row of icons.

The first thing that we need to do is define each `div` of icons to only take up 1/3 of the height of it's parent, which will create our rows of icons. Copy and paste the following code into `css/relative.css`:

```css
.one-third {
  position: relative;
  display: block;
  height: 20%;
  width: 100%;
}
```

We use the class `one-third` and assign the `position` property to `relative`. This means that the width and height of these rows will be relative to the height of the parent div (the div with the id iphone). We set `height: 33.3333333%;`, which means each row will take up 33.3333333% of it's parent.

#### Step 3:

Now that we have our three rows, we need to absolutely position our icons inside those relative rows. This way, as the iPhone scales in size, the icons slide with them. Let's take the first row (Snapchat, Weather, and Angry Birds)

Copy the code below and paste it into `css/relative.css`:

```css
#snapchat {
  position: absolute;
  margin-top: 30%;
  margin-left: 30%;
  height: 32px;
}

#weather {
  position: absolute;
  margin-top: 30%;
  margin-left: 45%;
  height: 32px;
}

#angry-bird {
  position: absolute;
  margin-top: 30%;
  margin-left: 60%;
  height: 32px;
}
```

On all three images, we're using the ID on the image as our CSS selector. From there, we're setting `postion: absolute;` And then we're setting the `margin-top` and `margin-left`, as well as the image `height`.

Save and refresh in the browser. Go ahead and try to shrink your browser window.

#### Step 4:

Now let's do the other two rows! Copy and paste the following into `css/relative.css`:

```css 
#facebook {
  position: absolute;
  margin-top: 30%;
  margin-left: 30%;
  height: 32px;
}

#mail {
  position: absolute;
  margin-top: 30%;
  margin-left: 45%;
  height: 32px;

}

#spotify {
  position: absolute;
  margin-top: 30%;
  margin-left: 60%;
  height: 32px;
}
#twitter{
  position: absolute;
  margin-top: 30%;
  margin-left: 30%;
  height: 32px;
}

#vsco {
  position: absolute;
  margin-top: 30%;
  margin-left: 45%;
  height: 32px;

}

#youtube {
  position: absolute;
  margin-top: 30%;
  margin-left: 60%;
  height: 32px;
}
```

Save your changes and refresh in the browser. Now when you shrink your page, the icons all still stay in the correct place! DONE!

#### Step 5:

Mark this lesson as done by entering in terminal, in Nitrous, in this lesson directory `learn submit`.

## Share Share Share!

Do you know what time is? Time to share your work! Screen shot your iPhone or code and share with **\#flatironcodeclub** and **\#iphoneorganizer**.




<p data-visibility='hidden'>View <a href='https://learn.co/lessons/hs-coding-club-css-positioning' title='iPhone Organizer'>iPhone Organizer</a> on Learn.co and start learning to code for free.</p>
