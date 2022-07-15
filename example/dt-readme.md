docker compose
------
docker-compose up -d

enable apisix mocking
------

```
{
  "content_type": "application/json",
  "delay": 0,
  "disable": false,
  "response_example": "{\n\t\"message\":\"success\",\n\t\"code\":\"0000\"\n}",
  "response_status": 200,
  "with_mock_header": true
}
```

start go access
------
export apisix_home=/home/ubuntu/apisix-docker
docker run -p 7890:7890 --rm -i -v $apisix_home/example/nginx_log/:/logs -v $apisix_home/example/goaccess_conf/goaccess.conf:/etc/goaccess/goaccess.conf -e LANG=$LANG allinurl/goaccess -a -o html - > index.html


port
----
nginx -> 80
apisix dashboard -> 9000