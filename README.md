imagecompare.js
==========
This will compare the images from source and destination directory considering both will have same directory structure and file names. To use this project, you will need to have a set of image pairs to compare. Each pair of images should be named the same then it will check the source file with same name at relevant destination directory path and create result difference image in ./demo/output directory. If the destination directory don’t have the respective file present it will not return the difference image.

This project depends upon the resemblejs which does analyse and compare images with Javascript and HTML5. [More info & Resemble.js Demo](https://huddleeng.github.io/Resemble.js/). Compatible with Node.js.

![Two image diff examples side-by-side, one pink, one yellow.](https://raw.github.com/Huddle/Resemble.js/master/demoassets/readmeimage.jpg "Visual image comparison")


### Install node

It is recommended to install Node using Node Version Manager

https://github.com/creationix/nvm

*Example commands for installation on Ubuntu*

``` bash
##Install node.js##
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs

above steps are working correctely for ubuntu-14-04 but if you are facing any issue with ubuntu-16-04 for node installation please follow below link
https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-16-04

##Install nvm##
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
or Wget:
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash

The script clones the nvm repository to ~/.nvm and adds the source line to your profile (~/.bash_profile, ~/.zshrc, ~/.profile, or ~/.bashrc).

Note: If the environment variable $XDG_CONFIG_HOME is present, it will place the nvm files there.

export NVM_DIR="${XDG_CONFIG_HOME/:-$HOME/.}nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
Note: You can add --no-use to the end of the above script (...nvm.sh --no-use) to postpone using nvm until you manually use it.

if you are getting below error :
Error: /lib/x86_64-linux-gnu/libz.so.1: version `ZLIB_1.2.9' not found (required by /home

please follow below link
https://github.com/AllToMP3/alltomp3-app/issues/25#issuecomment-371582608

You can download zlib version 1.2.9 and uncompress it.

cd zlib-1.2.9
./configure
make
sudo make install

```

### Prepare reference and test image to compare

## Step 1 - clone the project and update config file for source and test images directory
```$ git clone https://github.com/hmrc/visual-regression-report```

```$ cd visual-regression-report```

update config file (settings.json) for sourceDirectoryPath and testDirectoryPath and both should be absolute path from root directory.

## Step 2 - Install node dependencies

```$ npm install --save```

## Step 3 - Run analysis 

```$ npm start```

## Step 3 - Generate Report 

```$ npm test```

report will be generated under ./results/report.html, with all required dependencies and supporting images. This command will open the report in default browser.

## Additional

To check the demo file comparison under .${project}/demo, please update the config file(settings.json) for sourceDirectoryPath and testDirectoryPath  and both should be absolute path from root directory.

If you are facing below issue then its related to memory, try to increase RAM or delete files:

Killed

npm ERR! code ELIFECYCLE

npm ERR! errno 137


We tested this tool with more than 500 images for compare and having 10GB memory allocated. It tooks less than 5 mins to generate the report.


