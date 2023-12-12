# grid-template-columns-example-2
Created with CodeSandbox

<h2>This is a fancy demo of using CSS display:grid named columns</h2>

Credit goes to Kevin Powell who demoed this, 
I recreated his demo on my own, to get a better feel for working with it.

This demos CSS display: grid named:

<pre>
.primary-header__layout {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;

  /* grid-column: full-width; */
  grid-column: breakout-right; /* it breaks out to the right */
  /*grid-column: breakout-left; /* it breaks out to the left */
}
</pre>

You can swith this class between all these settings:
<pre>
grid-column: full-width;
grid-column: breakout-right;
grid-column: full-width;
grid-column: breakout-left;
</pre>

To understand how these names are defined controlled, it's here:

<pre>
.content-grid {
  display: grid;
  grid-template-columns:
    [full-width-start breakout-left-start] minmax(2rem, 1fr)
    [content-start breakout-right-start left-side-start] min(33%, 20rem)
    [left-side-end] min(33% - 6rem, 20rem)
    [content-end] 2rem
    [right-side-start] min(33%, 20rem)
    [breakout-left-end right-side-end] minmax(2rem, 1fr)
    [breakout-right-end full-width-end];
}
</pre>
Each grid line is named within square brackets, followed by a defined space using CSS units, which may include functions like minmax() or min(). This method precisely structures the grid layout.
>Note: you can have multiple names for a line name, which allows you to define overlapping areas like `breakout-right` and `content`

Any lines that have the same prefix but one ends in `<prefix>-start` and another ends in `<prefix>-end`, will be able to set just `grid-column:prefix;` and it will automagically start and end correctly! 🪄



Kevin's Video:
<a href="https://www.youtube.com/watch?v=cf-J4ffMBfo" target="kevins-video">https://www.youtube.com/watch?v=cf-J4ffMBfo</a>

Kevin's channel:
<a href="https://www.youtube.com/@KevinPowell" target="kevins-yt">https://www.youtube.com/@KevinPowell</a>

![screenshot of page](/screenshot.png)
