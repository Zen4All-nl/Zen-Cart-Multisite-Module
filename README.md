<div id="contentWrapper">
  <h1>Multi Site Module v1.0 for ZC 1.5.1 Documentation</h1>
  <div id="contentMenu">
    <ul>
      <li><a href="#introduction">Introduction</a></li>
      <li><a href="#whats_new">What's New</a></li>
      <li><a href="#installation">Installation</a></li>
      <li><a href="#upgrade">Upgrade</a></li>
      <li><a href="#configuration">Configuration</a></li>
      <li><a href="#version_history">Version History</a></li>
      <li><a href="#faqs">FAQs</a></li>
      <li><a href="#support">Support</a></li>
      <li><a href="#donations">Donations</a></li>
    </ul>
  </div>
  <h2><a name="introduction" id="introduction"></a>Introduction</h2>
  <div id="contentDescription">
    <p>This contribution Multi Site support to Zen Cart.</p>
    <p>Credit is due to <a href="http://www.medea.co.uk/" target="_blank">Gerome Romey</a> for creating Multi Site 0.4, and the <a href="http://www.zen-cart.com/index.php" target="_blank">Zen Cart Team</a> for creating the best open source ecommerce package available!</p>
  </div>
  <h2><a name="whats_new" id="whats_new"></a>What's New</h2>
  <div id="contentDescription">
    <p>Version 1.0 - Release Date: 2012-xx-xx</p>
    <ul>
    <li>Updated most files to contain the code of Zen Cart 1.5.1</li>
    <li>Added the admin module registration for Zen Cart 1.5.x</li>
    <li>The module is now multi lingual on the admin side as well as the Frontend</li>
    <li>The sitelink sidebox has its own tpl file</li>
    <li>Added SyntaxHightlighter 1.5.1 to multisite.php for easier reading and copiyng code</li>
    </ul>
  </div>
  <h2><a name="installation" id="installation"></a>Installation</h2>
  <div id="contentDescription">
    <p>This version of Multi Site has been updated and tested for use with Zen Cart 1.5.1</p>
<p>Please remember to <strong>backup your website files and database</strong> before you continue.</p>
    <p>To install Multi Site follow the steps below.</p>
    <ol>
      <li>Download the latest version of Multi Site from <span style="color:red;font-size:smaller;">(this link will be edited when the final release is on zen-cart.com)</span>:<br />
        <a href="http://www.zen-cart.com/index.php?main_page=product_contrib_info&amp;products_id=273" target="_blank">https://github.com/Zen4All/Zen-Cart-Multisite-Module/archive/Beta-for-ZC-1.5.1.zip<br />
        <br />
        </a></li>
      <li>Extract the contents  (of Beta-for-ZC-1.5.1.zip) to a temporary location, keeping the file structure intact. (Note: If you can't open this file try using <a href="http://www.7-zip.org/" target="_blank">7-Zip</a>, it's free!)<br />
        <br />
      </li>
      <li>Open the <strong>4_SQL_Files</strong> folder and then open the install.sql file in a text editor (not microsoft word) and copy all of the text to the clipboard. Next go to (Admin &gt; Tools &gt; Install SQL Patches) in your Zen Cart admin and paste the contents of install.sql into the text area and then press the send button. Or copy the code from below<br />
      <pre name="code" class="sql">ALTER TABLE orders ADD order_site varchar(30) NOT NULL DEFAULT 'no';</pre>
        This adds the column 'order_site' to the 'Orders' Table to know which site orders originate from.
        <br />
      </li>
      <li><span style="color:#900"><b>Alternative to step 3.</b></span> Open phpMyAdmin for your site and navigate to your database. Choose 'Import' and then 'choose file' and navigate to and select install.sql then choose 'Go'.<br /><br />
      </li>
      <li>Open the <strong>1_New_Files</strong> folder<br />
        <br />
      </li>
      <li>Rename the following folders to match your admin folder name.
        <br />
        <ul>
          <li><strong>YOUR_ADMIN</strong></li>
        </ul><br />
      </li>
      <li>Upload the entire contents of the <strong>1_New_Files</strong> folder, includes folder and the admin folder to your server, again keeping the file structure intact.
        <br />
        <ul>
          <li>YOUR_ADMIN/multisite.php</li>
          <li>YOUR_ADMIN/includes/autoloaders/config.multisite.php</li>
          <li>YOUR_ADMIN/includes/extra_datafiles/multisite.php</li>
          <li>YOUR_ADMIN/includes/init_includes/init_multisite_config.php</li>
          <li>YOUR_ADMIN/includes/languages/dutch/multisite.php</li>
          <li>YOUR_ADMIN/includes/languages/dutch/extra_definitions/multisite.php</li>
          <li>YOUR_ADMIN/includes/languages/dutch/extra_definitions/order_site.php</li>
          <li>YOUR_ADMIN/includes/languages/english/multisite.php</li>
          <li>YOUR_ADMIN/includes/languages/english/extra_definitions/multisite.php</li>
          <li>YOUR_ADMIN/includes/languages/english/extra_definitions/order_site.php</li>
          <li>YOUR_ADMIN/includes/clipboard.swf</li>
          <li>YOUR_ADMIN/includes/shBrushPhp.js</li>
          <li>YOUR_ADMIN/includes/shBrushXml.js</li>
          <li>YOUR_ADMIN/includes/shCore.js</li>
          <li>YOUR_ADMIN/includes/SyntaxHighlighter.css</li>
          <li>includes/config_sites/2fastshoes.com_config.php <span style="color:red;font-size:smaller;">(This is only an example config file)</span></li>
          <li>includes/config_sites/help.txt</li>
          <li>includes/config_sites/sites_switch.php</li>
          <li>includes/config_sites/www.example.com_config.php <span style="color:red;font-size:smaller;">(This is only an example config file)</span></li>
          <li>includes/functions/extra_functions/cat_filter.php</li>
          <li>includes/languages/dutch/extra_definitions/site_links.php</li>
          <li>includes/languages/english/extra_definitions/site_links.php</li>
          <li>includes/modules/sideboxes/site_links.php</li>
          <li>includes/templates/template_default/sideboxes/tpl_site_links.php</li>
        </ul>
        <br />
      </li>
      <li>Open the<strong> 2_Required_Core_Edits</strong> folder.<br />
        <br />
      </li>
      <li>Rename the following folder to match your admin folder name.
        <br />
        <ul>
          <li><strong>YOUR_ADMIN</strong></li>
        </ul><br />
      </li>
      <li>Before we proceed there are a couple of things to note. The files in the '2_Required_Core_Edits' folder are of two types. The first type of file CANNOT be over-ridden by the use of templates, the second type is of course the opposite and CAN be overridden by the use of Zen-Cart templates. You can read more about Zen-Cart templates on the Zen-Cart website. Thefiles in the folders listed in the next step are the files which CAN be overridden by the use of templates. In the previous version it was advised to just overide the default template files, but I advise against it. It may mean less work now, but in a future upgrade of your Zen Cart it complicates updates.<br>
        It is also possible your custom template already contains files in the mentioned folders, which would mean the old method is useless.
        <br />
        <br />
      </li>
      <li>The next folders contain files that have to replace the existing zencart files by the use of the templates. Rename the following folders to match your template folder name.<strong> You need to do this for every template installed !!</strong> The files in these folders <strong>may</strong> need merging with existing files in your template.<br />
        <ul>
          <li><strong>includes/modules/YOUR_TEMPLATE</strong></li>
          <li><strong>includes/modules/sideboxes/YOUR_TEMPLATE</strong></li>
          <li><strong>includes/templates/YOUR_TEMPLATE</strong></li>
        </ul>
      In the next folder there also already may be files present<br />
        <ul>
          <li><strong>includes/init_includes/overides</strong></li>
        </ul>
        </strong><br />
      </li>
      <li>Upload and MERGE where needed the entire contents of the <strong>2_Required_Core_Edits</strong> folder, includes folder and the admin folder to your server, again keeping the file structure intact.
        <br />
        <ul>
          <li>YOUR_ADMIN/orders.php</li>
          <li>includes/classes/category_tree.php</li>
          <li>includes/classes/order.php</li>
          <li>includes/classes/site_map.php</li>
          <li>includes/functions/functions_categories.php</li>
          <li>includes/functions/functions_lookups.php</li>
          <li>includes/init_includes/overrides/init_add_crumbs.php</li>
          <li>includes/init_includes/overrides/init_category_path.php</li>
          <li>includes/init_includes/overrides/init_sessions.php</li>
          <li>includes/init_includes/overrides/init_templates.php</li>
          <li>includes/pages/advanced_search_result/header_php.php</li>
          <li>includes/pages/featured_products/header_php.php</li>
          <li>includes/pages/index/main_template_vars.php</li>
          <li>includes/pages/products_all/header_php.php</li>
          <li>includes/pages/products_new/header_php.php</li>
          <li>includes/pages/reviews/header_php.php</li>
          <li>includes/pages/specials/main_template_vars.php</li>
          <li>includes/modules/sideboxes/YOUR_TEMPLATE/best_sellers.php</li>
          <li>includes/modules/sideboxes/YOUR_TEMPLATE/categories.php</li>
          <li>includes/modules/sideboxes/YOUR_TEMPLATE/document_categories.php</li>
          <li>includes/modules/sideboxes/YOUR_TEMPLATE/featured.php</li>
          <li>includes/modules/sideboxes/YOUR_TEMPLATE/manufacturers.php</li>
          <li>includes/modules/sideboxes/YOUR_TEMPLATE/reviews.php</li>
          <li>includes/modules/sideboxes/YOUR_TEMPLATE/specials.php</li>
          <li>includes/modules/sideboxes/YOUR_TEMPLATE/whats_new.php</li>
          <li>includes/modules/YOUR_TEMPLATE/categories_tabs.php</li>
          <li>includes/modules/YOUR_TEMPLATE/category_row.php</li>
          <li>includes/modules/YOUR_TEMPLATE/featured_products.php</li>
          <li>includes/modules/YOUR_TEMPLATE/meta_tags.php</li>
          <li>includes/modules/YOUR_TEMPLATE/new_products.php</li>
          <li>includes/modules/YOUR_TEMPLATE/product_listing.php</li>
          <li>includes/modules/YOUR_TEMPLATE/specials_index.php</li>
          <li>includes/templates/YOUR_TEMPLATE/sideboxes/tpl_categories.php</li>
          <li>includes/templates/YOUR_TEMPLATE/templates/tpl_advanced_search_default.php</li>
          <li></li>
        </ul>
        <br />
      </li>
      <li>Make a Template for each site
        <ul>
          <li>We assume that you already have a Zen-cart shop installed with some categories and products. You need to have a 2nd template that will be use for your 2nd shop. You can simply copy and past the one from your folder "includes/template/[YOUR_TEMPLATE]" Or you can download some from www.zen-cart.com.<br />
          <br />
          </li>
          <li>TIP: In order to make the things easy, I highly advice you to rename the template to the name of
each of your site. In this way, you will find easily the folder of the shop you want to modify...
When you rename your template's name, think of renaming every overriding folder too !
These folders should be:
            <ul>
              <li>includes/templates/YOUR_TEMPLATE</li>
              <li>includes/languages/YOUR_LANGUAGE/YOUR_TEMPLATE</li>
              <li>includes/languages/YOUR_LANGUAGE/extra_definitions/YOUR_TEMPLATE</li>
              <li>includes/languages/YOUR_LANGUAGE/html_includes/YOUR_TEMPLATE</li>
              <li>includes/languages/YOUR_LANGUAGE/modules/order_total/YOUR_TEMPLATE</li>
              <li>includes/languages/YOUR_LANGUAGE/modules/payment[YOUR_TEMPLATE</li>
              <li>includes/languages/YOUR_LANGUAGE/modules/shipping/YOUR_TEMPLATE</li>
              <li>includes/languages/YOUR_LANGUAGE/modules/YOUR_TEMPLATE</li>
              <li>includes/languages/YOUR_LANGUAGE/modules/sideboxes/YOUR_TEMPLATE</li>
            </ul><br />
          </li>
          <li>Do not use a template for two sites, otherwise, you will be obliged to have the same language files too (same shops' name and same sideboxes position)<br />
          <br /></li>
          <li>In the includes/templates/[YOUR_TEMPLATE]/template_info.php, change the template_name to the name of your site that uses the template:
              <pre name="code" class="php">$template_name = 'mysite';</pre>
          </li>
          <li>So, if your sites are called www.site1.com and www.site2.net Then your should rename your template to site1 and site2.<br />The file includes/templates/site1/template_info.php should have the line:
            <pre name="code" class="php">$template_name = 'site1';</pre>
          <br />The file includes/templates/site2/template_info.php should have the line:
            <pre name="code" class="php">$template_name = 'site1';</pre>
          <br />This will help you later in the admin section; the template selector is now only use for choose the site for which you want to change the sidebox setting.<br /><br />
          </li>
        </ul>
      <li>Create the configuration files of your sites
        <p>Add this line at the beginning of your "includes/configure.php":
        <pre name="code" class="php">include_once('includes/config_sites/sites_switch.php');</pre></p>
      </li>
    </ol>
    <p>Multi Site is now installed and ready to use!</p>
    <p>Go to the configuration chapter to read more on how to configure your sites.</p>
  </div>
  <h2><a name="upgrade" id="upgrade"></a>Upgrade <span style="color: #F00;">( Do a fresh installation)</span></h2>
  <div id="contentDescription" >
  <p><strong>Upgrading from previous versions is not supported</strong> Please do a fresh instaltion</p>
  </div>
  <h2><a name="configuration" id="configuration"></a>Configuration</h2>
  <div id="contentDescription">
  <ol>
    <li>How to change the configuration for a specific shop?
      <p>The Zen-cart configuration is contained in the database and declared in constants at runtime. The configuration in the admin section stands for the "default configuration". You can override this configuration by defining the constants of the setting that you want to change directly in the config file related to one of your site (folder "includes/config_sites")</p>
      <p>You now have to create a config file for each one of your sites! The name of the file has to be: "www.site1.com_config.php" (for the site targeted by the domain name www.site1.com). This file "www.site1.com_config.php" has to contain:</p>
      <pre name="code" class="php">&lt;?php
$template_dir = "site1";
define('SITE_NAME','site1');
?&gt;</pre>
      <p>$template_dir is the template that you want to use for this site SITE_NAME is the name of your site (use for the category filter and for the order page in admin; column site).</p>
      <p>You can add constants for overriding of the default configuration from the database or from the configure.php, the following lines are only exemples:</p>
      <p>//Do not display the categories at the main page for this site:</p>
      <pre name="code" class="php">define('SHOW_CATEGORIES_ALWAYS','0');</pre>
      <p>//Display the categories of ID 5 as the main category of the website:</p>
      <pre name="code" class="php">define('CATEGORIES_START_MAIN','5');</pre>
      <p>//Change the Contact us email address:</p>
      <pre name="code" class="php">define('STORE_OWNER_EMAIL_ADDRESS','an_email@address.com')</pre>
      <p>//Enable the SSL only for this site:</p>
      <pre name="code" class="php">define('ENABLE_SSL', 'true'); //assuming as 'false' in configure.php</pre>
      <p>Remember that the code above is only here as exemple and do not always need to be use.</p>
      <p>If you don't know what is the name of the constants of a configuration setting, you can find it by clicking in your admin on Tools => Multisite Tools. This brings up the Multisite page. Here you click on the link "Display Configuration for a new site". Now all you constants are shown. You can select and copy them to the new config file </p>
    </li>
    <li>Category Filter
      <p>The MultiSite module works by filtering the categories with the function cat_filter. It only displays the categories that have the name of the site (constant SITE_NAME) in html comment in the categories descriptions. Therefore, you need to add this description to EVERY categories description that have to be display in a shop. Sub categories Included!</p>
      <p>Example of html comment:</p>
      <pre name="code" class="html"><!--site1-site2-site3--> Description of a category that will be displayed in site1, site2 and site3.</pre>
      <p>This comment will allow this category for the shops site1 site2 and site3. the site names HAVE to be separated by "-".<br />
If you have Lots of categories, it may be quicker to add the categories trough the Multisite tool. Go to Tools =&gt; Multisite Tools, and click &quot;Display the relations Categories/Sites&quot;</p>
      <p>once you have put your html comments in your categories, they should appear on the front end of your shop. If a category has no html comment, it won't be displayed in any sites.</p>
    </li>
  </ol>
  </div>
  <h2><a name="version_history" id="version_history"></a>Version History</h2>
  <div id="contentDescription">
  	<p>Version 1.0 Current- Release Date: 2012-xx-xx</p>
    <ul>
    <li>Removed []</li>
    <li>modified [includes/classes/]
      <ul>
        <li>some text</li></ul></li><li>
    </li>
    </ul>
    <p>Version 0.4 -  Release Date: 2007-08-07</p>
    <ul>
      <li>Initial release</li>
    </ul>
  </div>
  <h2><a name="faqs" id="faqs"></a>FAQs</h2>
  <div id="contentDescription">
    <p>&nbsp;</p>
  </div>
  <h2><a name="support" id="support"></a>Support</h2>
  <div id="contentDescription">
    <p>You will find the official support thread at the link below. Please feel free to post any comments or questions there.</p><a href="http://www.zen-cart.com/showthread.php?63997-MultiSite-Module-Support-Thread">Support thread</a>
  </div>
</div>
