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
cd nginx_log
tail -F access.log | docker run -p 7890:7890 --rm -i -v ../nginx_log/:/logs -v ../goaccess_conf/goaccess.conf:/etc/goaccess/goaccess.conf -e LANG=$LANG allinurl/goaccess -a -o html - > index.html


port
----
nginx -> 80
apisix dashboard -> 9000