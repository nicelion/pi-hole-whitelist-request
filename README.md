# pi-hole-whitelist-request

By simply adding one line, found in index.php and right below, the users on your pi-hole network can easily request blocked web pages to be whitelisted, by sending an email to the pi-hole admin.

```php 
<p>To request this site be unblocked, <a href="mailto:webmaster@internet.com?Subject=Whitelist%20Request:%20<?php echo $serverName.$uri;?>&Body=<?php echo $serverName.$uri; ?>%0D%0A%0D%0A%0D%0AGenerated%20<?php echo date('D g:i A, M d'); ?>%20by%20Pi-hole%20<?php echo $piHoleVersion; ?>" target="_top">click here.</a> to send an email to the administrator.</p>

```

You'll need to edit ```index.php``` by running ``` vim /var/www/html/pihole/index.php```.

Add the line whereever you'd like, just before the closing html tag. See ```example.php``` for my placement and how I added it in. 

Then, once you save, when a user attempts to access a blocked website, the block page will look like this:


I should mention, I don't know if this will break your pi-hole install. I don't think it will, but who knows. I am not a professional, and know absolutly nothing about PHP. So please use at your discretion. 
