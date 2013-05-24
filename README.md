# Question2Answer Open Login #

## About ##

This is a plugin for **Question2Answer** that allows users to log in via Facebook, Google, Yahoo, Github and other OAuth/OpenID providers. 


## Description ##
This is an extension of the Facebook Login plugin, to which it adds additional providers. It is based on [HybridAuth](http://hybridauth.sourceforge.net/) library which acts as a middleware between the plugin and a wide range of OAuth and OpenID service providers. For this reason, it is possible to add any login provider supported by HybridAuth to your Q2A installation with virtually no effort.

The plugin also offers the ability to link multiple OpenID/OAuth-powered logins to a Q2A user account, allowing users to log in to the same account via multiple providers. For example, an user might link his or her Facebook and Google accounts to the Q2A user account and then log in to the Q2A site through any of the 3 methods (Q2A login page, Facebook OAuth or Google OpenID).


## Installation ##

* Install [Question2Answer][]
* Get the source code for this plugin from [Github][], either using [Git][], or downloading directly:

   - To download using git, install git and then type 
     `git clone git://github.com/alixandru/q2a-open-login.git open-login`
   - To download directly, go to the [project page][Github] and click **Download**

* Go to **Admin -> Plugins** on your Q2A installation and enable the providers which you would like to use. For all OAuth-based providers (all, except Google and Yahoo, which use OpenID) you need to provide some keys after you register your application with them. See [HybridAuth documentation](http://hybridauth.sourceforge.net/userguide.html) for information about what is needed for each provider.
* Optionally add the contents of the *qa-open-login.css* file to your theme's CSS file and select the option **Don't inline CSS** from the **Open Login Configuration** section on the **Admin -> Plugins** page.

Note: this plugin requires some database changes: a column called `oemail` (original email) will be added to the tables `qa_users` and `qa_user_logins`. These columns will store the email associated with the OpenID/OAuth accounts when the users first logs in through any OpenID/OAuth provider. These emails will then be used to determine if there are accounts which can be linked together.

  [Question2Answer]: http://www.question2answer.org/install.php
  [Git]: http://git-scm.com/
  [Github]: https://github.com/alixandru/q2a-open-login



## Adding new login providers ##

Since this plugin is based on [HybridAuth](http://hybridauth.sourceforge.net/), you can easily add new login providers to your Q2A site. All you need to do is to add the provider PHP file to the `Hybrid/Providers` folder and configure it from the Administration page. That's it! 



## Translation ##

The translation file is **qa-open-lang-default.php**.  Copy this file to the same directory and change the **"default"** part of the filename to your language code. Edit the right-hand side strings in this file, for example, changing:

**`'my_logins_title'=>'My logins',`**

to

**`'my_logins_title'=>'Mes comptes',`**

Don't edit the string on the left-hand side. Once you've completed the translation, don't forget to set the site language in the admin control panel. Translations for Romanian are also included.  



## Change log ##

**v2.0.0**

* Rewrite the plugin to use HybridAuth 2.1.2
* Add the ability to specify what login providers to appear in the page header


**v1.1.0**

* Add the ability to keep users connected when they log in through an external provider
* Fix issues with logging users out


**v1.0.0**

* Initial release which supports logging in through Facebook, Google, Yahoo and Github.



## Disclaimer ##
This code has not been extensively tested on high-traffic installations of Q2A. You should perform your own tests before using this plugin on a live (production) environment. 


## License ##
This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 2 of the License, or (at your option) any later version.


## About Q2A ##
Question2Answer is a free and open source platform for Q&A sites. For more information, visit [http://www.question2answer.org/](http://www.question2answer.org/)
