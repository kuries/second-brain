- (command to create a new user with all the privilges)
grant all on *.* to 'admin'@'localhost' identified by 'password'  with grant option;

- (Flush the privileges to ensure that they are saved and available in the current session)
FLUSH PRIVILEGES;

- (lists all the users)
SELECT User,Host FROM mysql.user;

- (shows the priviliges of a user)
SHOW GRANTS FOR 'admin@localhost';

- (revokes all grants for a mysql user)
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'bloguser'@'localhost'; 

- (drops user)
DROP USER 'bloguser'@'localhost';