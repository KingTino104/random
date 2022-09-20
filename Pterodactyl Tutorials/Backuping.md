# Pterodactyl Backup

## Backing up panel

1. Backup your hidden `.env` file containing the decryption APP_KEY from `/var/www/pterodactyl`
<br>

2. Export the database, in this case ours is named **panel**

    ```mysql
    mysqldump -u root -p --opt panel > /var/www/pterodactyl/panel.sql
    ```

    The *.sql* file would be saved in the `/var/www/pterodactyl/` folder.
<br>

3. Follow the panel [installation documentation](https://pterodactyl.io/panel/1.0/getting_started.html) to install the panel on your new server.
<br>

4. Transfer the `panel.sql` file to your new server and import the database. Make sure you're in the folder containing your *.sql* dump when performing the commands.

    ```mysql
    mysql -u root -p panel < panel.sql
    ```

    <br>

5. After this, transfer your old `.env` file to the `/var/www/pterodactyl` location to complete the panel migration.

<br>

Original: [Click Here](https://gist.github.com/Software-Noob/c18258658bef28e73b24d11d02d24915)
