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

---
## Endpoints


### Application
```
http://localhost:3007
```

### Users
```
http://localhost:5001/users
```

### Swagger UI
```
http://localhost:5001/doc/
```

### Sanity Check
```
http://localhost:5001/ping
```
---


