Different favicon on different pages\
used theme [OceanWP](https://wordpress.org/themes/oceanwp/).\
add in functions.php(theme file editor)
```
function custom_page_favicon() {
  $favicon_map = array(
    'blog' => 'https://demo.onfdc.com/favicon/wp-content/uploads/2023/06/12.png',
    'blog-1' => 'https://demo.onfdc.com/favicon/wp-content/uploads/2023/06/365.png'
  );

  $default_favicon = 'https://demo.onfdc.com/favicon/wp-content/uploads/2023/06/cropped-site.png';

  $current_page_slug = get_post_field('post_name', get_queried_object_id());

  if (isset($favicon_map[$current_page_slug])) {
    echo '<link rel="icon" href="' . $favicon_map[$current_page_slug] . '" type="image/png" />';
  } else {
    echo '<link rel="icon" href="' . $default_favicon . '" type="image/png" />';
  }
}
add_action('wp_head', 'custom_page_favicon');
```
<a href="mailto:manojchurya@gmail.com?subject=GitHub%20favicon%20different%20pages"><img src="https://img.shields.io/badge/gmail-%23DD0031.svg?&style=for-the-badge&logo=gmail&logoColor=white"/></a>
