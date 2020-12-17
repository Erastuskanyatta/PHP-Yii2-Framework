
## Working with Yii 2 PHP framework.
 
Nowadays, many developers have turned to use frameworks in designing websites. This has led to improved production speeds. PHP is a server-side scripting language  embedded in [HTML](https://en.wikipedia.org/wiki/HTML). 

## Introduction
Yii 2 is a generic PHP framework used for developing web applications with many ties. Yii 2 implements the MVC (Model, View, and Controller) development principle.

Model, View, and Controller help web developers work with a single part of the website at a time. To learn more on MVC click [here](https://www.guru99.com/php-mvc-frameworks.html).

## Prerequisites
To follow along with this tutorial, you need to have the following:
- a code editor like [Visual Studio Code](https://code.visualstudio.com/download)
- knowledge of PHP, HTML, and CSS
- Apache Web server. Download it [here](https://www.apachefriends.org/download.html). After installation, a folder `/opt/lampp` will be created.

## step 1 -- install Yii 2


Yii 2 can be installed from an archive file.

This involves the following steps"

1. Downloading the archive file from [yiiframeworks.com](https://www.yiiframework.com/download). Download the advanced application template.

2. Move the  archive file to the `/htdocs` inside where Xampp was installed . In my case it is `/opt/lampp/htdocs`.

```bash
$ sudo mv yii-advanced-app-2.0.39.tgz /opt/xampp/htdocs
```
3. Using the terminal open the  `/opt/xampp/htdocs` and unzip the Yii-2-advanced file.
```bash
$ sudo tar-xvzf Yii-advanced-app-2.0.39.tgz
```
Click [here](https://askubuntu.com/questions/499807/how-to-unzip-tgz-file-using-the-terminal) if you encounter any problem. 

4. Initialize your project by entering the following command.
```
$ PHP init
```
To initialize your application, you should select 0 (Development environment).

At this point, you have installed  Yii 2 Advanced Template. Open your browser and navigate, http://localhost/advanced/frontend/web to test it.

If you see the Congratulations! page in your browser, it means that the installation was successful.

![A congratulatory note](congratulations.png)


### step 2--understanding the Folder Structure and directories
Below are the folders inside the `advanced`. Open `/opt/lampp/htdocs/advanced` folder using your favorite code editor to see them.

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
2. common
3. frontend

Let us look at the work of the above folders:
### Folder 1. backend
The backend directory serves the admin services which are restricted from the users.
Inside this `backend` folder, we have the following main directories.


**`/assets`**: This directory consists of asset configurations. It has an `AppAsset.php` file, which contains the configurations of the CSS and the JAVASCRIPT. This is where we will be adding our CSS and JAVASCRIPT files.


**`/controllers`**: Yii 2 Controller is written in this folder. Yii 2 takes the convention of <NameController> to name the controllers. 


**`/models`**: In Yii 2, processing of data, and manipulating the values takes place here. In this directory, we have classes that link to the databases. Tables in databases and the models have one to one mapping.


**`/views`**: In Yii 2, the views directory is used to store files that will be displayed in the browser as HTML. The code placed in this directory is always in PHP format but displayed in the browser in HTML format.

Inside view we have two directories:

- **`views/layout`**: The layout directory contains the views that are fixed in the browser. These views get displayed on all pages of the website and their files are in `main.php`. For instance, the most website has footer and header files placed in this directory. So, all pages on that website contain a similar footer and header.

- **`views/site`**: Unlike files in layout, files in the site are not fixed. That is, one page does not have the same view as another page. The only similar thing is the header and the footer since they were placed in `main.php`.

### Folder 2: common
Here, we have files that are common to both backend and frontend directory. For instance, database configurations in `/common/config` takes place here.

### Folder 3: frontend

The `/frontend` project contains the contents displayed to the users. This folder has similar directories to those of `/backend`.

## Step 3--Creating our first web application using Yii 2

To create a web page, we need to change the different parts of our website to fit our preferences. Let us change the footer of our website. Replace the whole `<footer>` in `/frontend/views/layout/main.php` with the following code:

```PHP
// ...
<footer class="footer">
    <div class="container">
        <div class="col-md-6">
            <div>
           <h6>This is a footer</h6>
           <h5>Classic footer</h5>
            </div>
        </div>
        <div class="col-md-12">
            <div class="footer-copyright text-center py-3">© 2020 Copyright:
              <a href="https://mdbtrap.com/"> MDBootstrap.com</a>
            </div>

        </div>

    </div>

  
</footer>

//...

```
### Step 4 -- Configure CSS and JavaScript
All CSS files in a project are stored under `/web/CSS` and all JavaScript is stored under `/web/js`. 

Let us customize the footer we created above. Create a `footer.css` under `/web/css` and put the code below. 
```css
h6{
    color: red;
    text-align: center;
}
h5:hover{
    color: blue;
}
h5{
    color: violet;
}


```

Then register the styles above in `assets/AppAsset.php`.
```css
/* ... */
{
    public $basePath = '@webroot';
    public $baseUrl = '@web';
    public $css = [
        'css/site.css',
        'css/footer.css',
    ];
    /* ... */
}
```
### Modifying site contents
Now let us change the contents of our website. Replace the contents of `frontend/views/site/index.php` with the following code:

```PHP
<?PHP

/* @var $this yii\web\View */

$this->title = 'My Website';
?>
<div class="site-index">

    <div class="jumbotron">

       <h1>Hello World!</h1>
       <p>My first yii2 powered site.</p>
       <h2>Here is my <a href="<?= Yii::$app->urlManager->createUrl(['site/portfolio'])?>">Portfolio </a></h2>
    </div>
</div>
```
The code above replaces the default homepage content with bootstrap jumbotron. We also add a link that points to a portfolio page using the PHP URL manager. The URL Manager is used to link pages throughout Yii 2 framework. On clicking the link you get a 404 error as the portfolio page does not exist. Let us now create the portfolio page.

### Adding a new page to our website
To add a new page to our website, we need to create a view and an action. A view is the code that the user will see on the browser. Create a new file `frontend/views/site/portfolio.php` and put the following code:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Portfolio</title>
</head>
<body>
     <h1 style="text-align: center">This is the portfolio page</h1>
     <div class="container">
        <div class="col-sm-4">
            <div class="title">
                <h6>About Me</h6>
            </div>
            <div>I am a student.</div>
        </div>
     </div>
     
</body>
</html>
```
For the above view code to work, we need to create an action. We will put Actions in controllers. 


To display the portfolio page, we need to declare an action to display the portfolio page. Open  `frontend/controllers/SiteController.php` and add the following:
```PHP
<?PHP
// ...
class SiteController extends Controller
{
// ...

/**
     * Displays portfolio  page
     * 
     * @return mixed
     */
    public function actionPortfolio()
     {
         $this->layout='main';
         return $this->render('portfolio');

    }

}
```
After creating the action and the view, you can access the new page by clicking on "Portfolio" on the main page.

You should have a page like the one below;
![A congratulatory note](web.png)


### conclusion
Congratulations! Now you have a better understanding of the basics of the Yii 2 framework.
Yii 2 pushes you to create a securable and testable site by doing a lot of the heavy lifting for you.
I encourage you to use Yii 2 in your next project.
In this article;
- we have installed Yii 2 framework.
- we have looked at Yii 2 directories.
- we have created a portfolio page using yii2.

**Have a good Yii 2 coding ahead**
