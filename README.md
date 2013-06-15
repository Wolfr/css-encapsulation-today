CSS encapsulation today
=======================

This repo attempts to document the ways to have CSS encapsulation today.

In a drawing:

<img src="http://f.cl.ly/items/1L0R3x2o342T1F3K162J/Screen%20Shot%202013-06-15%20at%2011.15.19.png">

Use cases (the why):

* Re-using components across websites
  * A component can be anything: a video player, a PDF viewer, a weather widget, an HTML5 ad

# iframe 

See the `iframe/` folder.

An iframe in the most basic encapsulation method and since it's so old it works everywhere. Basically you are referencing a new HTML page inside the other one.

* Advantages
  * Easy to implement
  * Works everywhere

* Disadvantages
  * 2 HTTP requests for the HTML
  * The element container (iframe) doesn't scale with the page automatically
  * Parent site can't touch what is happening in the frame
  
# Scoped stylesheets

Scoped stylesheets are **not a solution** to CSS encapsulation. The only thing scoped styles does is limit styles to a particular element in the DOM. It doesn't prevent styles from the parent page to cascade to the "component".

See the `style-scoped/` folder.

* Advantages
  * Easy to implement
  
* Disadvantages
  * Browser support is limited (there is a <a href="https://github.com/thingsinjars/jQuery-Scoped-CSS-plugin">polyfill</a>)
  * **Not a solution** since styles bleed through

### resources

* <a href="http://www.html5forwebdesigners.com/semantics/index.html#scoped_styles">Scoped styles - HTML5 for web designers</a>
* <a href="http://css-tricks.com/saving-the-day-with-scoped-css/">Saving the Day with Scoped CSS</a> by Arley McBlain

# Shadow DOM

Possibly the best solution. What we actually want.

No demo yet. See the `shadow-dom` branch for an attempt. Please PR this repo if you are good with Polymer and/or the shadow DOM.

* Advantages 
  * Encapsulate styles OR provide hooks for styling to parent element (see Reaching into Shadows with CSS <a href="http://glazkov.com/2011/01/14/what-the-heck-is-shadow-dom/">here</a>)
  
* Disadvantages 
  * Has to be polyfilled for now using Polymer

See <a href="http://www.polymer-project.org/">Polymer project</a>.

### Resources

* <a href="http://www.youtube.com/watch?feature=player_embedded&v=0g0oOOT86NY#at=1777">Web components in action - Google I/O</a>
* <a href="http://glazkov.com/2011/01/14/what-the-heck-is-shadow-dom/">What the Heck is Shadow DOM?</a>
* <a href="http://www.html5rocks.com/en/tutorials/webcomponents/shadowdom-201/">Shadow DOM 201: CSS and Styling</a>
