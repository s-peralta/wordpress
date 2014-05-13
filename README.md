Beginners Guide to JavaScript
=============================

<!--All of the credit for this cheat sheet goes to <a href="http://blog.adtile.me/authors/viljami/">Viljami S.</a>. Majority of this JS Guide is a condensed/straight to the point version of his article.-->

Syntax / Snippets / Best Design Patterns


CSS LINK
--------

```
<link rel="stylesheet" href="<?php echo get_template_directory_uri(); ?>/css/normalize.css" type="text/css" media="screen" />
```

JS LINK
--------

```
<script src="<?php bloginfo('template_url'); ?>/js/vendor/hover.intent.js" type="text/javascript" charset="utf-8"></script>
```


Loop and Start While
--------

```
<?php if (have_posts()) : while (have_posts()) : the_post(); ?>
```

Title
--------
```
<?php the_title();?>
```

Navigation
--------
```
<?php wp_nav_menu(); ?>
```
OR Call a specific navigation menu

```
<?php wp_nav_menu(nav-primary); ?>
```

Date
--------
```
<?php the_date(); ?>
```

Content
--------
```
<?php the_content(); ?>
```

Thumbnail
--------
```
<?php the_post_thumbnail( $size, $attr ); ?> 
```


The Excerpt
--------
```
<?php the_excerpt(); ?> 
```


Loop and End While
--------
```
<?php endwhile; endif; ?>

```

List Pages
--------
```
<?php wp_list_pages( $args ); ?>
```

If Statement - If element exisits , do this
--------
```
<?php if ( has_post_thumbnail() ) {
the_post_thumbnail();
} ?>
```

The Permalink
--------
```
<?php the_permalink() ?>
```

INCLUDES
--------

The Header Template
--------
```
<?php get_header(); ?>
```
//The get_header() tag includes the file header.php or header-{name}.php from your current theme's directory. If that file is not found, it will instead include wp-includes/theme-compat/header.php.

The Footer Template
--------
```
<?php get_footer(); ?>
```
//The get_footer() tag includes the file footer.php or footer-{name}.php from your current theme's directory. If that file is not found, it will instead include wp-includes/theme-compat/footer.php.

The Sidebar Template
--------
```
<?php get_sidebar(); ?>
```
//The get_sidebar() tag includes the file sidebar.php or sidebar-{name}.php from your current theme's directory. If that file is not found, it will instead include wp-includes/theme-compat/sidebar.php.

Custom Template files
--------
```
<?php get_template_part(); ?>
```
//The get_template_part() tag includes the file {slug}.php or {slug}-{name}.php from your current theme's directory, a custom Include Tags other than header, sidebar, footer.

The Search Form Template
--------
```
<?php get_search_form(); ?>
```
//The get_search_form() tag includes the file searchform.php from your current theme's directory. If that file is not found, it will generate the search form.
// Permalink


Naming of Template
--------
```
<?php
/*
Template Name: One Column
*/

?>
```


Create Custom Post Type
--------
```
add_action( 'init', 'register_cpt_news' );
function register_cpt_news() {
	$post_type = 'news';
    $labels = array(
	    'name' => _x( 'News' ,$post_type ),
	    'singular_name' => _x( 'News' ,$post_type ),
	    'new_item' => _x( 'Add News' ,$post_type ),
	    'edit_item' => _x(  'Edit News' ,$post_type ),
	    'menu_name' => _x('News' ,$post_type ),
    );
    $args = array(
        'labels' => $labels,
        'hierarchical' => true,
        'description' => '',
        'supports' => array( 'title', 'editor', 'excerpt', 'thumbnail'),
        'public' => true,
        'show_ui' => true,
        'show_in_menu' => true,
        'show_in_nav_menus' => true,
        'publicly_queryable' => true,
        'exclude_from_search' => false,
        'has_archive' => false,
        'query_var' => true,
        'can_export' => true,
        'rewrite' => array('slug' => 'news', 'with_front' => false),
        'menu_icon' => 'dashicons-admin-page',
        'capability_type' => 'post'
    );
    register_post_type( $post_type, $args );
} 
```

ShortCode Grids - Foundation CSS Grid System
--------
```
function row( $atts, $content = null ) {
	return '<div class="content_block">' . do_shortcode($content) . '</div>';
}
add_shortcode('row', 'row');

function column_3( $atts, $content = null ) {
	return '<div class="large-3">' . do_shortcode($content) . '</div>';
}
add_shortcode('column_3', 'column_3');

function column_4( $atts, $content = null ) {
	return '<div class="large-4">' . do_shortcode($content) . '</div>';
}
add_shortcode('column_4', 'column_4');

function column_5( $atts, $content = null ) {		
	return '<div class="large-5">' . do_shortcode($content) . '</div>';
}
add_shortcode('column_5', 'column_5');

function column_6( $atts, $content = null ) {
   return '<div class="large-6">' . do_shortcode($content) . '</div>';
}
add_shortcode('column_6', 'column_6');

function column_7( $atts, $content = null ) {
   return '<div class="large-7">' . do_shortcode($content) . '</div>';
}
add_shortcode('column_7', 'column_7');

function column_8( $atts, $content = null ) {
   return '<div class="large-8">' . do_shortcode($content) . '</div>';
}
add_shortcode('column_8', 'column_8');

function column_12( $atts, $content = null ) {	
	return '<div class="large-12">' . do_shortcode($content) . '</div>';
}
add_shortcode('column_12', 'column_12');

--------


