brew install postgresql

brew services start postgresql
brew services stop postgresql

psql postgres

\conninfo | connect information
\q | Exit psql connection
\c | Connect to a new database
\dt | List all tables
\du | List all roles
\list | List databases

 CREATE ROLE me WITH LOGIN PASSWORD 'password';
 ALTER ROLE me CREATEDB;

 \q
 psql -d postgres -U me;
 \list

 \c api

 CREATE TABLE users (
  ID SERIAL PRIMARY KEY,
  name VARCHAR(30),
  email VARCHAR(30)
);

 INSERT INTO users (name, email)
  VALUES ('Jerry', 'jerry@example.com'), ('George', 'george@example.com');


npm i express postgres

http://localhost:3000/users
http://localhost:3000/users/1
curl --data "name=Elaie&email=elaie@example.com" http://localhost:3000/users
curl -X PUT -d "name=Kramer" -d "email=kramer@example.com" http://localhost:3000/users/1
curl -X "DELETE" http://localhost:3000/users/1
