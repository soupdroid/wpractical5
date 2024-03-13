# Practical 5 (Week 3) - Responsive layouts & Flexbox

In this practical you will first get familiar with using Flexbox before moving on to implementation of a responsive layout.

## Stage 1: Flexbox Familiarisation 
Open [Flexbox Froggy](http://flexboxfroggy.com/). Try to complete all 24 levels.

## Stage 2: Implementing Flexbox

The exercises in this stage use the starter code in this repository along with these instructions. In VS Code, open the starter code folder called “stage2” and run index.html in Chrome using the Live Server.

For each of the exercises in this stage, you will write flexbox CSS to recreate the layouts shown below. The HTML files and global CSS (main.css) is provided in the starter code. 

index.html shows the default layout with the basic styling provided by main.css. The other HTML files are identical except for links to additional stylesheets. **You should only edit the stylesheet associated with exercise and only use flexbox (no inline-block, no float, no position etc).**

These exercises go beyond what was covered in class. You can find all the information you need here:[https://css-tricks.com/snippets/css/a-guide-to-flexbox/ ](https://css-tricks.com/snippets/css/a-guide-to-flexbox/ )

### Exercise 2.1: Put the squares on one line
Edit **stage2/styles/exercise2_1.css** to make the green squares appear side by side with no gap between them. 
Check your edits by viewing stage2/exercise2_1.html in Chrome (you should be able to just click the link from stage2/index.html).

![Screenshot for Ex2.1](https://github.com/IM-WADD/Week3Practical1/assets/5978932/7dde3a22-f39c-4ef5-8024-ac7f1c55116d)

You should only need to set `display` to `flex`. Your job is to figure out which element(s) need the property.

### Exercise 2.2: Reverse the squares
Edit **stage2/styles/exercise2_2.css** to make the green squares appear side by side in _reverse order_ with no gap between them. Square 9 should be against the left edge of the window.

![Screenshot for Ex2.2](https://github.com/IM-WADD/Week3Practical1/assets/5978932/98b1ebd5-616f-47e3-8262-b286e8925eda)

### Exercise 2.3: Put the squares in grid
Edit **stage2/styles/exercise2_3.css** to put the squares in a 3 x 3 grid as pictured. The grid should be in the horizontal centre of the window. You can set the dimensions of the container element if needed. There is a particular flexbox property that allows you to set the wrapping of items in a container element.

![Screenshot for Ex2.3](https://github.com/IM-WADD/Week3Practical1/assets/5978932/be2014fd-eba6-46ab-982c-4fb26ee1bdfb)

### Exercise 2.4: Put the squares in grid 2
Edit **stage2/styles/exercise2_4.css** to put the squares in a 3 x 3 grid as pictured. The grid should be in the horizontal centre of the window. The key difference between this exercise and the previous one is the order of squares 4-6. You can set the dimensions of the container if needed. The `order` property will be helpful.

![Screenshot for Ex2.4](https://github.com/IM-WADD/Week3Practical1/assets/5978932/dc3cf570-f768-4681-9140-4dcde236010e)

### Exercise 2.5: Make a step layout
Edit **stage2/styles/exercise2_5.css** to put the squares in a stepped layout as pictured. The key flexbox property is `align-self`. You will also need to give the container element a height and change the margin of some of the items in the container.

![Screenshot for Ex2.5](https://github.com/IM-WADD/Week3Practical1/assets/5978932/a70e4a80-e5ab-4302-a2ac-ab3bdf51d4e4)

## Stage 3: Media Queries
Make a new copy of the York University Press website you created last practical. In this stage, you will add media queries to the CSS to make the site layout work for small and medium-sized devices. Screenshots of my media query layouts are shown on the last page of this document.

### Exercise 3.1: Evaluate the current layout in the device simulator
Run the website in Chrome using the Live Preview extension and open the device simulator, which you can find in Developer Tools. Set the device simulator to responsive mode then view the site at different breakpoints by clicking the grey bars above the site. Scroll the full length of the site at each breakpoint and determine when and how the layout stops working on smaller screens. The breakpoint at which you start to see problems will depend on the details of your design. My layout starts to have problems at the tablet breakpoint (768px) and gets worse the smaller the breakpoint.

Some things to look out for:
- Having to scroll left and right to see some content
- Overlapping text
- Images that are too big for the screen
- Very narrow lines of text

### Exercise 3.2: Improve the existing code
Add the viewport meta tag to the `<head>` of the HTML file:
```
<meta name="viewport" content="width=device-width, initial-scale=1">
```

From now on, include this meta tag in every HTML file you create.

Next, consider converting some of the existing desktop-friendly layout that was created using the inline-block approach to flexbox. This is not required but flexbox is often more suited to responsive layouts (i.e., requires fewer style overrides for small devices). In my case, simply using flexbox instead of the inline-block approach resolved several of my responsiveness issues, particularly at the tablet breakpoint.

Flexbox is recommended for the header section, the main navigation, the middle section (`<main>` and `<aside>` in side-by-side columns), and the “Other Headlines” section.

### Exercise 3.3: Customise the layout for medium-sized devices
Remove the page background colour and margins around the content area for all devices smaller than 768px. To do this, add the following media query and override the appropriate style rules (one example of overriding styles is provided).
```
@media screen and (max-width:768px) {
    body {
        background-color: white;
    }
}
```
Here are some more changes to make for medium-sized devices:
- Make the date left aligned.
- Change the middle section of the page from a two-column layout to a single column. Make sure the `<main>` and `<aside>` take up the full width of their container.
- Now that the “Most Popular” section is full width on tablets, make the three sections it contains appear side by side.

Create further customizations if they will improve the layout on tablets.

### Exercise 3.4: Further customize the layout for small devices
For this exercise, we’ll define small devices as those under 425px wide. Add a media query with a `max-width` of 425px and make the following layout changes for small devices only:
- Remove the float on the main story image, centre align it and make sure it’s no bigger than the width of its container. You will need to use the `max-width` property.
- In the previous exercise, you converted the “Most Popular” section from a single column to a three-column layout for all devices less than 768px. This style should only apply to tablets. For devices with a maximum width of 425 pixels, the layout of the “Most Popular” section should be the same as it is for devices bigger than 768px.

Create further customizations if they will improve the layout on the smallest devices. Be sure to check how your site looks at the smallest breakpoint.

## Stage 4: (Optional) Make Your Portfolio Responsive
If you finish early, add go back to the portfolio you have worked on in previous practicals and check how it appears on small devices. Adjust the layout as needed.

