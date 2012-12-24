wp-bootstrap-gallery
======================

A custom Wordpress gallery for dynamic thumbnail layout using Twitter Bootstrap 2.2.2 (https://github.com/twitter/bootstrap/) thumbnails and the WordPress built in gallery manager.

NOTE
----
This is a utility class is intended to format your Wordpress gallery shortcode to use Twitter Bootstrap 2.2.2 thumbnail layouts, and does not include the dependant Twitter Bootstrap files You will have to install include them manually. 

Sample Image
------------
There is no online demo at this time. A sample screenshot can be found here http://twitpic.com/bo1g7i

Installation
------------
Place **wp_bootstrap_gallery.php** in your Wordpress theme folder `/wp-content/your-theme/`

Open your Wordpress themes **functions.php** file  `/wp-content/your-theme/functions.php` and add the following code:

```php
// Register Custom Gallery
require_once('wp_bootstrap_gallery.php');
```

Useage
------------
Simply create a Wordpress post gallery as you usually would and the script will do the rest.


Supported Layouts
------------
+ 1 Image - One full width image 
+ 2 Images - Two half width images 
+ 3 Images - One 3/4 width image with two 1/4 width images to the right
+ 4 Images - One full width image with three 1/3 width images underneath
+ 5 Images - Two half width images with four 1/4 width images underneath
+ 6 Images - One 2/3 width image with two 1/3 width images to the right, and three 1/3 width images underneath 
+ 7 or more images -  One full width image with two 1/2 width images underneath. All remaining images 1/3 width underneath


Creating custom layouts
------------

All layouts are created using Bootstrap span declarations for 12 collums and css floats. The script counts the number of images and adds assigns an array of images spans for that number of images.

For example: If we want to do a layout 6 images where we have One 2/3 (8 Cols) width image on the left side with two 1/3 (4 Cols) width images on the right, and underneath two 1/3 (4 Cols) width images on the left side and one 2/3 (8 Cols) width image on the right.

**Find:**
```php
	case 6:
	    $span_array = array(8,4,4,4,4,4);
		break;
```

**Replace With:**
```php
	case 6:
	    $span_array = array(8,4,4,4,4,8);
		break;
```


Changelog
------------
**0.1:**
+ Initial Commit


Known Issues
------------
+ Thumbnails are not spaced properly when using the responsive framework. I am working on a fix for this but am currently stuck. I want the class to utilize the default Bootstrap CSS with no modifications.  


Todo
------------
+ Fix thumbnail padding
+ Include custom thumbnail sizes
+ Select thumbnail size bases in span for optimized loading