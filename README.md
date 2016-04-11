# Examen2016
### Debug

#### index.php
```html
<?php get_header ?>

	<h1>This is my index</h1>

  <p>This is unique content.</p>

<?php get_footer ?>
```

#### header.php
```html
<!doctype html>
<html <?php language_attributes(); ?>>
	<head>
		<meta charset="<?php bloginfo('charset'); ?>">
		<title><?php bloginfo('name'); ?><?php wp_title('|'); ?></title>
    	<meta name="description" content="<?php bloginfo('description'); ?>">
	</head>

  <?php
    if( is_front_page() ):
      $homepage_classes = array( 'homepage', 'my-class', 'extra-class' );
    else:
      $homepage_classes = array( 'no-homepage');
    endif;
  ?>

	<body <?php body_class( $homepage_classes ); ?> >

		<?php wp_nav_menu(array('theme_location'=>'primary')); ?>
```
#### footer.php
```html

	<footer>
		<p>This is my footer</p>
		<?php wp_nav_menu(array('theme_location'=>'secondary')); ?>
	</footer>

	<?php wp_footer(); ?>

	</body>
</html>
```


#### functions.php
```php
<?php

function syntra_theme_setup {
	add_theme_support(menus)
	register_nav_menu(primary, Primary Header Menu)
	register_nav_menu(secondary, Footer Menu)
}
add_action(init, syntra_theme_setup)
add_theme_support(post-thumbnails)
add_theme_support(post-formats, array( image, video, gallery ))

?>
```

### Maak
Maak een pagina template aan voor de leden pagina.
De opmaak van ieder lid moet worden gescheiden in een apparte file.
We gaan ervan uit dat de functionaliteit van het leden post type aanwezig is.
