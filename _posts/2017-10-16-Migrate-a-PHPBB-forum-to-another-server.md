1. Migrate DB and files
1. `vim config.php`: adjust database credentials
1. change values in mysql table `phpbb_config`: cookie_domain, script_path, server_name, server_protocol, cookie_secure (https or not)
1. in table `phpbb_users` find the admin by name and change field user_password to $H$9GjTh1vwNcXO589vULn75HOQhSPSa/0 ("testtest")
1. `chmod 666 config.php`
1. `chmod 777 files store images/avatars/upload`
1. mv cache cache.old; mkdir cache; chmod 777 cache
1. shift+f5 (chrome)
