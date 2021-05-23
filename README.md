# graphql-boilerplate

![](https://imgur.com/eMpNw0e.png)

Boilerplate for a scalable, production-ready GraphQL gateway server.

A hosted demo is available at https://graphql-bp.now.sh

## Features

* Database (via [Graphcool](https://graph.cool))
* User authentication

## Getting started

#### Requirements

* Node 8 (or higher)
* Graphcool CLI (Get it via `npm i -g graphcool@alpha`)
* GraphQL CLI (Get it via `npm i -g graphql-cli@beta`)
* Optional: GraphQL Playground desktop app (Download [here](https://github.com/graphcool/graphql-playground/releases))

#### Setup your project

```sh
# 1 .From your root directory of choice execute:
graphql create [project-name]

# 2. Choose the "Basic (TypeScript, DB, Auth) option

# 3. Navigate to the new project
cd [project-name]

#4. Deploy the Graphcool database
graphcool deploy
```

#### Launch the local server

```sh
# Start server (runs on http://localhost:4000)
yarn start

# Open Playground to explore GraphQL API
yarn playground
```

## Docs

### Commands

* `yarn start` starts GraphQL server
* `yarn debug` starts GraphQL server in debug mode (open [chrome://inspect/#devices](chrome://inspect/#devices) to debug)
* `yarn playground` opens the GraphQL Playground
* `yarn build` builds the application
* `yarn deploy` deploys GraphQL server to [`now`](https://now.sh)

### Project Overview
#### `/`
- [`.env`](https://github.com/graphcool/graphql-boilerplate/blob/master/.env) Contains important environment variables for development. Read more about `.env` [here](https://github.com/motdotla/dotenv)
- [`.graphqlconfig.yml`](https://github.com/graphcool/graphql-boilerplate/blob/master/.graphqlconfig.yml) GraphQL Config file containing the endpoints and schema configuration. Used by the [`graphql-cli`](https://github.com/graphcool/graphql-cli) and the [GraphQL Playground](https://github.com/graphcool/graphql-playground). See [graphql-config](https://github.com/graphcool/graphql-config) for more information.

#### `/database`
- [`/database/datamodel.graphql`](https://github.com/graphcool/graphql-boilerplate/blob/master/database/datamodel.graphql) contains the Database model that you define
- [`/database/schema.graphql`](https://github.com/graphcool/graphql-boilerplate/blob/master/database/schema.graphql) contains the database API that is being generated based on your `datamodel.graphql`

#### `/src`
- [`/src/schema.graphql`](https://github.com/graphcool/graphql-boilerplate/blob/master/src/schema.graphql) contains the GraphQL API of your application that is exposed to the world
- [`/src/index.ts`](https://github.com/graphcool/graphql-boilerplate/blob/master/src/index.ts) is the entry point of your application, pulling everything together and starting the [`graphql-yoga`](https://github.com/graphcool/graphql-yoga) Server.
- [`/src/resolvers/`](https://github.com/graphcool/graphql-boilerplate/tree/master/src/resolvers) includes the actual business logic of your application. In GraphQL you implement [resolvers](http://graphql.org/learn/execution/) that *resolve*  a specific query being requested
