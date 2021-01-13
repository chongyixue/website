# To install hugo on your Ubuntu machine

```bash
% sudo apt-get install golang-go
% wget https://github.com/gohugoio/hugo/releases/download/v0.27.1/hugo_0.27.1_Linux-64bit.deb
% sudo dpkg -i hugo_0.27.1_Linux-64bit.deb
```
Note you can also find other releases of hugo on:

```bash
https://github.com/gohugoio/hugo/releases/
```

# These are the steps to download this website and build it on Ubuntu machine

```bash
% git clone https://github.com/chongyixue/website.git
% cd website
% git submodule update --init
% git clone https://github.com/chongyixue/chongyixue.github.io.git public
```

Now you can make your chnages in the website/contents folder and run the 
following commands to view your website locally

```bash
% cd website
% hugo server -w # This will show the demo of webiste but will not build it
```
 
Go to your browser and type http://localhost:1313/ in the URL and you should 
be able to view your website.

# To make changes to your website and publish them

```bash
% hugo # This actually builds the webiste
% cd public
% git add .
% git commit -a -m "XYZ"
% git push  
```
This will push your repository to chongyixue.github.io and the changes in your
website will be available publicly.

# To commit the changes to your website folder that you use to build website

```bash
% cd website
% git add .
% git commit -a -m "ABC"
% git push
```

This will push the changes to website repo so that you can clone your hugo
project on any machine.

NOTE: Use % git status to check the changes you made in that repo

# Structure of the website folder

```
website
  |
  --- config.toml : This defines layout of your website.
  |
  --- content : This has info that is displayed on your website
  |      |
  |      --- home : This has a .md file for each section in your website e.g. posts, publication etc. 
  |      |          You don't put any content here. 
  |      |
  |      --- personal : Leave this empty
  |      |
  |      --- post : Don't touch _index.md. Just create a folder for a new tutorial. Copy index.md from
  |      |          another existing tutorial folder and modify it. e.g. if you want a tutorial on 
  |      |          Excel VBA, create a folder post/excel-vba and copy post/mahjong-tutorial/index.md
  |      |          into this folder and modify it accordingly.
  |      |
  |      --- publication : Don't touch index.md. Just copy existing file for a paper e.g. 
  |                        publication/nature.md to publication/new_paper.md and modify it. You can also
  |                        put the pdf of your paper here.
  | 
  --- static : Useless folder. Except the static/img folder has your profile picture.
  |
  --- themes : This has the theme. You just leave it alone.
  |
  --- public : When you build your website this folder will have all your html, css files. 
               Leave this folder alone as well.     
```
