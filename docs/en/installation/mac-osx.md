# Mac OSX

This topic covers setting up your Mac as a Web Server and installing SilverStripe. 

While OSX Comes bundled with PHP and Apache (Thanks Apple!) Its not quite ideal for SilverStripe so for setting up a
webserver on OSX we suggest using [MAMP](http://www.mamp.info/en/index.php) or using [MacPorts](http://www.macports.org/) 
to manage your packages.

If you want to use the default OSX PHP version then you will need to recompile your own versions of PHP with GD. Providing instructions
for how to recompile PHP is beyond the scope of our documentation but try an online search.

## Installing MAMP

If you have decided to install using MacPorts you can skip this section.

Once you have downloaded and Installed MAMP start the Application and Make sure everything is running by clicking the
MAMP icon. Under `Preferences -> PHP` make sure Version 5 is Selected.

Open up `/Applications/MAMP/conf/PHP5/php.ini` and make the following configuration changes:

	memory_limit = 64M

Once you make that change open the MAMP App Again by clicking on the MAMP Icon and click Stop Servers then Start
Servers - this is so our changes to the php.ini take effect.

###Composer
Composer (PHP's package manager) is the prefered way to install SilverStripe and ensure you get the correct set of files for your project.

Composer uses your MAMP PHP executible to run and also requires Git (so it can automatically download the required files from GitHub).

Process to install is as follows:

1. Install [git for mac](http://git-scm.com/download/mac).</li>
2. Install composer using the instructions below
3. Run the following command to get a fresh copy of SilverStripe via composer:
  
      `composer create-project silverstripe/installer /Applications/MAMP/htdocs/silverstripe/`
 
4. You can now [use composer]() to manage future SilverStripe updates and adding modules with a few easy commands.
 

## Installing SilverStripe

###Composer
[Composer (a dependancy manager for PHP)](http://getcomposer.org) is the prefered way to install SilverStripe and ensure you get the correct set of files for your project.

Composer uses your MAMP PHP executible to run and also requires [git](http://git-scm.com) (so it can automatically download the required files from GitHub).

Process to install is as follows:
<ol>
<li>Install [git for mac](http://git-scm.com/download/mac).</li>
<li>Install composer using the following instructions:</li>
	<ol>
 	#### Installing Composer with MAMP's instlallation of PHP
 	<li>If you are using MAMP, we first create an alias for our bash profile. We'll be doing this in nano, though you can do it in vim or a number of other editors as well if you prefer.</li>
 	<li>Within the terminal, run:<br />
 	   `nano ~/.bash_profile`</li>
	<li>This will open nano with the contents, at the top in a blank line add the following line (adjusting the version number of PHP to your installation of MAMP):<br />
	   `alias phpmamp='/Applications/MAMP/bin/php/php5.4.10/bin/php'`</li>
	<li>This will create an alias, phpmamp, so that you can take advantage of the MAMP installation of PHP. Please take note of the PHP version, in this case 5.4.10, as with different versions of MAMP this may be different. Check your installation and see what version you have, and replace the number accordingly (this was written with MAMP version 2.1.2).</li>
	<li>With that setup, we are ready to install composer. This is a two step process if we would like this to be installed globally, while you would only need to do the first step if you would like this installed to the local working directory only.</li>
	<li>First, run the following command in the terminal:<br />
	   `curl -sS https://getcomposer.org/installer | phpmamp`<br />
	Note that instead of the standard 'php' at the end which calls the global installation of PHP, we are using 'phpmamp' so that we correctly use the MAMP installation of PHP.</li>

	<li>Next, we want to make composer available globally, so we need to move the file to '/usr/local/bin/composer'. To do this, run the following command:<br />
	`sudo mv composer.phar /usr/local/bin/composer`</li>

	<li>Terminal will ask you for yor password, after entering it and pressing the 'return' (or enter) key, you'll have a working global installation of composer on your mac that uses MAMP!</li>

	<li>You can verify your installation worked by typing the following command:<br />
	`composer`</li>
	<li>It'll show you the current version and a list of commands you can use!</li>
</ol>

#### Installing Composer with the global installation of PHP
<ol>
  <li>With that setup, we are ready to install composer. This is a two step process if we would like this to be installed globally, while you would only need to do the first step if you would like this installed to the local working directory only.</li>
  <li>First, run the following command in the terminal:<br />
	`curl -sS https://getcomposer.org/installer | php`</li>
  <li>Next, we want to make composer available globally, so we need to move the file to `/usr/local/bin/composer`. To do this, run the following command:<br />
`sudo mv composer.phar /usr/local/bin/composer`</li>
  <li>Terminal will ask you for yor password, after entering it and pressing the 'return' (or enter) key, you'll have a working global installation of composer on your mac!</li>
  <li>You can verify your installation worked by typing the following command:<br />
`composer`</li>
  <li>It'll show you the current version and a list of commands you can use!</li>
</ol>


<li>Run the following command to get a fresh copy of SilverStripe via composer:
  
        `composer create-project silverstripe/installer /Applications/MAMP/htdocs/silverstripe/`</li>

<li>You can now [use composer](http://doc.silverstripe.org/framework/en/installation/composer) to manage future SilverStripe updates and adding modules with a few easy commands.</li>
</ol>

###Package Download

[Download](http://silverstripe.org/download) the latest SilverStripe installer package. Copy the tar.gz file to the 'Document Root' for MAMP - By Default its `/Applications/MAMP/htdocs`.
Don't know what your Document Root is? Open MAMP Click `Preferences -> Apache`. 

Extract the tar.gz file to a folder, e.g. `silverstripe/` (you always move the tar.gz file first and not the other way
around as SilverStripe uses a '.htaccess' file which is hidden from OSX so if you move SilverStripe the .htaccess file
won't come along.

###Run the installation wizard
Once you have a copy of the required code (by either of the above methods), open your web browser and go to `http://localhost:8888/silverstripe/`. Enter your database details - by default with MAMP its user `root` and password  `root` and select your account details. Click "Check Details".

Once everything is sorted hit "Install!" and Voila,  you have SilverStripe installed 
