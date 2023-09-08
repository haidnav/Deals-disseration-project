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

3. Create a new database for your Laravel site by clicking on "New" and giving it a suitable name.

4. Locate the `.env` file in your Laravel project's root folder. If it's not there, look for `.env.example` and rename it to `.env`.

5. Open the `.env` file in a text editor and update the following lines with your database details:

   ```dotenv
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=your_database_name
   DB_USERNAME=your_database_username
   DB_PASSWORD=your_database_password

Replace your_database_name, your_database_username, and your_database_password with your actual database credentials.


## Step 4: Install Composer Dependencies

1. Open your terminal or command prompt and navigate to the root of your Laravel project.

2. Run the following command to install the required dependencies:

   ```shell
   composer install


## Step 5: Generate Application Key

In your terminal or command prompt, still within your Laravel project's root directory, run the following command:
 ```shell
   php artisan key:generate


