
#### install postgres
```bash
$ sudo aptitude install postgresql postgresql-contrib
```

#### Create User and DataBase in Postgres
```bash
$ sudo su - postgres
postgres@django:~$ createuser --interactive -P
Enter name of role to add: user
Enter password for new role: 
Enter it again: 
Shall the new role be a superuser? (y/n) n
Shall the new role be allowed to create databases? (y/n) n
Shall the new role be allowed to create more new roles? (y/n) n
postgres@django:~$
```

#### Create DataBase
```bash
postgres@django:~$ createdb --owner user database_name
postgres@django:~$ logout
```

#### Create Group and to assign User
```bash
$ sudo groupadd --system webapps
$ sudo useradd --system --gid webapps --shell /bin/bash --home /var/www/html/django/sistravent sistravent
```

#### install Virtualenv
```bash
$ sudo aptitude install python-virtualenv

$ sudo mkdir -p /var/www/html/django/sistravent/
$ sudo chown sistravent:webapps /var/www/html/django/sistravent/
$ sudo apt-get install python-pip
$ sudo apt-get install libjpeg8 libjpeg62-dev libfreetype6 libfreetype6-dev
$ sudo apt-get install build-essential libssl-dev libffi-dev python-dev
$ sudo su - sistravent

sistravent@django:~$ virtualenv virtual -p python3.4
$ git clone git@gitlab.com:pever/sistravent.com.git sistravent
sistravent@localhost:~$ source virtual/bin/activate

(virtual)sistravent@localhost:~/sistravent$ pip install -r requirements/local.txt
```
