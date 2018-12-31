---
id: 253
title: Form Validation Client and Server Sides
date: 2010-09-18T19:07:06+00:00
author: seancamden
layout: post
guid: http://www.seancamden.com/?p=253
permalink: /?p=253
st_cached:
  - '<ul class="socialize-this"><li><a href="http://del.icio.us/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D253&title=Form+Validation+Client+and+Server+Sides" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/del.png" width="48px" height="48px" alt="Delicious" title="Delicious" /></a></li><li><a href="http://www.facebook.com/sharer.php?u=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D253&t=Form+Validation+Client+and+Server+Sides" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/facebook.png" width="48px" height="48px" alt="Facebook" title="Facebook" /></a></li><li><a href="http://digg.com/submit?phase=2&url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D253" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/digg.png" width="48px" height="48px" alt="Digg" title="Digg" /></a></li><li><a href="http://www.reddit.com/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D253&title=Form+Validation+Client+and+Server+Sides" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/reddit.png" width="48px" height="48px" alt="Reddit" title="Reddit" /></a></li><li><a href="http://www.stumbleupon.com/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D253&title=Form+Validation+Client+and+Server+Sides" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/stumble.png" width="48px" height="48px" alt="StumbleUpon" title="StumbleUpon" /></a></li><li><a href="http://twitter.com/home?status=Currently Reading http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D253"  target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/twitter.png" width="48px" height="48px" alt="Twitter" title="Twitter" /></a></li></ul>'
st_cached_time:
  - "1284861962"
---
I recently used [Cedric Dugas&#8217;s jQuery form validator](http://www.position-absolute.com/articles/jquery-form-validator-because-form-validation-is-a-mess/) on a few form pages for a client. I also used the technique described by Jeff Cogswell at O&#8217;Reilly&#8217;s OnLamp to handle validation on the server side with PHP. This way, folks with JavaScript on will see the fancy jQuery validation, and those running without will still still have to enter valid data. 

I put the validation code and the MySQL query in a separate file. It looks like this:
  
`<br />
<?php
if (($_POST['process'] == 1) &#038;&#038; (isset($_POST['no_js']))) {
  if ($_POST['firstName'] == "") {
    $firstNameMessage = "<span class=\"smaller errortext\">Please enter your first name.</span>";<br />
  }<br />
  if ($_POST['lastName'] == "") {<br />
    $lastNameMessage = "<span class=\"smaller errortext\">Please enter your last name.</span>";<br />
  }<br />
  if ($_POST['companyName'] == "") {<br />
    $companyNameMessage = "<span class=\"smaller errortext\">Please enter your company name.</span>";<br />
  }<br />
  if ($_POST['phoneNumber'] == "") {<br />
    $phoneNumberMessage = "<span class=\"smaller errortext\">Please enter your phone number.</span>";<br />
  }<br />
  if ($_POST['emailAddress'] == "") {<br />
    $emailAddressMessage = "<span class=\"smaller errortext\">Please enter your email address.</span>";<br />
  }<br />
  $emailpattern = "/^[a-zA-Z0-9_\.\-]+\@([a-zA-Z0-9\-]+\.)+[a-zA-Z0-9]{2,4}$/";<br />
  $emailValid = preg_match($emailpattern, $_POST['emailAddress']);<br />
  $emailValidMessage = "<span class=\"smaller errortext\">Please enter a valid email address.</span>";<br />
  $phonepattern = "/^[0-9\-\(\)\ ]+$/";<br />
  $phoneValid = preg_match($phonepattern, $_POST['phoneNumber']);<br />
  $phoneValidMessage = "<span class=\"smaller errortext\">Please enter a valid phone number.</span>";<br />
  if ((!(isset($firstNameMessage))) &&<br />
      (!(isset($lastNameMessage))) &&<br />
      (!(isset($companyNameMessage))) &&<br />
      (!(isset($phoneNumberMessage))) &&<br />
      (!(isset($emailAddressMessage))) &&<br />
      ($phoneValid == 1) &&<br />
      ($emailValid == 1)<br />
     ) {<br />
    $errormessage = 1;<br />
    include 'dbParams.php';<br />
    header("location: success/index.html");<br />
  }<br />
} elseif ($_POST['process'] == 1) {<br />
    include 'dbParams.php';<br />
    header("location: success/index.html");<br />
}<br />
?><br />
`