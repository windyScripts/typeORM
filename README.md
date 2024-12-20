Instructions:

docker run -d --name postgres -e POSTGRES_PASSWORD="password" -p 5432:5432 postgres

npx typeorm init --name postgresql --database postgres

cd postgresql

follow along to https://typeorm.io/

## Notes

What does this property of an entity have as database datatype?
`@Column("text") 
`description: string`
It's text (not varchar 255)

What does this property of an entity have as database datatype?
`@Column("double")`
`views: number`
double, not integer

What is the name of the default superuser created by postgres?
postgres

explain the following line of code:
`docker exec -it postgres psql -U postgres`
-i interactive mode
-t allocates a pseudo-terminal to enable terminal like experience
postgres is name of container
psql is the interactive terminal (command line tool) used to execute SQL commands.
-U specifies the user to connect to db.

explain the following line of code:
`ALTER USER username WITH SUPERUSER;`
Makes username a superuser, assuming they exist as a user with auth details.

How do you create a user after connecting to the postgresql instance?
CREATE USER userName WITH PASSWORD password;

If I wanted to grant a user the right to connect to a database, what would the command look like?
GRANT CONNECT ON DATABASE your_database TO read_only_user;

After granting connection permission to a user to a database, how would I grant them the right to see it's schema?
GRANT USAGE ON SCHEMA public TO read_only_user;

after granting a user permission to see the schema of a table, how would you allow the user to read entries from the table?
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT SELECT ON TABLES TO read_only_user;

What is the relationship between entities and repositories in typeORM?
Each entity has its own repository which handles all operations with its entity.