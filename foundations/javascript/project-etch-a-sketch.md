---
description: >-
  Learn how to make a basic version of the classic "Etch-A-Sketch" toy, with
  JavaScript.
---

# Project: Etch-A-Sketch

## Building an Etch-A-Sketch

In this project you'll be creating a pretty neat toy for your portfolio to flex your DOM manipulation skills. You're going to build a browser version of something between a sketchpad and an Etch-A-Sketch.

This project should _not_ be easy for you. You'll probably have to Google frequently to get the right JavaScript methods and CSS to use - in fact, that's the point! You _can_ build this using the tools that you have already learned and there are plenty of resources on the net for learning stuff that we haven't covered yet if you decide you need it. We'll walk you through the basic steps, but it will be up to you to actually implement them.

## Assignment

1. [Follow the instructions](https://www.learnhowtocodebook.com/foundations/frontend/project-create-a-web-page) at the beginning of the "Create a web page" project to setup a git repository for this project.
2. Create a webpage with a 16x16 grid of square divs
   * Create the divs using JavaScript... don't try making them by hand with copy and pasting in your html file!
   * Best to put your grid squares inside another "container" div \(that one can go directly in your html\)
   * There are several different ways to make the divs appear as a grid \(versus just one on each line\) feel free to use any or play with each of them:
     * float/clear
     * inline-block
     * flexbox
     * CSS Grid
   * Be careful with borders and margins, they can adjust the size of the squares!
   * "OMG, Why isn't my grid being created???"
     * Did you link your CSS stylesheet?
     * Open your browser's developer tools
     * Check if there are any errors in the JavaScript console
     * Check your "elements" pane to see if the elements have actually shown up but are somehow hidden.
     * Go willy-nilly and add  `console.log` statements in your JavaScript to see if it's actually being loaded.
3. Set up a "hover" effect so that the grid divs change color when your mouse passes over them, leaving a \(pixelated\) trail through your grid like a pen would.
   * Hint: "hovering" is what happens when your mouse enters a div and ends when your mouse leaves it.. you can set up event listeners for either of those events as a starting point.
   * There are multiple ways to change the color of the divs, including:
     * adding a new class to the div
     * changing the div's background color using JavaScript.
4. Add a button to the top of the screen which will clear the current grid and send the user a popup asking for how many squares per side to make the new grid.  Once entered the new grid should be generated _in the same total space as before_ \(e.g. 960px wide\) and now you've got a new sketch pad. **Tip**: Set the limit for the user input to a maximum of 100. A larger number of squares results in more computer resources being used, resulting in possible delays, freezing, or crashing that we want to prevent.
   * Research `button` tags in HTML and how you can make a JavaScript function run when one is clicked.
   * Also check out `prompt`s
   * You should be able to enter `64` and have a brand new 64x64 grid pop up without changing the total amount of pixels used
5. \(Optional\): Instead of just changing the color of your grid from black to white \(for example\) have each pass through it with the mouse change to a completely random RGB value.   Then try having each pass just add another 10% of black to it so that only after 10 passes is the square completely black.
6. Push your project to GitHub!

