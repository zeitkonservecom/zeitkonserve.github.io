1. Migrate DB and files
1. `vim config.php`: adjust database credentials
1. change values in mysql table `phpbb_config`: cookie_domain, script_path, server_name, server_protocol
1. `chmod 666 config.php`
1. `chmod 777 files store images/avatars/upload`
1. mv cache cache.old; mkdir cache; chmod 777 cache
