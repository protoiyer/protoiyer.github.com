---
layout: post
title: "Setting up my Linux box and Ruby on Rails - Ubuntu 12.04 edition"
date: 2012-05-02 22:12
comments: true
author: protoiyer
categories: 
- ruby
- rails
- ruby on rails
- ubuntu
- tweak
- tips
---

Introduction
------------

About an year back, I had [posted in depth](http://protoiyer.posterous.com/setting-up-my-linux-box-and-ruby-on-rails-dev) about my love for Ruby, and how I set up my Linux box on Ubuntu 10.10, including how to set up Ruby on Rails in that environment. 

Well the time has come for an update for [Ubuntu](http://www.ubuntu.com/) [12.04 LTS](http://releases.ubuntu.com/precise/) that came out during the last week of April.

Since I had written that [previous post](http://protoiyer.posterous.com/setting-up-my-linux-box-and-ruby-on-rails-dev) in such detail, I will just jot down the steps in this one. This is more for my reference, but may be it will be of use to someone as well. Also, that post came in quite handy during the current setup and so I hope I would refer back to this one as well in future.

I was on Ubuntu 10.10, whose [support came to an end ](http://goo.gl/fIfI3) during April and I was looking forward to the final release version of 12.04 ever since.

Now, there were only two ways to upgrade -- from 10.10 to 11.04, then to 11.10, and finally to 12.04. Or, take backups, take a deep breath, and wipe your disk clean and install 12.04. I chose the later path since the former sounded a terrible idea. Also, interestingly had I been on 10.10 (another LTS version), I could have directly upgraded to 12.04 (which is again an LTS version). So, a good lesson learned there -- I will think twice before upgrading to non-LTS versions from here on.

So, here I had a blank machine one more time, and this time too I decided to jot down the things I had to do to get the machine to a state that I would be happy about. I am a bit finicky about things like colors and fonts. 

Compared to the 10.10 days, there are some changes - some of the apps now come pre-installed (Firefox 12.0) or is no longer supported on Linux (Picasa)

So, once the OS is installed, here are the things I did:


Basic Machine Set Up
--------------------
 
##### A. Installing my favorite fonts

[Inconsolata](http://kevin.vanzonneveld.net/techblog/article/install_the_best_coding_font/)
```  
  sudo apt-get install ttf-inconsolata
```  

[Inconsolata-dz](http://goo.gl/Hhbxg), an even better looking Inconsolata

[Inconsolata-g](http://goo.gl/R54Mp), another derivative of Inconsolata though I prefer the dz version more.

Droid family of fonts, designed by Google for Android phones
```  
  sudo apt-get install ttf-droid
```

[Meslo](http://goo.gl/ttbDt) 

Another brilliant monospace font that has caught my attention off late is [Meslo](http://goo.gl/ttbDt) (based on the Menlo font that the latest versions of Mac use), created by Andre Berg. The beauty of these fonts (and of course of the original Mac Monaco) is that they are very legible at small font sizes. Also, it is more compact (width-wise) at the same point size compared to say, Inconsolata. I use Meslo Medium at 9 points these days. You can download it from the [Meslo github page](https://github.com/andreberg/Meslo-Font/downloads). I haven't changed the references in this post from Inconsolata to Meslo, however.
 

##### B. Configure gEdit
 
```  
enable
  View
    Display line numbers
  Editor
    Tab Stops
      Tab width: 2
      Insert spaces instead of tabs
    Automatic indentation
      Enable automatic indentation
  Font
    Remove "Use the system fixed width font"
    select "Inconsolata 11" as font
  Color Scheme
    Oblivion
  ... # and so on 
```  

 
##### C. Configure Nautilus

```  
View
  Default view List
  Arrange Items by Modification Date
  Zoom 50%
  ... 
```  


##### D. Configure Terminal

```  
General tab
"Inconsolata 11" as font
Color: White on black  
```  
 

##### E. Install [Chrome Dev Channel](http://www.chromium.org/getting-involved/dev-channel)
  
  Thankfully Chrome remembers all my settings and plugins and so this was pretty hassle free. The only setting I remembered doing was to set the font to Droid.

  Of course, Chrome doesn't remember any userscripts that you installed, and so I had to reinsall the following userscripts:

[Google Reader - Even More Compact Design (Nov 2011)](http://userscripts.org/scripts/show/116888)   
[O'Reilly Safari Minimalist Tweaked](http://userscripts.org/scripts/show/76653)   
[Resurrect Google Cache & Related links](http://userscripts.org/scripts/show/114455)   
[Google Plus Right Side Bar Remover](http://userscripts.org/scripts/show/106671)
 

##### F. Install aptitude

  This would come in handy to install stuff that needs aptitude rather than the default apt-get package manager.

```  
sudo apt-get install aptitude
```  
 
##### G. Install Pinta (equivalent of Paint.net)

  I am someone who takes a number of screenshots in a month for various things, and so not having the equivalent of Paint.net is not acceptable. I usually crop the screenshots and so I need a decent, basic editor. Enter [Pinta](http://www.ubuntugeek.com/pinta-paint-net-clone-for-linux.html#more-4476)

```  
sudo add-apt-repository ppa:pinta-maintainers/pinta-stable
sudo apt-get update
sudo aptitude install pinta
```  

 
##### H. Configure Reliance NetConnect

  Unfortunately, my Reliance Netconnect just doesn't work with the out-of-the-box method (of adding a new mobile network connection), and what works is the steps outlined by Harbhag at his blog: [Reliance Netconnect Broadband+ on Ubuntu](http://goo.gl/0mxqM)

 
##### I. Further tips and tricks to customize Ubuntu

  Refer [any](http://goo.gl/IFCX3) [of](http://goo.gl/kevrX) [these](http://goo.gl/WF111) [awesome](http://goo.gl/0ujkA) resources or google for more.
 
 
##### J. Install "Open Terminal [Command-Prompt] Here"

  This allows you to open a terminal from any path in the file manager Nautilus, and for me it is an indispensable tool. From [this SuperUser thread](http://superuser.com/questions/166407/how-to-open-a-menu-with-open-terminal-here-in-ubuntu-10-04-by-left-clicking-des):

```  
sudo apt-get install nautilus-open-terminal
```  
 

##### K. Install tmux

  [Tmux](http://tmux.sourceforge.net/) is a terminal multiplexer and ensures that every time I open it I have all the windows I need (multiple terminals, rails server, rails console, rails db server and so on) are up and running.

  Here are [some](http://goo.gl/Mr8tD) [references](http://goo.gl/OFjS0) [and a book](http://goo.gl/2lirZ) that would be useful to get started.

```  
sudo apt-get install tmux
```  

  Since the apt-get repository had an old version, I downloaded and compiled the source. But the above should get you started.

  Of course, to make it even more easier, I use the [Tmuxinator gem](https://github.com/aziz/tmuxinator) as well:

```  
gem install tmuxinator
```  


##### L. Install the indicator-weather applet

```  
sudo apt-get install indicator-weather
```  


##### M. Install Ack, which is of course better than grep

```  
sudo apt-get install ack-grep
```  


##### N. Install Kazam for recoring videos for screencasts.

```  
sudo add-apt-repository ppa:kazam-team/stable-series
sudo apt-get install kazam
```  


##### O. Install xsane for the scanner

```  
sudo apt-get install xsane
```  


##### P. Install VLC player

```  
sudo apt-get install vlc vlc-plugin-pulse
```  


##### Q. Install lo-menubar to make LibreOffice play nicely with Unity

```  
sudo apt-get install lo-menubar
```  


##### R. Install Nautilus Image converter to have a quick option to resize images from Nautilus

```  
sudo apt-get install nautilus-image-converter
```  


##### S. Install xclip to use the clipboard from the commandline

```  
sudo apt-get install xclip
```  


##### T. Install ImageMagick

```  
sudo apt-get install libqt4-dev
sudo apt-get install imagemagick libmagickcore-dev
sudo apt-get install libmagickwand-dev
```  


##### U. Install Exuberant Ctags (for Vim)

```  
sudo apt-get install exuberant-ctags
```  


##### V. Install MyUnity to tweak Ubuntu.

```  
sudo apt-get install myunity
```  

  The best part for me is that I can easily tweak the unity launcher bar from this.


##### W. Install Ubuntu Tweak to tweak Ubuntu.

  Can be downloaded from [http://ubuntu-tweak.com/](http://ubuntu-tweak.com/)


##### X. Install Compiz Config Settings Manager

```  
sudo apt-get install compizconfig-settings-manager
```  

  This allows me to continue to use the Super(Windows key)+N combination to invert the monitor colors - an indispensable tool for reading using the browser.


##### Y. Install AmbianceOneiric theme

  I prefer the all dark provided by AmbianceOneiric theme compared to light+dark menus of the default theme.

  Download from the [github repo](https://github.com/StanAngeloff/AmbianceOneiric).


##### Z. Change the keyboard shortcut to open the HUD.

  I find the default mapping of the [left] Alt key to open the [HUD](http://youtu.be/w_WW-DHqR3c) highly irritating, as whenever I press Alt+tab or Alt+LeftArrow (in the browser to go to the previous page), the system would promptly open the HUD. I have to press Escape to close it and get the focus back on whatever window I wanted to access.

  Go to System settings | Keyboard | Shortcuts tab. The entry "Key to show the HUD" should have the shortcut listed as "Alt L". Click that row and press the right Alt key to get the row to display the new keyboard shortcut as "Alt R". Peace of mind guaranteed. Of course, I do use HUD a lot, including to shut down the device, but I prefer to pay the extra penalty of clicking the right Alt key to invoke it.


##### AA. Remap Caps Lock to act as Control key

  I wasn't aware till recently that the editors like emacs make heavy use of the hard to reach Control key for virutally every shortcut not because it was designed by people who didn't care, but because before the advent of x86 hardware, all keyboards had the Caps and Control keys swapped. Which means their decision (taken before the x86 days) to use the Control key makes a lot of sense. Luckily it is [pretty easy to remap the Caps Lock](http://www.emacswiki.org/emacs/MovingTheCtrlKey) to act as the Control key. Though it will take a little while for the change to sink in, after a week or so it would be pretty difficult to live without it!


 
Developer tools Setup
=================
 
##### A. Install LAMP   

Install following instructions at [Installing LAMP on Ubuntu 12.04 Precise Pangolin](http://goo.gl/nfzPH). Like last time, I stopped short of installing the phpAdmin software that is mentioned at the end of that post.
 
  
##### B. Install vim

  I have become a big fan of terminal vim over the last year, and this time decided to compile and install vim with ruby support. I followed the [steps outlined in this post](http://goo.gl/ELSa4), including installing mercurial to clone the vim source code. Of course I used Ruby 1.9.3 on Ubuntu 12.04, but other than that the steps outlined in that post works. Of course, I still can't get Command-T to work on my box, and that is something I will have to check one of these days.

  I ended up installing version 7.3.509, which was the latest version available while I was installing.

  For Vim plugin management, this time I decided to do away with my manual style, and was almost going to use the highly rated [Pathogen](https://github.com/tpope/vim-pathogen) plugin. But googling revelaed an even simpler (dare I say better) way of doing that using [Vundle](https://github.com/gmarik/vundle).

  For more on Vundle, do read [these](http://goo.gl/8honf) [two](http://goo.gl/lwDkf) posts. I assure you it is worth your time!
 
  Of course, to install terminal vim using the package manager, use

```  
sudo apt-get install vim
```  

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 
  Note: From here on, the installation process was done based on a bunch of resources:
 
  [Installing RoR in Ubuntu](http://arunsark.wordpress.com/2011/02/25/installing-ror-in-ubuntu/) by my good friend and colleague, [Arun Vydianathan](http://twitter.com/arunsark)  
  The excellent and free [Ruby on Rails Tutorial book](http://ruby.railstutorial.org/ruby-on-rails-tutorial-book#sec:up_and_running)   
  Of course my [previous post](http://protoiyer.posterous.com/setting-up-my-linux-box-and-ruby-on-rails-dev) :)
  
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 
 
##### C. Install git

```  
sudo apt-get install git-core
```  
 
 
##### D. Set up tab completion for git
 
  I had backed up the file "contrib/completion/git-completion.bash" and so this was pretty painless - I just had to copy the file into my home (~) folder. 

```  
$ cd folder/having/git-completion.bash
$ cp contrib/completion/git-completion.bash ~

# Open the .bashrc file for editing
$ gvim ~/.bashrc 

# NOW, Paste the contents from [this Rails tutorial page](http://ruby.railstutorial.org/bashrc) into the file.

# NEXT, run the following to source the bashrc file.
$ . ~/.bashrc
```  

  If you don't have that file, you might have to download the latest git source. Please refer my previous installation post for more on this.

  
##### E. Install curl

```  
sudo apt-get install curl
```  
  
 
##### F. Install Ruby Version Manager (RVM)

  Refer the [RVM installation page](https://rvm.beginrescueend.com/rvm/install/) and follow along.
 
 
##### G. Install Ruby

```  
rvm install 1.9.3 
```  
 
  Create the required [rvm gemsets](https://rvm.io/gemsets/) as per your requirement.

 
##### H. Install the latest version of Rails

```  
gem install rails
```  
 
  If you run into the strange bundle-install-fails-on-every-gem issue due to handshake problem (Gem::RemoteFetcher::FetchError), please refer either of these [two](http://goo.gl/oW0ev) [posts](http://goo.gl/PGcJF) for a solution.
  
  To complete the set up of Rails development environment along with the required test setup and deployment (using heroku) environment, refer to the excellent [Ruby on Rails Tutorial](http://ruby.railstutorial.org/), chapters 1 and 3. Chapter 2 is about using scaffold to create a sample app, and doesn't add any value towards our current goal: setting up the environments.
 


##### I. Install the databases

  If you had followed along from the top (referring to the different sources, you would have already installed both mysql and sqlite3). If you haven't, please refer the "Databases" step of [this post](http://appogee.posterous.com/ubuntu-1010-ruby-on-rails-setup).
 
  For me, what is left to do is to install postgresql
 
```  
# Install postgresql and deps
sudo apt-get install postgresql libpq-dev
gem install pg 
```  

  Of course, you would then have to then try to log into the postgresql db server, create the required users/roles etc. Refer [this post](http://xtremekforever.blogspot.in/2011/05/setup-rails-project-with-postgresql-on.html) to install and set up postgresql.


##### J. Install node

  Since the package repository is not kept upto date, it is always better to install node from the source on a Ubuntu box. Refer the excellent gist: [install node and npm without having to sudo](https://gist.github.com/579814) for instructions. I prefer [cloning the git repo](http://goo.gl/HWYTZ) method, and one can safely ignore line numbers 15-18 that is for installing npm. This is so since npm is bundled along with node that we installed following line numbers 1-14 of that gist.


Conclusion
----------

  My ideas about what constitutes preferred configuration is bound to change over time, and so would the tools required to do the job. If I come across something great, I will try to update this post with that info.
 
  Thanks for reading and I hope at least some of it would have been useful for you.   


Revision History
----------------

<a name="update1" />Update# 1</a> - Thu, 03-May-12: Cleaned up the code snippets' layout.  

<a name="update2" />Update# 2</a> - Mon, 21-May-12: Changed the pinta ppa to point to the correct one, changed reference to the package libmagick to imagemagick, moved items K-Z to the more appropriate top section, added info about AmbianceOneiric theme and changing the HUD keyboard shortcut, added reference to Meslo and mapping the Caps Lock to act as the Control key. Added a note about installing node.js.   
