## Intro to Postgresql

Tags: #postgresql #intro
See also :
Previous :

### Body
1) To login
	- **sudo -u postgres psql** 
2) Create a new database called testdb, owned by testuser.
	-  **sudo -u postgres createdb --owner=testuser testdb**
3) Create a new PostgreSQL user called testuser, allow user to login, but NOT creating databases
    - **sudo -u postgres createuser --login --pwprompt testuser** 
4) Login to PostgreSQL: psql -U user database
     - **psql -U testuser testdb**
 5) **sudo systemctl stop postgresql
	 sudo systemctl disable postgresql**
 6) \q to quit from console
### References

- https://www.digitalocean.com/community/tutorials/how-to-use-postgresql-with-your-django-application-on-ubuntu-16-04
- https://www3.ntu.edu.sg/home/ehchua/programming/sql/PostgreSQL_GetStarted.html
- https://stackoverflow.com/questions/10757431/postgres-upgrade-a-user-to-be-a-superuser