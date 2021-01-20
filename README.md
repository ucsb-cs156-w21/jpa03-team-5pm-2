# STARTER-lab03


* TODO: Change the title of this README 
  in the text `# STARTER-jpa03` above
  to match the name of your repo, i. e., `jpa03-yourgithubid`, then delete
  this TODO item.

* TODO: Correct the links to repo below, 
  then delete this TODO.  Replace it with 
  a link to your repo, e.g. 
  https://github.com/ucsb-cs156-w21/jpa03-cgaucho

Repo: https://ucsb-cs156-w21/STARTER-jpa03

* TODO: Correct the links to app on Heroku below, 
  then delete this TODO.  Replace it with 
  a link to your running app on Heroku, e.g.
  https://jpa03-cgaucho.herokuapp.com


On Heroku: https://jpa03-cgaucho.herokuapp.com

* TODO: Correct the links to codecov report below
  then delete this TODO.  Replace it with 
  a link to your codecov report.  Fix the URLs in the codecov
  badge markup below as well so that the badge links to your
  correct codecov report.

On Codecov: https://codecov.io/gh/ucsb-cs156-w21/jpa03-cgaucho

[![codecov](https://codecov.io/gh/ucsb-cs156-w21/jpa03-cgaucho/branch/main/graph/badge.svg)](https://codecov.io/gh/ucsb-cs156-w21/jpa03-cgaucho)


## Integrations

* The npm package `prettier` is used to implement a pre-commit hook that formats JavaScript code.  See: [docs/prettier.md](./docs/prettier.md) for more information.

## Getting Started

To get started with this application, you'll need to be able to
* Run it locally (i.e. on localhost)
* Deploy it to Heroku
* Get the test cases running on GitHub Actions
* See aggregrated code coverage statistics on Codecov

This application has integrations with the following third-party
services that require configuration
* Auth0.com (for authentication)
* Google (for authentication)
* A postgres database provisioned on Heroku

All of the setup steps for running the app on localhost and Heroku are described in these  file: 
* [./docs/SETUP-FULL.md](./docs/SETUP-FULL.md) if it is your first time setting up a Spring/React app with Auth0 and Google
* [./docs/SETUP-QUICKSTART.md](./docs/SETUP-QUICKSTART.md) if you've done these steps before.

## Setting up GitHub Actions (CI/CD, CodeCov)

To setup GitHub Actions so that the tests pass, you will need to configure
some _secrets_ on the GitHub repo settings page; see: [./docs/github-actions-secrets.md](./docs/github-actions-secrets.md) for details.

This file also describes the setup for Codecov

## Property file values

This section serves as a quick reference for values found in these files: 
* [`application.properties`](./src/main/resources/application.properties)
* [`secrets-localhost.properties`](./secrets-localhost.properties.SAMPLE)
* [`secrets-heroku.properties`](./secrets-heroku.properties.SAMPLE)

| Property name                                                     | Heroku only? | Explanation                                                               |
| ----------------------------------------------------------------- | ------------ | ------------------------------------------------------------------------- |
| `app.namespace`                                                   |              | See `Getting Started` below                                               |
| `app.admin.emails`                                                |              | A comma separated list of email addresses of permanent admin users.       |
| `app.member.hosted-domain`                                        |              | The email suffix that identifies members (i.e. `ucsb.edu` vs `gmail.com`) |
| `auth0.domain`                                                    |              | See `Getting Started` below                                               |
| `auth0.clientId`                                                  |              | See `Getting Started` below                                               |
| `security.oauth2.resource.id`                                     |              | Should always be `${app.namespace}/api`                                   |
| `security.oauth2.resource.jwk.keySetUri`                          |              | Should always be `https://\${auth0.domain}/.well-known/jwks.json`         |
| `spring.jpa.database-platform`                                    | Yes          | Should always be `org.hibernate.dialect.PostgreSQLDialect`                |
| `spring.datasource.driver-class-name`                             | Yes          | Should always be `org.postgresql.Driver`                                  |
| `spring.jpa.properties.hibernate.temp.use_jdbc_metadata_defaults` | Yes          | Should always be `false`                                                  |
| `spring.datasource.url`                                           | Yes          | Should always be `${JDBC_DATABASE_URL}`                                   |
| `spring.datasource.username`                                      | Yes          | Should always be `${JDBC_DATABASE_USERNAME}`                              |
| `spring.datasource.password`                                      | Yes          | Should always be `${JDBC_DATABASE_PASSWORD}`                              |
| `spring.jpa.hibernate.ddl-auto`                                   | Yes          | Should always be `update`                                                 |
