Beginners Guide to JavaScript
=============================

<!--All of the credit for this cheat sheet goes to <a href="http://blog.adtile.me/authors/viljami/">Viljami S.</a>. Majority of this JS Guide is a condensed/straight to the point version of his article.-->

Syntax / Snippets / Best Design Patterns


----------------------------------------------------------------------------------------------------------------

CSS LINK

<link rel="stylesheet" href="<?php echo get_template_directory_uri(); ?>/css/normalize.css" type="text/css" media="screen" />

----------------------------------------------------------------------------------------------------------------

JS LINK

<script src="<?php bloginfo('template_url'); ?>/js/vendor/hover.intent.js" type="text/javascript" charset="utf-8"></script>

----------------------------------------------------------------------------------------------------------------

// Loop and Start While
<?php if (have_posts()) : while (have_posts()) : the_post(); ?>

// Title 
<?php the_title();?>

//Navigation
<?php wp_nav_menu(); ?>

//Date
<?php the_date(); ?>

//Content
<?php the_content(); ?> 

//Thumbnail
<?php the_post_thumbnail( $size, $attr ); ?> 

<?php if ( has_post_thumbnail() ) {
the_post_thumbnail();
} ?>

// The Excerpt
<?php the_excerpt(); ?> 


// Loop and End While
<?php endwhile; endif; ?>

</div>

List Pages

<?php wp_list_pages( $args ); ?>

INCLUDES

//The Header Template
<?php get_header(); ?>

//The get_header() tag includes the file header.php or header-{name}.php from your current theme's directory. If that file is not found, it will instead include wp-includes/theme-compat/header.php.

//The Footer Template
<?php get_footer(); ?>

//The get_footer() tag includes the file footer.php or footer-{name}.php from your current theme's directory. If that file is not found, it will instead include wp-includes/theme-compat/footer.php.

//The Sidebar Template
<?php get_sidebar(); ?>

//The get_sidebar() tag includes the file sidebar.php or sidebar-{name}.php from your current theme's directory. If that file is not found, it will instead include wp-includes/theme-compat/sidebar.php.

//Custom Template files
<?php get_template_part(); ?>

//The get_template_part() tag includes the file {slug}.php or {slug}-{name}.php from your current theme's directory, a custom Include Tags other than header, sidebar, footer.

//The Search Form Template
<?php get_search_form(); ?>

//The get_search_form() tag includes the file searchform.php from your current theme's directory. If that file is not found, it will generate the search form.
// Permalink

<?php the_permalink() ?>



See also get_search_form and Migrating Plugins and Themes to 2.7 for more detail.

//The Comments Template
<?php comments_template(); ?>
//This tag includes the file comments.

NAME OF TEMPLATES

<?php
/*
Template Name: One Column
*/

?>

INCLUDE TO POSTTYPE.PHP
require_once ( get_template_directory() . '/functions/post-types.php' );
