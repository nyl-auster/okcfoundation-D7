OKCFOUNDATION
---------------

OKC Foundation is an additionnal module for OKC Design theme.

https://github.com/nyl-auster/okcdesign

It allows to place block quickly on foundation css grid, by specifying foundation classes.

Edit block configuration and set foundation classes in drupal ini format, like this :

```
   * = large-6 columns
   <front> = small-12 columns
```

Where "*' represents the targeted pages, and "large-6 columns" are foundations css classes you want
to add to the block.

You may also use your theme infofile to place your blocks on the grid, which is the recommened
method as it allows to commit your work with your favourite VCS tool.

MORE ON CONFIGURATION
---------------------

 foundation classes MUST be specified in drupal ini format in
 the textarea from block configuration page.
```
   * = large-12 columns
   <front> = small-6 columns end
   node/4/* = large-12 columns
```

 key is the page targeted, and value is the foundation classes the block will use.
 "*" is a special wildcard meaning "for all pages".

 Additionnaly, you may use your theme info file to register your
 block grid informations, like this :

```
 okcfoundation_classes[block-15][*] = large-12 columns
 okcfoundation_classes[user-online][<front>] = large-1 columns
```

 Where "block-15" is "module-delta"; "*" is the targeted page and "large-12 columns" is foundation classes.
 module and delta are displayed in html classes (ex : for block-user-online, module is "user" and delta is "online"
 or in the block url configuration :
 
 for "admin/structure/block/manage/block/15/configure?destination=node", module is "block" and delta is "15".

 If a block as classes in both info files and block configuration page, the block configuration
 page wins againts theme info file.
 Juste empty textarea to make theme info file active again for this block.

 Using themeinfo file is a nice way to version your grids layout; there is no easy
 way to deploy configuration saved in textarea.
