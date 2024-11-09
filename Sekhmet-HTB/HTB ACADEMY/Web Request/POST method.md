The credits or other data is send not in the url like GET. Instead it is sent in the HTTP request (the POST one).

```shell-session
curl -X POST -d 'username=admin&password=admin'
```