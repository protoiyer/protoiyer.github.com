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

About an year back, I had [posted in depth](http://protoiyer.posterous.com/setting-up-my-linux-box-and-ruby-on-rails-dev) about my love for Ruby, and how I set up my Linux box on Ubuntu 10.10, including how to set up Ruby on Rails in that environment. 

Well the time has come for an update for [Ubuntu](http://www.ubuntu.com/) [12.04 LTS](http://releases.ubuntu.com/precise/) that came out during the last week of April.

Since I had written that previous post in such detail, I will just jot down the steps in this one. This is more for my reference, but may be it will be of use to someone as well. Also, that post came in quite handy during the current setup and so I hope I would refer back to this one as well in future.

I was on Ubuntu 10.10, whose [support came to an end ](http://goo.gl/fIfI3) during April and I was looking forward to the final release version of 12.04 ever since.

Now, there were only two ways to upgrade -- from 10.10 to 11.04, then to 11.10, and finally to 12.04. Or, take backups, take a deep breath, and wipe your disk clean and install 12.04. I chose the later path since the former sounded a terrible idea. Also, interestingly had I been on 10.10 (another LTS version), I could have directly upgraded to 12.04 (which is again an LTS version). So, a good lesson learned there -- I will think twice before upgrading to non-LTS versions from here on.

So, here I had a blank machine one more time, and this time too I decided to jot down the things I had to do to get the machine to a state that I would be happy about. I am a bit finicky about things like colors and fonts. 

Compared to the 10.10 days, there are some changes - some of the apps now come pre-installed (Firefox 12.0) or is no longer supported on Linux (Picasa)

So, once the OS is installed, here are the things I did:


Basic Machine Set Up
=================
 
A. Installing my favorite fonts

  [Inconsolata](http://kevin.vanzonneveld.net/techblog/article/install_the_best_coding_font/)
    sudo apt-get install ttf-inconsolata
 
  [Inconsolata-dz](http://goo.gl/Hhbxg), an even better looking Inconsolata

  [Inconsolata-g](http://goo.gl/R54Mp), another derivative of Inconsolata though I prefer the dz version more.

  Droid family of fonts, designed by Google for Android phones
    sudo apt-get install ttf-droid
 

B. Configure gEdit
 
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

 
C. Configure Nautilus

  View
    Default view Compact
    Arrange Items by Modification Date
    Zoom 50%
    ... 
 

D. Configure Terminal

  General
    "Inconsolata 11" as font
    Color: White on black  
 

E. Install [Chrome Dev Channel](http://www.chromium.org/getting-involved/dev-channel)
  
  Thankfully Chrome remembers all my settings and plugins and so this was pretty hassle free. The only setting I remembered doing was to set the font to Droid.

  Of course, Chrome doesn't remember any userscripts that you installed, and so I had to reinsall the following userscripts:

  [Google Reader - Even More Compact Design (Nov 2011)](http://userscripts.org/scripts/show/116888)
  [O'Reilly Safari Minimalist Tweaked](http://userscripts.org/scripts/show/76653)
  [Resurrect Google Cache & Related links](http://userscripts.org/scripts/show/114455)
  [Google Plus Right Side Bar Remover](http://userscripts.org/scripts/show/106671)
 

F. Install aptitude

  This would come in handy to install stuff that needs aptitude rather than the default apt-get package manager.
    sudo apt-get install aptitude
 
 
G. Install Pinta (equivalent of Paint.net)

  I am someone who takes a number of screenshots in a month for various things, and so not having the equivalent of Paint is not acceptable. I usually crop the screenshots and so I need a decent, basic editor. Enter [Pinta](http://www.ubuntugeek.com/pinta-paint-net-clone-for-linux.html#more-4476)
    sudo add-apt-repository ppa:moonlight-team/pinta
    sudo apt-get update
    sudo aptitude install pinta
 
 
H. Configure Reliance NetConnect

  Unfortunately, my Reliance Netconnect just doesn't work with the out-of-the-box method (of adding a new mobile network connection), and what works is the steps outlined by Harbhag at his blog: [Reliance Netconnect Broadband+ on Ubuntu](http://goo.gl/0mxqM)

 
O. Further tips and tricks to customize Ubuntu

  Refer [any](http://goo.gl/IFCX3) [of](http://goo.gl/kevrX) [these](http://goo.gl/WF111) [awesome](http://goo.gl/0ujkA) resources or google for more.
 

 
Developer tools and other tools Setup
=================
 
A. Install LAMP via instructions at [Installing LAMP on Ubuntu 12.04 Precise Pangolin](http://goo.gl/nfzPH) Like last time, I stopped short of installing phpAdmin which is mentioned at the end.
 
  
B. Install vim

  I have become a big fan of both terminal vim over the last year, and this time decided to compile and install vim with ruby support. I followed the [steps outlined in this post](http://goo.gl/ELSa4), including installing mercurial to clone the vim source code. Of course I used Ruby 1.9.3 on Ubuntu 12.04, but other than that the steps outlined in that post works. Of course, I still can't get Command-T to work on my box, and that is something I will have to check one of these days.

  I ended up installing version 7.3.509, which was the latest version available while I was installing.

  For Vim plugin management, this time I decided to do away with my manual style, and was almost going to use the highly rated [Pathogen](https://github.com/tpope/vim-pathogen) plugin. But googling revelaed an even simpler (dare I say better) way of doing that using [Vundle](https://github.com/gmarik/vundle).

  For more on Vundle, do read [these](http://goo.gl/8honf) [two](http://goo.gl/lwDkf) posts. I assure you it is worth your time!
 

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 
  Note: From here on, the installation process was done based on a bunch of resources:
 
  1. [Installing RoR in Ubuntu](http://arunsark.wordpress.com/2011/02/25/installing-ror-in-ubuntu/) by my good friend and colleague, [Arun Vydianathan](http://twitter.com/arunsark)
 
  2. The excellent and free [Ruby on Rails Tutorial book](http://ruby.railstutorial.org/ruby-on-rails-tutorial-book#sec:up_and_running)

  3. Of course my previous post :)
  
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 
 
C. Install git

  sudo apt-get install git-core
 
 
D. Set up tab completion for git
 
  I had backed up the file "contrib/completion/git-completion.bash" and so this was pretty painless - I just had to copy the file into my home (~) folder. 
    $ cd folder/having/git-completion.bash
    $ cp contrib/completion/git-completion.bash ~
    
    # Open the .bashrc file for editing
    $ gvim ~/.bashrc 
   
    # NOW, Paste the contents from [this Rails tutorial page](http://ruby.railstutorial.org/bashrc) into the file.
    
    # NEXT, run the following to source the bashrc file.
    $ . ~/.bashrc

  If you don't have that file, you might have to download the latest git source. Please refer my previous installation post for more on this.

  
E. Install curl

  sudo apt-get install curl
  
 
F. Install Ruby Version Manager (RVM)

  Refer the [RVM installation page](https://rvm.beginrescueend.com/rvm/install/) and follow along.
 
 
G. Install Ruby

  rvm install 1.9.3 
 
  Create the required [rvm gemsets](https://rvm.io/gemsets/) as per your requirement.

 
H. Install the latest version of Rails

  gem install rails
 
  If you run into the strange bundle-install-fails-on-every-gem issue due to handshake problem (Gem::RemoteFetcher::FetchError), please refer either of these [two](http://goo.gl/oW0ev) [posts](http://goo.gl/PGcJF) for a solution.
  
  To complete the set up of Rails development environment along with the required test setup and deployment (using heroku) environment, refer to the excellent [Ruby on Rails Tutorial](http://ruby.railstutorial.org/), chapters 1 and 3. Chapter 2 is about using scaffold to create a sample app, and doesn't add any value towards our current goal: setting up the environments.
 

I. Install the databases

  If you had followed along from the top (referring to the different sources, you would have already installed both mysql and sqlite3). If you haven't, please refer the "Databases" step of [this post](http://appogee.posterous.com/ubuntu-1010-ruby-on-rails-setup).
 
  For me, what is left to do is to install postgresql
 
  # Install postgresql and deps
    sudo apt-get install postgresql libpq-dev
    gem install pg 

  Of course, you would then have to then try to log into the postgresql db server, create the required users/roles etc. Google if you don't how to do it.
 
 
J. Install "Open Terminal [Command-Prompt] Here"

  This allows you to open a terminal from any path in the file manager Nautilus, and for me it is an indispensable tool. From [this SuperUser thread](http://superuser.com/questions/166407/how-to-open-a-menu-with-open-terminal-here-in-ubuntu-10-04-by-left-clicking-des):
  sudo apt-get install nautilus-open-terminal
 

K. Install tmux

  [Tmux](http://tmux.sourceforge.net/) is a terminal multiplexer and ensures that every time I open it I have all the windows I need (multiple terminals, rails server, rails console, rails db server and so on) are up and running.

  Here are [some](http://goo.gl/Mr8tD) [references](http://goo.gl/OFjS0) [and a book](http://goo.gl/2lirZ) that would be useful to get started.

  Of course, to make it even more easier, I use the [Tmuxinator gem](https://github.com/aziz/tmuxinator):
    gem install tmuxinator


L. Install the indicator-weather applet

  sudo apt-get install indicator-weather


M. Install Ack, which is of course better than grep

  sudo apt-get install ack-grep


N. Install Kazam for recoring videos for screencasts.

  sudo add-apt-repository ppa:kazam-team/stable-series
  sudo apt-get install kazam


O. Install xsane for the scanner

  sudo apt-get install xsane


P. Install VLC player

  sudo apt-get install vlc vlc-plugin-pulse


Q. Install lo-menubar to make LibreOffice play nicely with Unity

  sudo apt-get install lo-menubar


R. Install Nautilus Image converter to have a quick option to resize images from Nautilus

  sudo apt-get install nautilus-image-converter


S. Install xclip to use the clipboard from the commandline

  sudo apt-get install xclip


T. Install ImageMagick

  sudo apt-get install libqt4-dev
  sudo apt-get install libmagick libmagickcore-dev
  sudo apt-get install libmagickwand-dev


U. Install Exuberant Ctags (for Vim)

  sudo apt-get install exuberant-ctags


V. Install MyUnity to tweak Ubuntu.

  sudo apt-get install myunity

  The best part for me is that I can easily tweak the unity launcher bar from this.


W. Install Ubuntu Tweak to tweak Ubuntu.

  Can be downloaded from [http://ubuntu-tweak.com/](http://ubuntu-tweak.com/)


X. Install Compiz Config Settings Manager

  sudo apt-get install compizconfig-settings-manager

  This allows me to continue to use the Super(Windows key)+N combination to invert the monitor colors - an indispensable tool for reading using the browser.


=================

  Of course, my ideas about what constitutes my preferred configuration is bound to change over time, and so would the tools required to do the job. If I come across something great, I will try to update this post with that info.
 
Thanks for reading and I hope at least some of it would have been useful for you.
