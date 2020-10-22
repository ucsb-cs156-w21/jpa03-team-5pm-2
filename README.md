# STARTER-lab03


* TODO: Change the title of this README 
  in the text `# STARTER-jpa03` above
  to match the name of your repo, i. e., `jpa03-yourgithubid`, then delete
  this TODO item.

* TODO: Correct the links to repo below, 
  then delete this TODO.  Replace it with 
  a link to your repo, e.g. 
  https://github.com/ucsb-cs156-f20/jpa03-cgaucho

Repo: https://ucsb-cs156-f20/STARTER-jpa03

* TODO: Correct the links to app on Heroku below, 
  then delete this TODO.  Replace it with 
  a link to your running app on Heroku, e.g.
  https://cs156-f20-jpa03-cgaucho.herokuapp.com


On Heroku: https://cs156-f20-jpa03-cgaucho.herokuapp.com

* TODO: Correct the links to codecov report below
  then delete this TODO.  Replace it with 
  a link to your codecov report.  Fix the URLs in the codecov
  badge markup below as well so that the badge links to your
  correct codecov report.

On Codecov: https://codecov.io/gh/ucsb-cs156-f20/jpa03-cgaucho

[![codecov](https://codecov.io/gh/ucsb-cs156-f20/demo-spring-react-todo-app/branch/main/graph/badge.svg)](https://codecov.io/gh/ucsb-cs156-f20/demo-spring-react-todo-app)


# About this Repo: Demo Spring React App

This is a demo todo app with Spring Boot and Create React App.

This version was created as a branch off of version 1.1.0 of the code
in this repo, which has ongoing development.   By the time you
work with this starter code, the code in this original repo may
have further commits, features, bug fixes, etc.

* <git@github.com:ucsb-cs156-f20/demo-spring-react-todo-app.git>

## Getting started

The first thing you'll want to do is set up your Auth0 SPA App. Instructions for setting up auth0 can be found [here](./docs/auth0.md).

- As part of these instructions, you will have created `javascript/.env.local` from `javascript/.env.local.SAMPLE`
- Next, run this command to create a secrets file for the backend when running on localhost:
  ```bash
  cp secrets-localhost.properties.SAMPLE secrets-localhost.properties
  ```
- Next, you need update the values in your new `secrets-localhost.properties`. You can copy the corresponding values from the `javascript/.env.local`,
  using this guide:

  | For this value in `secrets-localhost.properties` | Use this value from `javascript/.env.local` |
  | ------------------------------------------------ | ------------------------------------------- |
  | `auth0.domain`                                   | `REACT_APP_AUTH0_DOMAIN`                    |
  | `auth0.clientId`                                 | `REACT_APP_AUTH0_CLIENT_ID`                 |
  | `security.oauth2.resource.id`                    | `REACT_APP_AUTH0_AUDIENCE`                  |

  You may see additional values in `secrets-localhost.properties` such as the ones below. You do not need to adjust these; leave the values alone.

  ```
  security.oauth2.resource.jwk.keySetUri=https://${auth0.domain}/.well-known/jwks.json
  ```

At this point, you should be able to run the app locally via

```bash
mvn spring-boot:run
```

## Deploying to Production

To deploy to production on Heroku, see: [./docs/heroku.md](./docs/heroku.md)

## Setting up GitHub Actions

To setup GitHub Actions so that the tests pass, you will need to configure
some _secrets_ on the GitHub repo settings page; see: [./docs/github-actions-secrets.md](./docs/github-actions-secrets.md) for details.
