# Project Name

> Project description

## Related Projects

  - https://github.com/teamName/repo
  - https://github.com/teamName/repo
  - https://github.com/teamName/repo
  - https://github.com/teamName/repo

## Table of Contents

1. [Usage](#Usage)
1. [Requirements](#requirements)
1. [Development](#development)
4. [Database](#database)

## Usage

> Some usage instructions

## Requirements

An `nvmrc` file is included if using [nvm](https://github.com/creationix/nvm).

- Node 6.13.0
- etc

## Development

### Installing Dependencies

From within the root directory:

```sh
npm install -g webpack
npm install


```


##To initalize server and webpack
  From the command line run the following: 
    1) npm start
    2) npm run dev-react

##To seed the database. 


  1) From the command line, run these two commands: 
    mysql.server start
    mysql 
        (^^if the second command does not work run: 'sudo mysql')


  2)Uncomment line 91 in seedDB.js in the root directory

  3)From the command line, run these two commands to create and seed the database: 
    npm run create-db
    npm run get-data

  4) Comment out line 91 in seedDB.js to prevent reseeding of the database. 


##To initalize with live data from the eventId within the url

  1) In client/src/components/app.jsx, uncomment lines 24, 25, and 26

  2) In client/src/components/app.jsx, comment out line 27



##Install cors if not done already
  1) npm install --save cors
  2) in server/server.js, add the following:
    const cors = require('cors')
    app.use(cors())

## Database

To start up the database on Windows:
- start mysql server with CE GUI
- cd to root project folder
- `mysql` (enter)
- In mysql terminal:
```
  CREATE DATABASE meetup
    DEFAULT CHARACTER SET utf8mb4
    DEFAULT COLLATE utf8mb4_general_ci;
```
- `\. createDB.sql`
- ** database should be created **
- Schemas:
### events
```
+-----------+--------------+------+-----+---------+-------+
| Field     | Type         | Null | Key | Default | Extra |
+-----------+--------------+------+-----+---------+-------+
| event_id  | int(11)      | YES  |     | NULL    |       |
| id        | varchar(200) | YES  |     | NULL    |       |
| organizer | varchar(200) | YES  |     | NULL    |       |
+-----------+--------------+------+-----+---------+-------+
```
### users
```
+----------+--------------+------+-----+---------+-------+
| Field    | Type         | Null | Key | Default | Extra |
+----------+--------------+------+-----+---------+-------+
| PersonID | int(11)      | YES  |     | NULL    |       |
| id       | varchar(200) | YES  |     | NULL    |       |
| first    | varchar(200) | YES  |     | NULL    |       |
| last     | varchar(200) | YES  |     | NULL    |       |
| photoURL | varchar(200) | YES  |     | NULL    |       |
+----------+--------------+------+-----+---------+-------+
```
### events_users
```
+----------+--------------+------+-----+---------+-------+
| Field    | Type         | Null | Key | Default | Extra |
+----------+--------------+------+-----+---------+-------+
| event_id | varchar(200) | YES  |     | NULL    |       |
| user_id  | varchar(200) | YES  |     | NULL    |       |
+----------+--------------+------+-----+---------+-------+
```
