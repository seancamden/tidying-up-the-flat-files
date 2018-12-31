---
id: 278
title: WordPress add_options_page
date: 2010-12-03T22:29:07+00:00
author: seancamden
layout: revision
guid: http://www.seancamden.com/2010/12/03/277-revision/
permalink: /?p=278
---
Just documenting some of the things I&#8217;ve figured out about the add\_options\_page() function because it doesn&#8217;t, yet, have an entry in the WordPress codex.

This function adds an option page for a plugin to the WordPress dashboard.
  
add\_options\_page( $page\_title, $menu\_title, $capability, $menu_slug, $function);

  * $page_title &#8212; The string you put here will end up in the <title>
      tag for the options page.</li> 
      
      <li>
        $menu_title &#8212; The string you put here will end up in the menu on the left side of the dashboard, under settings by default.
      </li>
      <li>
        $capability &#8212; Put a specific variable here from the <a href="http://codex.wordpress.org/Roles_and_Capabilities">Roles and Capabilities</a> list. manage_options is a sensible choice.
      </li>
      <li>
        $menu_slug &#8212;
      </li>
      <li>
        $function &#8212; The string you put here must be the name of the function that will run when when this plugin&#8217;s admin page is selected.
      </li></ul>