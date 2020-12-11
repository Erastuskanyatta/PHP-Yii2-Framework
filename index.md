## Getting started with Yii 2 PHP Web framework.
 
Nowadays,many people have turned to using frameworks in designing web apps. This has led to improved production speeds. PHP is a general-purpose scripting language especially used in web development. It is a server side scripting language that is embedded in [HTML](https://en.wikipedia.org/wiki/HTML). It is used in managing dynamic content, databases and session tracking.
It can be integrated with databases like MySQL, PostgreSQL and Mongodb.

## Introduction
Yii 2 is a generic web programming framework used for developing web applications with multiple ties. It can be used together with a database. 
Like other PHP frameworks,Yii implements the MVC (Model, View and Controller).

MVC aims to separate business logic from user interface considerations, so that developers can more easily change each part without affecting the other. To learn more on MVC click [here](https://www.guru99.com/php-mvc-frameworks.html).

## Prerequisites
To follow along with this tutorial,you are required to have the following: 
- a code editor like [Visual Studio Code](https://code.visualstudio.com/download)
- knowledge of HTML and CSS
- Apache web server. You can get it [here](https://www.apachefriends.org/download.html).

## step 1 -- install yii2
Yii 2 can be installed from an archive file.

This Involves three steps;

1.Download the archive file from [yiiframeworks.com](https://www.yiiframework.com/download).

2.Unpack the download file to a web-accessible folder. 

3.Modify the config/web.php file by entering a secret key for the cookieValidationkey configuration item.


```php
// !!! insert a secret key in the following(if it is empty) - this is required by cookie validation
'cookieValidationKey' =>'secret',
```
```bash
sudo apt install php-gd

sudo service apache2 restart
```
Then test your web app using the in-built web server by running the following command in a terminal: 
```bash
$ php yii serve
```
You can also learn how to configure your web server [here](https://www.php.net/manual/en/features.commandline.webserver.php).
<!-- At this point, you are ready to start using the Yii framework for development. 
 After your done with the installation,you can configure your web server or use the build in server [bult-in-web server](https://www.php.net/manual/en/features.commandline.webserver.php) by running the following command in your terminal while in the project directory . -->
 

### Understanding the Folder Structure and directories
Inside the `advanced` folder,we have the following folder structure:
```bash
.
├── backend
├── codeception.yml
├── common
├── composer.json
├── composer.lock
├── console
├── docker-compose.yml
├── environments
├── frontend
├── init
├── init.bat
├── LICENSE.md
├── README.md
├── requirements.php
├── vagrant
├── Vagrantfile
├── vendor
└── yii.bat
```
In this `advanced` folder, we have three main directories:
1. backend
2. console
3. frontend

Let us look at the work of the above folders:
### Folder 1. backend
In web application, we consider two things, the user facing side of the website and the admin panel which is the backend part. The backend directory serves the admin services which are restricted from the users.
Inside this `backend` folder, we have the following main directories.
![backend](3.png)
### assets
This directory consists of assets configurations. By default, it has an `AppAsset.php` file, which includes the configurations of the javascript and the css files. This is where we will be adding our CSS and JavaScript files.
### controllers
Yii 2 contollers are written in this folder. Yii 2 follows the convention of <NameController> for naming the controllers. Example, `UserController.php` is the name of the file containing `User` controllers.

### models
Models are the classes which contain the 'business logic'. When we say business logic it's the processing of data, manipulating the values, etc. In Yii, this directory also has classes which are a link to the Database through which we can access the database tables. These models and tables have one to one mapping.
### views
Views store the files that are displayed via a browser. The data to be placed is passed from the controler in the view and then sent to the browser as HTML. 

Inside views we have two directories:
### 1. layout

Layouts are a special type of views that represent the common parts of multiple views. For example, the pages for most Web applications share the same page header and footer. 
Instead of repeating the same page header and the footer in every view,a better way is to do this layout embed the rendering result of a content view at an appropriate place in the layout. The files in this directory are under `main.php` folder.

### 2. Site

Unlike files in layout,files in site are not fixed.That is,one page does not have the same view with another page.The only similar thing is the header and the footer since it was placed in `main.php`.

### 3. common
In this directory we have configurations which used in the backend and the frontend projects. For example, you can have database configuration in common/config if, both of them uses the same database.

### Folder 2: frontend

The `frontend` project provides the main interfaces to users.The user only interacts with the frontend. This folder has similar directories to those of `backend`. 

## step 3  accessing the installed Yii application using a browser
Use your browser to access the installed Yii application. Open your browser and navigate, http://localhost/advanced
You should first see the following directory;
```bash
Index of /test
[ICO]	Name	Last modified	Size	Description
[PARENTDIR]	Parent Directory 	 	- 	 
[ ]	LICENSE.md 	2020-08-07 23:30 	1.5K	 
[ ]	Vagrantfile 	2020-08-07 23:30 	2.6K	 
[DIR]	backend/ 	2020-08-07 23:30 	- 	 
[ ]	codeception.yml 	2020-08-07 23:30 	167 	 
[DIR]	common/ 	2020-08-07 23:30 	- 	 
[ ]	composer.json 	2020-08-07 23:30 	1.4K	 
[ ]	composer.lock 	2020-08-07 23:31 	169K	 
[DIR]	console/ 	2020-08-07 23:30 	- 	 
[ ]	docker-compose.yml 	2020-08-07 23:30 	864 	 
[DIR]	environments/ 	2020-08-07 23:30 	- 	 
[DIR]	frontend/ 	2020-08-07 23:30 	- 	 
[ ]	init 	2020-08-07 23:30 	8.6K	 
[ ]	init.bat 	2020-08-07 23:30 	319 	 
[ ]	requirements.php 	2020-08-07 23:30 	5.7K	 
[DIR]	vagrant/ 	2020-08-07 23:30 	- 	 
[DIR]	vendor/ 	2020-08-07 23:31 	- 	 
[ ]	yii 	2020-11-22 22:36 	717 	 
[ ]	yii.bat 	2020-08-07 23:30 	323 	 
[ ]	yii_test 	2020-11-22 22:36 	928 	 
[ ]	yii_test.bat 	2020-11-22 22:36 	328 	 
```
Inside frontend directory click the web directory and if the installation was successful you should  see the below "Congratulations!" page in your browser. 

![A congratulatory note](congratulations.png)


## Congratulation for creating your first Yii program.
If you don't get a congratulation note,just go back a little and follow the steps. 

## Step 4 Creating our first web application using yii 
Now that we have yii installed and working in our pc lets create our first yii frontend project. We will start by creating the navigation bar and the footer. In our `view` directory we will open `main.php` under layout file and  enter the following:
```php
      ---
      <body>
<?php $this->beginBody() ?>

<div class="wrap">
    <li><a href="<?= Yii::$app->urlManager->createUrl(['site/contact'])?>">Contact</a></li>
    <?php
    NavBar::begin([
        'brandLabel' => Yii::$app->name,
        'brandUrl' => Yii::$app->homeUrl,
        'options' => [
            'class' => 'navbar-inverse navbar-fixed-top',
        ],
    ]);
    $menuItems = [

      
        ['label' => 'Home', 'url' => ['/site/index']],
        ['label' => 'About', 'url' => ['/site/about']],
        ['label' => 'Contact', 'url' => ['/site/contact']],
    ];
    if (Yii::$app->user->isGuest) {
        $menuItems[] = ['label' => 'Signup', 'url' => ['/site/signup']];
        $menuItems[] = ['label' => 'Login', 'url' => ['/site/login']];
    } else {
        $menuItems[] = '<li>'
            . Html::beginForm(['/site/logout'], 'post')
            . Html::submitButton(
                'Logout (' . Yii::$app->user->identity->username . ')',
                ['class' => 'btn btn-link logout']
            )
            . Html::endForm()
            . '</li>';
    }
    echo Nav::widget([
        'options' => ['class' => 'navbar-nav navbar-right'],
        'items' => $menuItems,
    ]);
    NavBar::end();
    ?>

    <div class="container">
        <?= Breadcrumbs::widget([
            'links' => isset($this->params['breadcrumbs']) ? $this->params['breadcrumbs'] : [],
        ]) ?>
        <?= Alert::widget() ?>
        <?= $content ?>
    </div>
</div>


<footer class="footer">
    <div class="container">
        <div class="col-md-4">
            <div>
            Contact Us though; <br>
            0734568543 <br>
            0723435678
                
            </div>
        </div>
         <div class="col-md-4">
        <div class="w3l-title">
       <h3  class="panel-title" >About Me</h3>
        </div>
        <div class="panel-body">
         <p>Get to know me</p> <br>
         <div class="social-icons">
         <i class="fa-linkedin">U have a question for me?</i> <br>
         <a href="<?= Yii::$app->urlManager->createUrl(['site/contact'])?>">Contact</a> <br>
         <i class="fa-linkedin">My address</i> <br>
         <p>PO.BOX 292 xxxx <br> PO.BOX 345-10100 xxx</p>
         </div>
         </div>  
        </div>
          <div class="col-md-4">
         <h3 class=panel-title>My social media link</h3> <br>
         <i class=""></i>
         <a href="https://en-gb.facebook.com/">  Facebook </a><br>
         <a href="https://www.instagram.com/">Instagram </a><br>
         <a href="https://twitter.com/home?lang=en">Twitter  </a><br>
         <a href="https://www.google.com/">  Google </a><br>
         <a href="https://web.whatsapp.com/">Whatsapp </a><br>
      </div>
        <br> <br>
        <div class="col-md-12">
            <div class="footer-copyright text-center py-3">© 2020 Copyright:
              <a href="https://mdbtrap.com/"> MDBootstrap.com</a>
            </div>

        </div>

    </div>

  
</footer>
<?php $this->endBody() ?>
</body>
      ---
```
In the above code we have used PHP URL manager to route.

You should add all the CSS and JavaScript files in the assets directory as shown below: 
```css
{
    public $basePath = '@webroot';
    public $baseUrl = '@web';
    public $css = [
        'css/site.css',
        'css/bootstrap.min.css',
        'css/styles.css',
    ];
    public $js = [
 
```
In our case all the style are in css folder and that how we will be linking  them.

## Body
Now lets modify the body.This will be done inside the `index.php` file which is in the site directory. This file contains the entire page of the website..
When we modify the index.php file we will have the code below.We will also add a link that will take us to service page that we are going to create.
```php
<?php

<?php

/* @var $this yii\web\View */

$this->title = 'My Yii Application';
?>
<div class="site-index">

    <div class="jumbotron">

       <h1>Hello World!</h1>
        <p>My first webpage using yii2.</p>
         <h2>Click here <a href="<?= Yii::$app->urlManager->createUrl(['site/portfolio'])?>">Portfolio </a>to go to the portfolio page. </h2>
    
</div>

```
Now lets create a view page called portfolio page.To create a page, we
must create a view and  an action.
Inside views/site folder create a file called portfolio.php.To do this,right click on site to create a new file(portfolio.php) with the following code:
```html
<!DOCTYPE html>
<html>
<head>
	<title>Portfolio</title>
</head>
<body>
     <h1 style="text-align: center">This is the portfolio page that we have created.</h1>
     <div class="container">
     	<div class="col-sm-4">
     		<div class="title">
     			<h6>About Me</h6>
     		</div>
     		<div>Iam a student.</div>
     	</div>
     	<div class="col-sm-4">
     		<div class="title">
     			<h6>My contact</h6>
     		</div>
     		<div>xxxxxxxx.</div>
     	</div>
     	<div class="col-sm-4">
     		<div class="title">
     			<h6>Services</h6>
     		</div>
     		<div>I write articles at an affordable price.</div>
     	</div>
     </div>
     
</body>
</html>
```
Now that we have created a view,lets create an action.

Actions are the objects that end users can directly refer to for execution. Actions are grouped by controllers. The execution result of an action is the response that an end user will receive.

Declare the portfolio action in the existing SiteController, which is defined in the class file
controllers/SiteController.php.
```php
<?php
namespace frontend\controllers;

use frontend\models\ResendVerificationEmailForm;
use frontend\models\VerifyEmailForm;
use Yii;
use yii\base\InvalidArgumentException;
use yii\web\BadRequestHttpException;
use yii\web\Controller;
use yii\filters\VerbFilter;
use yii\filters\AccessControl;
use common\models\LoginForm;
use frontend\models\PasswordResetRequestForm;
use frontend\models\ResetPasswordForm;
use frontend\models\SignupForm;
use frontend\models\ContactForm;

/**
     * Display portfolio  page
     * 
     * @return mixed
     */
    public function actionPortfolio()
     {
         $this->layout='main';
         return $this->render('portfolio');

    }
    // ...
```
After creating the action and the view, you may access the new page by clicking on the portfolio link that is on the main page and your browser should display an image similar to the one below;
![hello world](2.png)

In Yii, all action methods are prefixed with the word action. This is how the framework differentiates action methods from non-action ones. If an action ID requires multiple words, then they will be concatenated by
dashes.

To add any other page in yii follow the same same steps above and you will be done.

### Is framework important when codding?
This one depends on you as an individual,some people  will prefer framework while others won't.However,I would recommend someone to use framework especially the beginners since;
1. it is easy to install
2. encourages testing
3. utilizes modern technology


### conclusion
Like any other good framework,Yii help you create modern web application quickly and make sure they perform well.It pushes you to create securable and testable site by doing a lot of the heavy lifting for you.
I really encourage you to check it out for the next web project..
In this article;
- we have installed yii2 framework.
- we have looked at yii2 directories.
- we have created a portfolio page using yii2.

Have You tried yii2??Why not?Try today!