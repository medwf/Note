# Requirements and install
- `php` : install it with `pacman -S php` 
	- `zend engine`: compiler and runtime environment
- composer:
``` bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'dac665fdc30fdd8ec78b38b9800061b4150413ff2e3b6f88543c636f7cd84f6db9189d43a81e5503cda447da73c7e5b6') { echo 'Installer verified'.PHP_EOL; } else { echo 'Installer corrupt'.PHP_EOL; unlink('composer-setup.php'); exit(1); }"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```

- get cakePhp v5 using composer.
``` bash
php composer.phar create-project --prefer-dist cakephp/app:5 cms
taping: y
```

# Conventions
## database conventions
- `tables` names corresponding to CakePHP models are plural and underscored.
	- `users`, `menu_links`, `user_favorite_pages`.
- `columns` names with two or more words are underscored.
	- `first_name`.
- `Foreign Keys` in **hasMany**, **belongsTo/hasOne** relationships are recognized by default as the **(singular)** name of the related table followed by `_id`
	- for: `users`  write: `user_id`.
	- deleted `s` and add `_id`.
-  `join` tables are used in **BelongsToMany** relationships between models. These should be named for the tables they connect. The names should be **pluralized** and **sorted alphabetically**
	- `articles_tags` not  `tags_articles` or `article_tags`.
# Creating database
## database configuration
``` php
// config/app_local.php
return [
    // More configuration above.
    'Datasources' => [
        'default' => [
		      // craete or define existing user and database.
		      // set it here.  
            'host' => 'localhost',
            'username' => 'cakephp',
            'password' => 'AngelF00dC4k3~',
            'database' => 'cake_cms',
            'url' => env('DATABASE_URL', null),
        ],
    ],
    // More configuration below.
];
```

## execute tables using script sql
- `cat file.sql | mariadb -u user_name -p `
## Migrations
- The SQL statements to create the tables for this tutorial can also be generated using the Migrations Plugin. Migrations provide a platform-independent way to run queries so the subtle differences between MySQL, PostgreSQL, SQLite, etc. don’t become obstacles

``` BASH
bin/cake bake migration CreateUsers email:string password:string created modified
bin/cake bake migration CreateArticles user_id:integer title:string slug:string[191]:unique body:text published:boolean created modified
bin/cake bake migration CreateTags title:string[191]:unique created modified
bin/cake bake migration CreateArticlesTags article_id:integer:primary tag_id:integer:primary created modified
```
- `bake migration` 
	- `<name class migration>` : generate change methods to migrate.
- `migrations migrate` : migrate all change. 
# Generating `baking our backend`
- `bake` generate baking our back-end.
	- `bin/cake bake all` : showing  all existing tables.
	- `bin/cake bake all <NameOfTable>` : generating back-end specific table.
		- generate `templates`, `tests`, `Models/Tables`, `controller` ... 
		- access to template for back-end with lowercase of name table

- `cache`  clear all cache CachePHP to regenerate new schema 
	- `bin/cake cache clear_all `.

# Config
## Routes
- `config/routers.php`
- default view showing.
``` php
$builder->connect('/', [
	'controller' => 'Pages', // pages folder 
	'action' => 'display',  // display method on PagesController.
	'home'   // home.php file in Pages folder
]);
```
# Controller

# Model
## has-Many and Belongs-to
- users has many article
- and article belong to user
``` php
// user table
$this->hasMany('Articles', [
	'foreignKey' => 'user_id',
]);

// article table
$this->belongsTo('Users', [
	'foreignKey' => 'user_id',
	'joinType' => 'INNER',
]);
```

## BolongToMany
``` php
// in articleTable
$this->belongsToMany('Tags', [
	'foreignKey' => 'article_id',
	'targetForeignKey' => 'tag_id',
	'joinTable' => 'articles_tags',
]);

// in tagTable
$this->belongsToMany('Articles', [
	'foreignKey' => 'tag_id',
	'targetForeignKey' => 'article_id',
	'joinTable' => 'articles_tags',
]);
```
# Templates
## Element
- void duplicated code in views
- in directory : `templates/element`
- `element(_string $elementPath_, _array $data_, _array $options = []_)`
	- `$elementPath_` : path start from `templates/element`
	- `$data_`: array of passing argument
	- `$options`

- `example` : create new file call `user-form.php`  has code view 
- And u can call it with :
```PHP

<?php echo $this->element('user-form', [
	'legend' => 'Add User'
]); 
 ?>
```
- [for more](https://book.cakephp.org/5/en/views.html#elements)


# Association

## default layout html/PHP
- `templates/layout/default.php` : default views show
- `tempaltes/layout/error.php` : error view exceptions show.
	- to a void that set in `config/app_local.php` `'DEBUG' => false`
- `tempaltes/Error` : specific view showing depends on HTTP error code.

## default pages
- `tempales/Pages` : pages folder for pages routes
	- `home.php` : default page showing.
# errors i found
## error  require ext-intl *
``` markdown
$ php composer.phar create-project --prefer-dist cakephp/app:5 cms

Creating a "cakephp/app:5" project at "./cms"  
Installing cakephp/app (5.0.0)

- Installing cakephp/app (5.0.0): Extracting archive  
    Created project in /home/medwf/cms  
    Loading composer repositories with package information  
    Updating dependencies  
    Your requirements could not be resolved to an installable set of packages.
    

Problem 1  
- Root composer.json requires cakephp/cakephp ^5.0.0 -> satisfiable by cakephp/cakephp[5.0.0, ..., 5.2.3].  
- cakephp/cakephp[5.0.0, ..., 5.2.3] require ext-intl * -> it is missing from your system. Install or enable PHP's intl extension.

To enable extensions, verify that they are enabled in your .ini files:  
- /etc/php/php.ini  
You can also run `php --ini` in a terminal to see which files are used by PHP in CLI mode.  
Alternatively, you can run Composer with `--ignore-platform-req=ext-intl` to temporarily ignore these required extensions.

--- solution:
The error you're seeing is because the **CakePHP 5** framework requires the PHP **`intl` extension**, which is missing from your system. This is a common issue when setting up PHP projects that rely on internationalization features.

$ pacman -S intl
$ sudo vim /etc/php/php.ini
add or modify this line `extension=intl`
```

## Error Database driver
``` markdown
Database driver `Cake\Database\Driver\Mysql` cannot be used due to a missing PHP extension or unmet dependency. Requested by connection `default`

==> solution
add or modify this lines

`
extension=mysqli
extension=pdo_mysql
`
```

``` markdown
Database driver `Cake\Database\Driver\Sqlite` cannot be used due to a missing PHP extension or unmet dependency. Requested by connection `test`

install : `sudo pacman -S php-sqlite`
add: 
`
extension=pdo_sqlite
`
```