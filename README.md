#Phing-Deploy

Deploy your project easily to any server using phing tasks.

## Requirements

* You are able to access your server passwordless via ssh
* You can either copy files to the server using ssh or rsync (tunneled through ssh)
* You have a machine where you can use phing, composer and bower. **This is not necessary on the live server**

## Installation

    $> composer require --save --dev org_heigl/phingdeploy
    $> composer install
    $> phing phingdeploy.install

## Usage

On any machine you are able to login into your live server via passwordless ssh
(using certificate based login) you can use ```phing phingdeploy``` to deploy to your
live server. This will do the following:

* call ```composer install```
* call ```bower install```
* copy all the files in your current directory to a dedicated deployment-directory
  excluding the ```.git```, ```doc``` and ```tests```-folders
* either copy or sync the content of this deployment-folder to the live server.
  Therefore unneccessary files will not be synced to the server.


## Configuration

For all configuration-parameters have a look into the file [```config/build.properties.dist```](config/build.properties.dist).
You might want to copy that file into your top-folder, rename it to ```build.properties```
and adapt it to your needs. You can simply remove (or comment out) lines you do not wish to overwrite.
