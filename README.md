# Ampersand #

A jQuery plugin to make use of the gorgeous Open Source Ampersands library: http://opensourceampersands.com/

### What does it do? ##

It's a little jQuery plugin that works on any jQuery object and wraps ampersands in a span for separate styling.


Friday; May 20, 2011 by Christopher Schmitt:

Added ability to find and replace double dashes with open sace, " -- ", and replace them with an em dash and remove the white space. 

More information on em dashes at http://www.alistapart.com/articles/emen/

### Why would I want to do that? ###

Ampersands are cool, but the default ampersands in many fonts are a bit lame. Having really nice ampersands can lift a design. 

Check out http://webofawesome.com for an example.

Friday; May 20, 2011 by CS:

Double dashes in content are not that attractive, especially when you want to represent a sudden break in a conversation. A good ole, slick em dash does the trick. 

Also, check out the included DEMO folder for a localized example of the script. 

## Usage ##

In your header, import jQuery and the ampersand plugin

    <script src="/static/javascripts/jquery-1.6.min.js"></script>
    <script src="/static/javascripts/ampersand_plugin.js"></script>
    
Now in your JavaScript, call ampersand on any element, eg:

    $('h1').ampersand();
    $('h2').ampersand();
    $('.intro').ampersand();
    
## CSS ##

You will notice that any ampersands are wrapped in span tags like so:

    <span class="ampersand">&amp;</span>
    
Now you just need to style these up. Visit http://opensourceampersands.com/ and download the font face kit of your choosing. Pop the font on your server and in your CSS do something like:


    @font-face {
        font-family: 'myfont';
        src: url('/path-to-font/myfont.eot');
        src: url('/path-to-font/myfont.eot?iefix') format('eot'),
             url('/path-to-font/myfont.woff') format('woff'),
             url('/path-to-font/myfont.ttf') format('truetype'),
             url('/path-to-font/myfont.svg#webfont0ZQvEa4G') format('svg');
        font-weight: normal;
        font-style: normal;
    }
    
    span.ampersand {
      font-family: myfont;
      font-size:1.2em;
      line-height:0.8em;
    }
    
Obviously, replace path-to-font and myfont with the actual values.

## Limitations ##

In it's current form, it will replace any ampersand, including ones inside hyperlinks. I should really get round to fixing this...

Friday; May 20, 2011 by CS:

Would need to split up the options to allow for finding and replacing specific characters in specific portions of a Web document. 

E.g., maybe something like this:

$("#main :header").ampersand( char : "&" ); // targets all HTML headers for ampersand upgrade
$("p").ampersand( char : " -- " ); // targets all paragraphs for double dash replacements 


