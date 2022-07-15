docker compose
------
docker-compose up -d

enable apisix mocking
------

start go access
------
tail -F access.log | docker run -p 7890:7890 --rm -i -e LANG=$LANG allinurl/goaccess -a -o html --log-format COMBINED --real-time-html - > report.html
