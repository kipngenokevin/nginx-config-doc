To add a new subdomain to your VPS using Nginx, follow these steps:

1. **Create a New Configuration File for the Subdomain:**

   Create a new Nginx configuration file for your subdomain. Typically, these files are located in `/etc/nginx/sites-available/`.

   ```sh
   sudo nano /etc/nginx/sites-available/safaricom-offers.gigastreammedia.net
   ```

2. **Add Server Block Configuration:**

   In the new configuration file, add the following server block configuration:

   ```nginx
   server {
       listen 80;
       server_name safaricom-offers.gigastreammedia.net;

       root /var/www/safaricom-offers.gigastreammedia.net;
       index index.html index.htm index.php;

       location / {
           try_files $uri $uri/ =404;
       }

       # Optional: Add PHP support
       location ~ \.php$ {
           include snippets/fastcgi-php.conf;
           fastcgi_pass unix:/var/run/php/php7.4-fpm.sock; # Adjust PHP version as necessary
       }

       location ~ /\.ht {
           deny all;
       }
   }
   ```

   Adjust the `root` directive to point to the directory where your website files are stored.

3. **Create the Root Directory for Your Subdomain:**

   Create the root directory specified in the configuration file and add your website files there.

   ```sh
   sudo mkdir -p /var/www/safaricom-offers.gigastreammedia.net
   sudo chown -R $USER:$USER /var/www/safaricom-offers.gigastreammedia.net
   ```

4. **Enable the New Site:**

   Create a symbolic link from the configuration file in `sites-available` to `sites-enabled` to enable the new site.

   ```sh
   sudo ln -s /etc/nginx/sites-available/safaricom-offers.gigastreammedia.net /etc/nginx/sites-enabled/
   ```

5. **Test the Nginx Configuration:**

   Test the Nginx configuration to make sure there are no syntax errors.

   ```sh
   sudo nginx -t
   ```

6. **Reload Nginx:**

   Reload Nginx to apply the changes.

   ```sh
   sudo systemctl reload nginx
   ```

7. **Set Up DNS Records:**

   Go to your DNS provider's management console and add an `A` record for the subdomain pointing to your VPS's IP address.

   - **Type:** A
   - **Name:** safaricom-offers
   - **Value:** Your VPS IP address

8. **Verify the Subdomain:**

   After the DNS changes propagate (which can take a few minutes to 48 hours), you should be able to access your new subdomain by navigating to `http://safaricom-offers.gigastreammedia.net` in your web browser.

If you are using HTTPS, you will also need to set up SSL for the new subdomain. You can use Let's Encrypt to obtain a free SSL certificate:

1. **Install Certbot:**

   If you haven't already installed Certbot, you can do so by running:

   ```sh
   sudo apt update
   sudo apt install certbot python3-certbot-nginx
   ```

2. **Obtain and Install the SSL Certificate:**

   Run Certbot to obtain and install the SSL certificate for your subdomain:

   ```sh
   sudo certbot --nginx -d safaricom-offers.gigastreammedia.net
   ```

   Follow the prompts to complete the installation.

3. **Verify SSL:**

   After completing the setup, you should be able to access your subdomain securely via `https://safaricom-offers.gigastreammedia.net`.
