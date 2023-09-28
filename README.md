![Deals-imagebanner](https://github.com/haidnav/Deals-disseration-project/blob/main/deals-image.png)

# Project Requirements
- [Node.js](https://nodejs.org/en)
- [PHP]((https://www.php.net/downloads.php))
- Laravel
- Composer: https://getcomposer.org/download/
**Please download these before continuing, laravel will automatically be installed when running composer**


# Setting Up a Laravel Project with XAMPP

This guide will walk you through the steps to set up a Laravel web application on your local machine using XAMPP. 

## Step 1: Install XAMPP

If you haven't already installed XAMPP, follow these instructions:

1. Download the latest version from the official website [here](https://www.apachefriends.org/).
2. Install XAMPP according to the instructions for your operating system.

## Step 2: Copy Laravel Files

1. Create a new folder within the "htdocs" directory of your XAMPP installation. The default paths are:
   - Windows: `C:\xampp\htdocs`
   - macOS: `/Applications/XAMPP/htdocs`
   - Linux: `/opt/lampp/htdocs`

2. Copy all your Laravel project files and folders into the newly created folder.

## Step 3: Database Setup

1. Open the XAMPP Control Panel and start both the Apache and MySQL services.

2. Access phpMyAdmin by going to [http://localhost/phpmyadmin/](http://localhost/phpmyadmin/) in your web browser.

3. Create a new database for your Laravel site by clicking on "New" and giving it a suitable name. (for example `deals_app`)
   
4. Import the attached SQL file into your newly created database within PHPMyAdmin

5. Locate the `.env` file in your Laravel project's root folder. If it's not there, look for `.env.example` and rename it to `.env`.

6. Open the `.env` file in a text editor and update the following lines with your database details:

   ```dotenv
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=your_database_name (this would be deals_app, as named above)
   DB_USERNAME=your_database_username
   DB_PASSWORD=your_database_password

Replace your_database_name, your_database_username, and your_database_password with your actual database credentials. DB_USERNAME is `root` by default and DB_PASSWORD should be left empty.


## Step 4: Install Composer Dependencies

1. Open your terminal or command prompt and navigate to the root of your Laravel project.

2. Run the following command to install the required dependencies:

```shell
composer install
```

If you encounter an error here, try:
```shell
composer upgrade
```
**You can download composer here:** https://getcomposer.org/download/
## Step 5: Generate Application Key

In your terminal or command prompt, still within your Laravel project's root directory, run the following command:
```shell
php artisan key:generate
```
This will generate a unique application key needed for encryption purposes.

## Step 6: Run Database Migrations
In the terminal or command prompt, run the following command to execute the database migrations:
```shell
php artisan migrate
```
This will create the necessary tables in your database based on your Laravel project's migration files.

## Step 7: Start the Server
1.	Make sure XAMPP's Apache and MySQL services are running.
2.	Navigate to your htdocs directory and your projects root folder. Run the following command:
```shell
php artisan serve
```
3.	Your terminal should output a link to access the application.
example:
```shell
(base) haidernaveed@Haiders-MBP deals % pwd
/Applications/XAMPP/xamppfiles/htdocs/deals
(base) haidernaveed@Haiders-MBP deals % php artisan serve
Starting Laravel development server: http://127.0.0.1:8000
[Fri Sep  8 07:08:05 2023] PHP 8.2.5 Development Server (http://127.0.0.1:8000) started
```


By following these steps you should now be up and running and can begin using the application in a local enivronment.

## Step 8: Start using the app in web environment

Now that the deals app is running in your local web environment, there are some things to do first to gain a better understanding.

1. Register as a user. This can be done by clicking log in, at the top right corner of the page. This should open a modal that has the log in form. Look for a link to `create account`, and register yourself as a new user.
2. Check PHPMyAdmin to see if you have been registered. You can find your newly created user in the `user` table.
3. Locate the row of your newly created user and click `edit`.
4. Change `role` from `user` to `admin`. Then click on `Go` at the bottom of the page.
5. Go back to the deals app. Alter the URL, it should be `/dashboard`, change this to `/logout`.
6. You should now be on the home page. Please log in again.
7. If done correctly you should now be seeing the admin dashboard. Here you can create categories and sub categories, as well as approve or decline deals posted by users.
8. Now that the admin account is set up. You can set up a regular user account by simply signing up. Then you can create deals to post, but ensure that you have created some categories first.
9. Once you have submitted a deal, you will need to go back into the admin account in order to accept the deal. Once accepted it can be viewed on the front end.











