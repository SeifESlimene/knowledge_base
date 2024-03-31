.| Command     | Description |
| ----------- | ----------- |
| `sudo -u postgres psql` | Connect To psql with user postgres |
| `\x` | Toggle Expanded Mode |
| `\?` | See All Commands |
| `SELECT version();` | Knowing The Version Of PostgreSQL |
| `\du or \du+` | List all user accounts (or roles) in the current PostgreSQL database server |
| `\l` | List All Available Databases For A Specific User |
| `SELECT current_database();` | Return The Name Of The Current Database |
| `\c <database_name>` | Switching To Another Database |
| `\dt` | Enlisting The Available Tables In The current Database |
| `\d Table` | Describing A Particular Table |
| `TABLE mytablename; or SELECT * FROM mytablename;` | Show All Data Inside A Table |
| `\g` | Seeing The Previously Executed Command |
| `\q` | Quit postgresql |
| `sudo -u postgres psql -c "show data_directory;"` | Show Directory Data |
| `ALTER USER postgres PASSWORD '123456';` | Change Password Of A Specific User |
| `CREATE DATABASE "cars";` | Creating A Database |
| `create user seif with encrypted password 'apprentus-dev-password-seif';` | Creating A User |
| `grant all privileges on database "apprentus-seif" to seif;` | Grant access to DB to user |
| `\c - a_new_user` | Change User |
| `\conninfo` | To get information about current connection |
| `\c a_new_database a_new_user.` | To Change Database And User |
| 'SELECT count(*) FROM mytablename;` | Row count of a table in PostgreSQL |

##### Clear The Screen:

> `$ Type ctrl + l`

---

#### Make postgres listen to outside world:
https://www.bigbinary.com/blog/configure-postgresql-to-allow-remote-connection
> `$ sudo find / -name "postgresql.conf"`

> `$ sudo find / -name "pg_hba.conf"`

> `$ sudo /etc/init.d/postgresql restart`

---

> `$ sudo service postgresql status`

> `$ sudo service postgresql start`

> `$ sudo service postgresql stop`

> `$ sudo service postgresql restart`

> `$ sudo /etc/init.d/postgresql status`

> `$ sudo /etc/init.d/postgresql start`

> `$ sudo /etc/init.d/postgresql stop`

> `$ sudo /etc/init.d/postgresql restart`

> `$ sudo systemctl status postgresql`

> `$ sudo systemctl start postgresql`

> `$ sudo systemctl stop postgresql`

> `$ sudo systemctl restart postgresql`
