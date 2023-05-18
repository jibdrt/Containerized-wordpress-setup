# Containerized wordpress setup

## Install lando & docker

## Create a new folder
> mdkir "sitename"

## Navigate to the new folder
> cd "sitename"

## Create a Lando Yml file
> touch .lando.yml

## Define the basic configuration

>name: sitename<br>
>recipe: wordpress<br>
>config:<br>
>  webroot: .<br>

## Run the container

> lando start

## Download wordpress core

> lando wp core download

## Create a new theme

> cd wp-content/themes<br>
> mdkir "themename"<br>
> touch index.php functions.php front-page.php header.php footer.php page.php single.php style.css
 
 ## Create a gulpfile

 > touch gulpfile.js

 ## Define the build

 > See <a href="https://github.com/jibdrt/Containerized-wordpress-setup/blob/main/gulpfile.md">gulpfile.md</a>

 ## Install gulp and sass dependencies

 > npm install sass gulp gulp-sass gulp-concat gulp-uglify






