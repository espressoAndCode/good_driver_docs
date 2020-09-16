# Good (Truck) Driver Incentive Program

## Developer Instructions

This project requires [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/). Please verify that these are installed and running correctly before proceeding.

---
## Setup

### Clone the Repo
```
$ git clone https://F20-Team14-Borbely-Bailey-Shaw@dev.azure.com/F20-Team14-Borbely-Bailey-Shaw/F20-Team14-Borbely.Bailey.Shaw/_git/F20-Team14-Borbely.Bailey.Shaw
$ cd F20-Team14-Borbely.Bailey.Shaw
```
### Set the following environment variable

This defines the base URL for AJAX requests from the React app. 
 
```
$ export REACT_APP_USERS_SERVICE_URL=http://localhost:5001
```
**PRO TIP** - put this in your `.bashrc` file so you don't have to enter it every time you open a shell. It becomes a pain, and I promise that you'll forget.

If you do it this way, be sure to add double quotes around the value like this:
```
export REACT_APP_USERS_SERVICE_URL="http://localhost:5001"
```

### Build the images
```
$ docker-compose build
```

### Run the containers
```
$ docker-compose up -d
```
Note - the `-d` flag runs a detached container, meaning that it gives no shell logging. During development you may want to omit this flag for more verbose feedback. 

---

### Sanity Check

Type the following command:
```
http://localhost:5001/ping
```
If everything is running correctly on the server you should see:
```
{
  "message": "pong!",
  "status": "success"
}
```
---
## Database
### Create the database
```
$ docker-compose exec users python manage.py recreate_db
```

### Seed the database
```
$ docker-compose exec users python manage.py seed_db
```
The database uses a persistent volume, meaning that you only need to create the database and seed it with data once. The data will be preserved between container restarts. If you have added a bunch of data and want to reset, you can nuke the database with the `recreate_db` command. It's optional to run `seed_db`, but it gives a few values to start off.


Want to access the *Postgres* database via psql?
```
$ docker-compose exec users-db psql -U postgres
```
Then, you can connect to the database and run SQL queries. For example:
```
# \c users_dev
# select * from users;
```

---
## Endpoints

### Application

This is the URL for the client side of the application, the *React* web application user interface:
```
http://localhost:3007
```

### Users

You can directly access the *Flask* backend users endpoint via the exposed endpoint:
```
http://localhost:5001/users
```

### Swagger UI

[Swagger UI](https://swagger.io/tools/swagger-ui/) is an open-source API documentation generator that allows developers to interact with the actual API and examine endpoints, signatures, and responses thorugh a convenient web interface. view The Swagger UI, navigate to the following URL. 

```
http://localhost:5001/doc/
```
---

# Other Commands

To stop the containers:
```
$ docker-compose stop
```
To bring down the containers:
```
$ docker-compose down
```
Want to force a build?
```
$ docker-compose build --no-cache
```
Remove images:
```
$ docker rmi $(docker images -q)
```

# Developing with Docker

The Docker containers offer a convenient way to create a consistent development environment so that all developers can have confidence that their work will run in the production environment.  

When you run the *docker-compose up* command, Docker references the *docker-compose.yml* file for a variety of instructions about how to build and run the containers. A couple of the commands are:
```
users:
    volumes:
      - './services/users:/usr/src/app'
```
and:
```
client:
    volumes:
      - './services/client:/usr/src/app'
```
These commands create *bindings* that connect the docker container with your local file system. This means that you can open the project in your code editor, make changes, and immediately see those changes updated into the running container.






















