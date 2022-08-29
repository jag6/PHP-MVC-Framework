# PHP-MVC-Framework
PHP MVC Framework with Example Model

<h2>Overview</h2>
This MVC Framework contains an example model, which is provided to give a base for how models can be built using this framework in PHP. 
<br><br>
The 'libraries' folder contains the heart of the MVC. 
<br><br>
<ul>
  <li>Controller.php - loads the models and views</li>
  <li>Core.php - creates the url and loads the core controller</li>
  <li>Database.php - connects to the database, creates prepared statements, binds values, and returns rows and results</li>
</ul>

The libraries are autoloaded by the 'bootstrap.php' file, which also loads the 'config.php' file. The 'config' folder's 'config.php' sets the database's params as well as the project's app root, url root, and sitename.

The 'models' folder contains all the models that will query your databases. They are called by the controllers in the 'controllers' folder. The model's content will be whatever you enter into it's respective database.

The 'public' folder contains the CSS, JavaScript, and Image folders.

The 'helpers' folder has been left empty as the alerts and other helpers content can be added later to fit your project's requirements.

<h2>Model Example</h2>
The example provided in this repository has the 'controllers/Pages.php' file be responsible for sending the database content located at 'models/Post.php' to the files stored in the 'views/pages' folder. In this example the database has been named 'posts', and is queried by the model named 'Post'.

<h3>Creating the Database and it's Content</h3>
The simplest way to create a database would be to do so using phpmyadmin. In order to query your database, you must go over to the 'config.php' file and change 'YOUR_DBNAME' to whatever database name you would like. Upon doing so, create this database name using phpmyadmin. Then create a table, filling the database with whatever content you would like. 
<br><br>
Just like the database name in the 'config.php' needs to be the same as the database name you've created in phpmyadmin, the model needs to query the same name as the one you've created as the table for the same database. In this example, the table name that has been created in phpmyadmin is 'posts' and we can see it being queried in 'Post.php'. 'Post' is the name of the model which is responsible for handling the table 'posts' content.

<h3>Calling the Model</h3>
To render the database content, you must go over to 'Pages.php' to have the model be constructed. You can see how this is being done in the file. Then you can decide which 'views' file the content should be sent to. In this example it is being sent to the index page.

<h3>Rendering the Model's Content</h3>
Lastly, the content needs to be called in the 'views' folder. In this example the 'posts' content is being mapped on the index page.

<h3>Content Flow Review</h3>
'Post' model at 'models/Post.php' queries table 'posts' from database 'YOUR_DBNAME' stored at phpmyadmin -> 'controllers/Pages.php' calls 'Post' model and sends it to 'pages/index.php' -> 'index.php' renders 'posts'

<h2>Items that Need Changing</h2>
As previously stated, the 'config.php' will need to have it's 'DB_NAME' replaced by one of your choosing. Note that anything else starting with 'YOUR' will also need to be replaced. 'DB_USER' has 'root' as a default, which may be changed if you would like.

The '.htaccess' file located in the 'public' folder will also need your attention. Here you will need to change the 'MVC' for 'Rewrite Base'. This will be whatever folder your project is stored in on your computer.
