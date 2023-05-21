**Flexbox Overview**

Every HTML element that’s a direct child of a flex container is an “item”. Flex items can be manipulated individually, but for the most part, it’s up to the container to determine their layout. The main purpose of flex items are to let their container know how many things it needs to position.

**Flex Containers**

The first step in using flexbox is to turn one of our HTML elements into a flex container. We do this with the display property, which should be familiar from the CSS Box Model chapter. By giving it a value of flex, we’re telling the browser that everything in the box should be rendered with flexbox instead of the default box model.

We have a flex container with one flex item in it. However, our page will look exactly like it did before because we haven’t told the container how to display its item.

**aligning a flex item**

After you’ve got a flex container, your next job is to define the horizontal alignment of its items. That’s what the justify-content property is for. 

This has the same effect as adding a margin: 0 auto declaration to the .menu element. But, notice how we did this by adding a property to the parent element (the flex container) instead of directly to the element we wanted to center (the flex item). Manipulating items through their containers like this is a common theme in flexbox, and it’s a bit of a divergence from how we’ve been positioning boxes thus far.

Other values for justify-content are shown below:

center
flex-start
flex-end
space-around
space-between

Try changing justify-content to flex-start and flex-end. This should align the menu to the left and right side of the browser window, respectively. Be sure to change it back to center before moving on. The last two options are only useful when you have multiple flex items in a container.

This turns our .menu into a nested flex container, and the space-around value spreads its items out across its entire width. You should see something like this:

The flex container automatically distributes extra horizontal space to either side of each item. The space-between value is similar, but it only adds that extra space between items. This is what we actually want for our example page, so go ahead and update the justify-content line:

Flex containers only know how to position elements that are one level deep (i.e., their child elements). They don’t care one bit about what’s inside their flex items. This means that grouping flex items is another weapon in your layout-creation arsenal. Wrapping a bunch of items in an extra <div> results in a totally different web page. For example, let’s say you want both the Sign Up and Login links to be on the right side of the page, as in the screenshot below. All we need to do is stick them in another <div>:

But, now we need to lay out the .links element because it’s using the default block layout mode. The solution: more nested flex containers! Add a new rule to our styles.css file that turns the .links element into a flex container: