
## ❓ How to use this template

1. Click on **Use this template** button when you're on the repo main page.
![image](https://user-images.githubusercontent.com/62112531/174029013-c5c46b36-e107-47f1-ab1e-d15e9904db28.png)


## 🔨 How to install

### Server requirements

- [**PHP**](http://php.net/) >= 7.2
- [**Apache**](https://wordpress.org/) >= 2.4
- [**MySQL**](https://downloads.mysql.com/archives/installer/) >= 5.7 _(not 8.x)_ or [**MariaDB**](https://mariadb.org/) >= 10.3

<details>
 <summary> 
  
 ### 👉 If it's a new website _(click to expand)_
  
 </summary>
 
 1. **Clone this project repository** in your local website folder  
 _(create a local website environment first if you haven't done it yet)_  
 _(example with laragon: `C:/laragon/www/my-project` for https://my-project.test)_

 2. **Download [Pilo'Press Installer](https://github.com/Pilot-in/PiloPress-Installer)** using the method of your choice & **follow [Pilo'Press Installer README steps](https://github.com/Pilot-in/PiloPress-Installer#installation-steps)**.
 </details>
 <details>
 
 <summary>
  
 ### 👉 If it's an existing website / TMA _(click to expand)_

 </summary>

 1. **Clone this project repository** in your local website folder  
 _(create a local website environment first if you haven't done it yet)_  
 _(example with laragon: `C:/laragon/www/my-project` for https://my-project.test)_

 2. Copy `wp-config-sample.php` file & paste it as `wp-config.php` file & change DB related values with your local config:  
 `DB_NAME` _(usually the name of your project)_  
 `DB_USER` _(usually `root`)_  
 `DB_PASSWORD` _(usually `root` or empty)_  
 `DB_HOST` _(usually `localhost`)_  

 3. Go to https://api.wordpress.org/secret-key/1.1/salt/ & copy the generated code & replace it with what is already into your `wp-config.php` file _(`AUTH_KEY`...)_.

 2. Use a **database tool** _(PHPMyAdmin, Adminer...)_ to import the database dump _(named `db.sql.gz` in the folder)_ into the MySQL database  
 _(example with laragon: in database `my-project` for https://my-project.test)_

 3. Edit `site_url` & `home_url` values in `wp_options` table with the url you're using in your local server / virtual host  
 _(example with laragon: https://my-project.test for **"My Project"** website)_

 4. **Login into the WordPress admin** using `/connect-in` slug _(or with `/wp-login.php` if it doesn't work)_  
 _(example with laragon: https://my-project.test/connect-in for **"My Project"** website)_  
 Admin access should be available in Dashlane, if it's not the case, ask the lead dev on slack to share it with you

 5. In the WordPress admin, go to **Settings > Permalinks** _(Réglages > Permaliens)_
 6. then go to **Plugins > Add new** _(Extensions > Ajouter)_ & install **WP Migrate Lite** plugin
 7. Finally in **Tools > WP Migrate** _(Outils > WP Migrate)_, click on "**New Migration**" button then "**Find & Replace**" button  

 8. In **"Custom Find & Replace"**:  
 In the **left field**: add **prod url** with a slash _(example: `/www.my-project.com`)_  
 In the **right field**: add **local url** with a slash _(example: `/my-project.test`)_

 9. Click on "**Preview changes**" button to see if there are some matches, if that's the case, you're good to click on "**Find & Replace**" button!

</details>

### Pilo'Press
- You have to recompîle Pilo'Press style when you just synced the project on your computer. To do so, go to the WordPress back-office & click on **"Pilo'Press > Styles > Update & compile"**

## 🔍 How to set automatic code review

1. Go to "**Settings**" on the repository _(the new one, **not Pilo-Project-Template repository**)_, then click on "**Secrets > Actions**".
2. Click on "**New repository secret**"
3. Set `GH_BOT_TOKEN` as name & `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` as value, then click on "**Add secret**".
4. **Create a new branch** with **your name** _(ex: `Damien`)_
5. Then create a **new pull request of this branch** with your name and what you're going to do on this project _(example: **TMA: Damien**)_.
6. When you will commit / push code to this branch, **Pilo'Bot** will give you good practices as comments & review your code.
7. Be sure to have installed / use **[PilotIn-Coding-Standards](https://github.com/Pilot-in/PilotIn-Coding-Standards)** in your IDE _(PHPStorm, VSCode...)_ to code with the correct lint & developments functions / good practices.
