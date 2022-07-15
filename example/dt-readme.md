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
tail -F access.log | docker run -p 7890:7890 --rm -i -e LANG=$LANG allinurl/goaccess -a -o html --log-format COMBINED --real-time-html - > report.html
