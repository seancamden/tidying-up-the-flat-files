---
id: 277
title: WordPress add_options_page
date: 2010-12-03T22:30:03+00:00
author: seancamden
layout: post
guid: http://www.seancamden.com/?p=277
permalink: /?p=277
st_cached:
  - '<ul class="socialize-this"><li><a href="http://del.icio.us/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D277&title=WordPress+add_options_page" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/del.png" width="48px" height="48px" alt="Delicious" title="Delicious" /></a></li><li><a href="http://www.facebook.com/sharer.php?u=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D277&t=WordPress+add_options_page" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/facebook.png" width="48px" height="48px" alt="Facebook" title="Facebook" /></a></li><li><a href="http://digg.com/submit?phase=2&url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D277" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/digg.png" width="48px" height="48px" alt="Digg" title="Digg" /></a></li><li><a href="http://www.reddit.com/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D277&title=WordPress+add_options_page" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/reddit.png" width="48px" height="48px" alt="Reddit" title="Reddit" /></a></li><li><a href="http://www.stumbleupon.com/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D277&title=WordPress+add_options_page" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/stumble.png" width="48px" height="48px" alt="StumbleUpon" title="StumbleUpon" /></a></li><li><a href="http://twitter.com/home?status=Currently Reading http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D277"  target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/twitter.png" width="48px" height="48px" alt="Twitter" title="Twitter" /></a></li></ul>'
st_cached_time:
  - "1291440549"
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
        $capability &#8212; Put a specific variable here from the <a href="http://codex.wordpress.org/Roles_and_Capabilities">Roles and Capabilities</a> list; manage_options is a sensible choice.
      </li>
      <li>
        $menu_slug &#8212;
      </li>
      <li>
        $function &#8212; The string you put here must be the name of the function that will run when when this plugin&#8217;s admin page is selected.
      </li></ul>