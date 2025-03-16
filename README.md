/

-src/
    -index.js //main server file
    -models/
    controllers/
    middlewares/
    services/
    utils/
    config/
    repository/  [how we will be handling the models of the DB]

    
-tests/  [later]
-static/
-temp/



# welcome to Flights Service

#Project setup
-Clone the project on your local
-Execute `npm install` on the same path as of your root directory of the downloaded project.

-Create a `.env` file in the root directory and add the following enviroment variable
- `PORT = 3000`
-Inside the `src/config` folder create a new file `config.json` and then add the folloing piece of json

```
"development": {
    "username": "<Your DB login name>",
    "password": "<Your DB Password>",
    "database": "Flights_Search_DB_DEV",
    "host": "127.0.0.1",
    "dialect": "mysql"
  },
 

```

-Once you've added your db config db config as listed above, go to the src folder from your terminal and execute `npx sequalize db:create`

# DB Design
-Airplane Table [Id, model_number, capacity, created_at, updated_at]
-Flight [id , src_airport_id, dest_airport_id, departure_date, arrival_date, departure_time, arrival_time]
-Airport[id , name, city_id, address]
-city [id, name]

-airplane ----1:N---> flights
-city---1:N--->airport
-Airport--N:1--->flights