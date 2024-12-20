Instructions:

docker run -d --name postgres -e POSTGRES_PASSWORD="password" -p 5432:5432 postgres

npx typeorm init --name postgresql --database postgres

cd postgresql

follow along to https://typeorm.io/