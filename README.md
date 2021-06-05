# docker-create-react-app

Use `docker` to create and develop React apps created with `create-react-app`.

So that `nodejs` is **not required** on your dev machine and the `node_modules` mess is avoided.

- [x] No need to worry about your local versions of `nodejs`/`yarn`
- [x] No need to worry about `npm` package versioning 
- [x] Sets up `node_modules` folder with Docker for seamless development 
- [x] Reproducible production builds 
- [x] Non-opinionated, just the basics

## Usage

1. Clone this repo
2. Run [`create`](./create)
3. Copy [`project/`](./project) folder to your own repo

```

```

4. Install additional dependencies (optional)

```sh
cd project/

# dev dependencies
bin/darn add --exact --dev \
  node-sass@4.14.1 \
  prettier \
  serve

# app dependencies
bin/darn add --exact \
  @popperjs/core@2.9.2 \
  axios \
  bootstrap@5.0.1 \
  react-bootstrap \
  react-query \
  react-router-dom
```

5. Start a development server

```sh
bin/darn start
```

6. Create a production build 

```sh
bin/parn build
```

The `darn` and  `parn` commands are simple wrappers around `docker-compose run` that make it shorter to type `yarn` commands inside `development` and `production` containers.
