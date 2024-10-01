These are the current running ports
```
kipngeno@srv565586:/var/www/data-api.gigastreammedia.net/bundle-purchase$ sudo lsof -i -P -n | grep LISTEN
[sudo] password for kipngeno: 
systemd-r    670 systemd-resolve   14u  IPv4   20569      0t0  TCP 127.0.0.53:53 (LISTE)
sshd       66707            root    3u  IPv4  758972      0t0  TCP *:22 (LISTEN)
sshd       66707            root    4u  IPv6  758974      0t0  TCP *:22 (LISTEN)
node      149903        kipngeno   18u  IPv6 1420047      0t0  TCP *:3000 (LISTEN)
postgres  182561        postgres    5u  IPv6 1659359      0t0  TCP [::1]:5432 (LISTEN)
postgres  182561        postgres    6u  IPv4 1659360      0t0  TCP 127.0.0.1:5432 (LISTEN)
node      256626        kipngeno   18u  IPv6 2161333      0t0  TCP *:3005 (LISTEN)
nginx     403313            root    6u  IPv4 3248364      0t0  TCP *:443 (LISTEN)
nginx     403313            root    7u  IPv4 3248365      0t0  TCP *:80 (LISTEN)
nginx     403313            root    8u  IPv6 3248366      0t0  TCP *:80 (LISTEN)
nginx     549484        www-data    6u  IPv4 3248364      0t0  TCP *:443 (LISTEN)
nginx     549484        www-data    7u  IPv4 3248365      0t0  TCP *:80 (LISTEN)
nginx     549484        www-data    8u  IPv6 3248366      0t0  TCP *:80 (LISTEN)
nginx     549485        www-data    6u  IPv4 3248364      0t0  TCP *:443 (LISTEN)
nginx     549485        www-data    7u  IPv4 3248365      0t0  TCP *:80 (LISTEN)
nginx     549485        www-data    8u  IPv6 3248366      0t0  TCP *:80 (LISTEN)
nginx     549486        www-data    6u  IPv4 3248364      0t0  TCP *:443 (LISTEN)
nginx     549486        www-data    7u  IPv4 3248365      0t0  TCP *:80 (LISTEN)
nginx     549486        www-data    8u  IPv6 3248366      0t0  TCP *:80 (LISTEN)
nginx     549487        www-data    6u  IPv4 3248364      0t0  TCP *:443 (LISTEN)
nginx     549487        www-data    7u  IPv4 3248365      0t0  TCP *:80 (LISTEN)
nginx     549487        www-data    8u  IPv6 3248366      0t0  TCP *:80 (LISTEN)
```
