---
id: 254
title: Form Validation Client and Server Sides
date: 2010-09-18T19:05:28+00:00
author: seancamden
layout: revision
guid: http://www.seancamden.com/2010/09/18/253-revision/
permalink: /?p=254
---
I recently used [Cedric Dugas&#8217;s jQuery form validator](http://www.position-absolute.com/articles/jquery-form-validator-because-form-validation-is-a-mess/) on a few form pages for a client. I also used the technique described by Jeff Cogswell at O&#8217;Reilly&#8217;s OnLamp to handle validation on the server side with PHP. This way, folks with JavaScript on will see the fancy jQuery validation, and those running without will still still have to enter valid data. 

I put the validation code and the MySQL query in a separate file. It looks like this:
  
<?php
if (($_POST['process'] == 1) &#038;&#038; (isset($_POST['no_js']))) {
  if ($_POST['firstName'] == "") {
    $firstNameMessage = "<span class=\"smaller errortext\">Please enter your first name.</span>&#8220;;


    
}
    
if ($_POST[&#8216;lastName&#8217;] == &#8220;&#8221;) {
      
$lastNameMessage = &#8220;<span class=\"smaller errortext\">Please enter your last name.</span>&#8220;;
    
}
    
if ($_POST[&#8216;companyName&#8217;] == &#8220;&#8221;) {
      
$companyNameMessage = &#8220;<span class=\"smaller errortext\">Please enter your company name.</span>&#8220;;
    
}
    
if ($_POST[&#8216;phoneNumber&#8217;] == &#8220;&#8221;) {
      
$phoneNumberMessage = &#8220;<span class=\"smaller errortext\">Please enter your phone number.</span>&#8220;;
    
}
    
if ($_POST[&#8217;emailAddress&#8217;] == &#8220;&#8221;) {
      
$emailAddressMessage = &#8220;<span class=\"smaller errortext\">Please enter your email address.</span>&#8220;;
    
}
    
$emailpattern = &#8220;/^[a-zA-Z0-9_\.\-]+\@([a-zA-Z0-9\-]+\.)+[a-zA-Z0-9]{2,4}$/&#8221;;
    
$emailValid = preg\_match($emailpattern, $\_POST[&#8217;emailAddress&#8217;]);
    
$emailValidMessage = &#8220;<span class=\"smaller errortext\">Please enter a valid email address.</span>&#8220;;
    
$phonepattern = &#8220;/^[0-9\-\(\)\ ]+$/&#8221;;
    
$phoneValid = preg\_match($phonepattern, $\_POST[&#8216;phoneNumber&#8217;]);
    
$phoneValidMessage = &#8220;<span class=\"smaller errortext\">Please enter a valid phone number.</span>&#8220;;
    
if ((!(isset($firstNameMessage))) &#038;&#038;
        
(!(isset($lastNameMessage))) &#038;&#038;
        
(!(isset($companyNameMessage))) &#038;&#038;
        
(!(isset($phoneNumberMessage))) &#038;&#038;
        
(!(isset($emailAddressMessage))) &#038;&#038;
        
($phoneValid == 1) &#038;&#038;
        
($emailValid == 1)
       
) {
      
$errormessage = 1;
      
include &#8216;dbParams.php&#8217;;
      
header(&#8220;location: success/index.html&#8221;);
    
}
  
} elseif ($_POST[&#8216;process&#8217;] == 1) {
      
include &#8216;dbParams.php&#8217;;
      
header(&#8220;location: success/index.html&#8221;);
  
}
  
?>