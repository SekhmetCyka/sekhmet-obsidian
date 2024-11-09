

| Command                                           | Description                                |
| ------------------------------------------------- | ------------------------------------------ |
| `curl https://pornhub.com`                        | Send the html code of the page             |
| `curl -o https://pornhub.com/roccoInfo.php`       | Send the file 'roccoInfo.php'              |
| `curl -k https://pornhub.com`                     | Will ignore invalid SSL key                |
| `curl -v https://pornhub.com`                     | Show all requestst (GET and RESPONSE)      |
| `curl -I https://pornhub.com`                     | Only see the response Header               |
| `curl -i https://pornhub.com`                     | See both Header (request and response)     |
| `curl -H https://pornhub.com`                     | Only see the request Header                |
| `curl -A https://pornhub.com`                     | Set the user agent with what we request    |
| `curl -X POST -d 'username=admin&password=admin'` | -X to specify POST and -d specify the data |
| `curl -b "admin cookies"`                         | -b to specify cookies used                 |
curl -X POST -d '{"search":"flag"}' -b 'PHPSESSID=u5mlr5ht9m8pqgotif7aa1vhg2' -H 'Content-Type: application/json' http://94.237.55.236:48989/search.php
