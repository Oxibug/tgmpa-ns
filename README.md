# TGMPA using Unique Namespace
TGM Plugin Activation Modified, Use unique namespace to be able to use multiple TGMPA in the same site simultaneously. 

==================

We Strongly Recommended to use this plugin in WordPress Plugins and Not inside WordPress Themes
For WordPress Themes, Use tgmpa-unique-cls instead
https://github.com/Oxibug/tgmpa-unique-cls

==================

How to use?

1. Search & Modify namespace **OxibugTGMPA** with your own project's namespace.

2. In class **TGMPA_Includes** .. Modify the following
  A. **TGMPA_MAIN_PREFIX** constant value with your own project prefix.
  B. **CONST_OXIBUG_TEXTDOMAIN** constant with your project text domain
  C. Modify menu, notices and page descriptions in **strings** array
  D. For WordPress Multisite, Change the key **parent_slug** value to **plugins.php** because you can't add plugins from sites and TGMPA still not compatible with Network
  
3. Copy those three php files in your project's, In this example we include in **inc\tgmpa** directories

**Finally, Including**

Include the TGMPA in the main project's file like **functions.php** in themes or your plugin's main file

Include the TGM_Plugin_Activation class, Depending on your implementation, you may want to change the include call:
 
**Parent Theme:**

`require_once     get_template_directory()    . '/path/to/tgmpa-includes.php';`
 
**Child Theme:**

`require_once     get_stylesheet_directory()  . '/path/to/tgmpa-includes.php';`
 
**Plugin:**

`require_once     dirname( __FILE__ )         . '/path/to/tgmpa-includes.php';`
 
**Example**

`require_once ( get_template_directory() . '/inc/tgmpa/tgmpa-includes.php' );`

`\OxibugTGMPA\TGMPA_Includes::instance( get_template_directory() . '/inc/tgmpa' );`
