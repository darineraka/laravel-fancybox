#FancyBox Utility for Laravel Views

##Credits

FancyBox version 1.3 - http://www.fancybox.net

jQuery - http://www.jquery.com

####Live Demo

http://laravel.bookerthedog.com

##What is it?

A simple class bundled with all of the required FancyBox 1.3 assets and some javascript to create simple FancyBox jQuery windows within your views.

iFrames are used to wrap the output of your target link inside FancyBox. There are 4 FancyBox profiles pre-configured which you can modify as needed.

##Installation

###Laravel Artisan Command-line

    php artisan bundle:install fancybox
    php artisan bundle:publish fancybox

###Add to application/bundles.php

    return array(
        'fancybox' => array(),
    );

... or auto-start it:

    return array(
        'fancybox' => array('auto' => true),
    );

###In bundles/fancybox/start.php

If you don't yet have jQuery loaded in your views, uncomment the asset container for jquery at lne 8:

    Asset::container('fancybox')->add('jquery','js/jquery-1.7.1.min.js');

###In your view/layout/wherever your HTML header is

Add the following lines to the HTML head of the view.

<code><?php echo Asset::container('fancybox')->scripts(); ?></code>

<code><?php echo Asset::container('fancybox')->styles(); ?></code>

##Usage

Within your view, use the FancyBox::html() method to generate HTML links for your taget pages.

    <?php echo FancyBox::html(URL, LinkText, fancybox_profile, fancybox_title ); ?>

###Examples

####Wrap your signup@index controller action inside a FancyBox

    <?php echo FancyBox::html(URL::to_action('signup@index'),'SignUp!','default','SignUp for Our Services'); ?>

##Customizing Fancy Boxes

Edit the public/bundles/fancybox/fancybox.js file to your liking with any of the FancyBox options.

Reference: http://fancybox.net/api

       $('a[rel="fancybox_default"]').fancybox({
             'titleShow'          : true,
             'title'              : $(this).attr('title'),
              'titlePosition'      : 'outside',
             'padding'            : 10,
             'margin'             : 20,
             'opacity'            : false,
             'modal'              : false,
             'cyclic'             : false,
             'scrolling'          : 'auto',
             'width'              : 800,
             'height'             : 400,
             'autoScale'          : true,
             'autoDimensions'     : true,
             'centerOnScroll'     : false,
             'hideOnOverlayClick' : true,
             'hideOnContentClick' : true,
             'enableEscapeButton' : true,
             'overlayShow'        : true,
             'overlayOpacity'     : 0.4,
             'overlayColor'       : '#000',
             'transitionIn'       : 'elastic',
             'transitionOut'      : 'elastic',
             'easingIn'           : 'easeInCirc',
             'easingOut'          : 'easeOutCirc',
             'speedIn'            : 600,
             'speedOut'           : 200,
             'ajax'               :
             {
             }
       });

