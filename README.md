# python-web-bottle-api-basic-auth-ssl-mysql-raw-sql-simple

## Description
Simple web app that serves static pages
for a bottle project.

Uses sqlalchemy raw sql to query a table `dog`.

Is self-signed ssl cert.
Requires basic authentication for endpoints.

| username | password |
| -------- | -------- |
| *user* | *pass* |

Remotely tested with *testify*, ssl is not verified.

## Tech stack
- python
  - bottle
  - sqlalchemy
  - cheroot
  - testify
  - requests
- bootstrap
- jquery
- dataTable
- mariadb
- ssl

## Docker stack
- alpine:edge
- python:latest
- mariadb:latest

## To run
`sudo ./install.sh -u`
- Get all dogs: https://localhost/dog
  - Schema id, breed, and color
- CRUD opperations
  - Create: curl -i -k -X PUT localhost/dog/<id> -u 'user:pass'
  - Read: https://localhost/dog/<id>
  - Update: curl -i -k -X POST localhost/dog/<id>/<breed>/<color>  -u 'user:pass'
  - Delete: curl -i -k -X DELETE localhost/dog/<id>  -u 'user:pass'

## To stop
`sudo ./install.sh -d`

## For help
`sudo ./install.sh -h`

## Credit
- [Bottle sqlalchemy setup](https://github.com/iurisilvio/bottle-sqlalchemy/blob/master/examples/basic.py)
- [Disable ssl for testing](https://stackoverflow.com/questions/23013220/max-retries-exceeded-with-url-in-requests)