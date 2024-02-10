<h1 align="center">NodeJS Polls</h1>

<p><b>What did I build!?</b></p>
 
I developed the project with `TypeScript`, `Fastify`, `Prisma` and `Redis`, exploring API concepts, such as the HTTP method and routes, in addition to getting my hands dirty creating tables using Prisma. The idea of ​​the project is in the name itself, polls. I want users to be able to create their polls, search for other polls (by id) and vote on them, in addition to validating the user's action logic. The Redis database was used to handle the vote cache and organize the ranking of the most voted options. All this with realtime functionality using `websockets`.

<p><b>Pub/Sub Pattern</b></p>

The `Pub/Sub` (publication/subscription) pattern is a messaging model where senders (publishers) send messages to channels without knowing who will receive them, while receivers (subscribers) subscribe to specific channels to receive messages of interest. In real-time communication systems with Web Sockets, this allows efficient and asynchronous communication between different system components, facilitating a flexible and scalable architecture.

Start development:

```sh
git clone https://github.com/pratesMath/nodejs-polls.git
cd node-polls
npm ci
```

<h2>Let's Setup the project</h2>

create the project from scratch:

```sh
npm init -y
```

<p>Install (production) dependencies: </p>

```sh
npm i fastify zod ioredis @fastify/cookie @fastify/websocket @prisma/client
```

<p>Install dev dependencies: </p>

```sh
npm i -D typescript @types/node tsx prisma
```

<p>Initialize TypeScript with <b>tsc</b>: </p>

```sh
npx tsc --init
```

<h3>PostgreSQL with docker and Prisma ORM</h3>

After configuring the `docker-compose.yml` file, run the command below:

```sh
docker compose up -d
```

To check the images raised by Docker Compose use:

```sh
docker ps
```

Copy `.env.example` file:

```sh
cp .env.example .env
```

<p>Initialize Prisma (ORM): </p>

```sh
npx prisma init
```

Give your migration a name after changing the schema.prisma file in the prisma folder:

```sh
npx prisma migrate dev
```

<p><b>NOTE</b>: if you have problems running <b>Prisma ORM</b> in the project using docker because you have postgreSQL installed and configured locally like me, try stopping your postgreSQL database from running. The commands below are there to help you: </p>

```sh
sudo systemctl status postgresql # to check the postgresql status
sudo systemctl stop postgresql # to stop postgresql from working
sudo systemctl start postgresql # to get PostgreSQL running
```

<div align="center">
  <p>Made w/ 💙 by <a href="https://github.com/pratesMath">pratesMath</a>.</p>
</div>
