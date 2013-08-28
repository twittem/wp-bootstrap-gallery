wp-bootstrap-gallery
======================

A custom WordPress gallery for dynamic thumbnail layout using Twitter Bootstrap 2 (https://github.com/twitter/bootstrap/) and the WordPress built in gallery manager. Once the script is setup it will alter the WordPress gallery shortcode to create a unique 
thumbnail layout based on the number of gallery items.

NOTE
----
This is a utility class is intended to format your WordPress gallery shortcode to use Twitter Bootstrap 2.2.2 thumbnail layouts, and does not include the dependant Twitter Bootstrap files You will have to install include them manually. 

Sample Image
------------
![Gallery Sample](http://d3j5vwomefv46c.cloudfront.net/photos/large/705506382.jpg?1356134094)

Installation
------------
Place **wp_bootstrap_gallery.php** in your Wordpress theme folder `/wp-content/your-theme/`

Open your WordPress themes **functions.php** file  `/wp-content/your-theme/functions.php` and add the following code:

```php
// Register Custom Gallery
require_once('wp_bootstrap_gallery.php');
```

Useage
------------
Simply create a WordPress post gallery as you usually would and the script will do the rest.

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

All layouts are created using Bootstrap span declarations for 12 columns and CSS floats. The script counts the number of images and assigns an array of spans for that number of images.

For example: If we want to layout 6 images where we have One 2/3 (8 Cols) width image on the left side with two 1/3 (4 Cols) width images on the right, and underneath two 1/3 (4 Cols) width images on the left side and one 2/3 (8 Cols) width image on the right. 

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
**1.0:**
+ Updated to div layout to fix float issues.
+ Licence now GPL-2.0+ to match WordPress.
+ Added a copy of the GPL-2.0+ Licence.

**0.1:**
+ Initial Commit

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/twittem/wp-bootstrap-gallery/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

