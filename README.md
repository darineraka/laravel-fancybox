#FancyBox Utility for Laravel Views

##Credits

FancyBox version 1.3 - http://www.fancybox.net

jQuery - http://www.jquery.com

##What is it?

A simple class bundled with all of the required FancyBox 1.3 assets and some javascript to create simple FancyBox jQuery windows within your views.

iFrames are used to wrap the output of your target link inside FancyBox. There are 4 FancyBox profiles pre-configured which you can modify as needed.

##Installation

###Laravel Artisan Command-line

<code>php artisan bundle:install fancybox</code>

<code>php artisan bundle:publish fancybox</code>

###Add to application/bundles.php

<code>'fancybox' => array(),</code>

... or auto-start it:

<code>'fancybox' => array('auto' => true),</code>

###In bundles/fancybox/start.php

If you don't yet have jQuery loaded in your views, uncomment the asset container for jquery at lne 8:

<code>Asset::container('fancybox')->add('jquery','js/jquery-1.7.1.min.js');</code>

###In your view/layout/wherever your HTML header is

Add the following lines to the <head> of the view.


<code><?php echo Asset::container('fancybox')->scripts(); ?></code>

<code><?php echo Asset::container('fancybox')->styles(); ?></code>

##Usage

Within your view, use the FancyBox::html() method to generate HTML links for your taget pages.

<code><?php echo FancyBox::html (URL, LinkText, fancybox_profile, fancybox_title ); ?></code>

###Examples

####Wrap your signup@index controller action inside a FancyBox

<code><?php echo FancyBox::html(URL::to_action('signup@index'),'SignUp!','default','SignUp for Our Services'); ?></code>

##Customizing Fancy Boxes

*Edit the public/bundles/fancybox/fancybox.js file to your liking.

