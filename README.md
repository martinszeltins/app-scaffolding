# App scaffolding

App scaffolding with Vue.js (v3) and Laravel (v8) and Docker and JWT tokens for auth.

**Instructions**

````
$ git clone https://github.com/martinszeltins/app-scaffolding.git
$ cd app-scaffolding
$ docker-compose up -d
````

*Give it a few minutes to build.*

*And another minute after the build to install dependencies.*

The app will be running at [http://localhost:15319/](http://localhost:15319/)

<br>

**Important (!)**

*If containers get stopped, remove the containers (not images) and remove all volumes associated with app otherwise the seeder will try to run again and cause duplicate key conflict.*

<br>

**Change scaffold variables**

Search for all "scaffold" variables and change them to your liking.

<br>

**Intellisense**

In order to get intellisense to work, you should also install both client and server dependencies (npm install and composer install)

<br>

**Adminer**

You can connect from your host to the mysql container using adminer

````
System: MySQL
Server: 127.0.0.1:37092 (localhost won't work)
Username: root
Password: scaffold_password
````

<br>

**Add a TLS certificate**

You can easily add a TLS certificate using ````mkcert````

````
mkcert -install
mkcert yoursite.dev *.yoursite.dev
````

Then add it to docker-compose

volumes:
- ./webserver/etc/nginx/cert:/etc/nginx/cert

and also in nginx virtual host
