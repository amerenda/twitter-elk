# twitter-elk
Searches public twitter for keywords, writes the tweet data into an elasticsearch index (via logstash), and lets you graph/map the data with kibana.

## Docker files
### To start
- clone or fork project
- go to: https://apps.twitter.com/ and create a new app and get consumer/oauth keys
- edit logstash/config/twitter.conf put your consumer and oauth keys in (found above)
- edit logstash/config/twitter.conf and adjust keywords [More Info](https://www.elastic.co/guide/en/logstash/current/plugins-inputs-twitter.html)
- install [docker](https://docs.docker.com/engine/installation/) and [docker-compose](https://docs.docker.com/compose/install/)
- Start with `docker-compose up`
- You can also use `docker-compose up -d` to run as a backgroun daemon
- open 127.0.0.1 in a browser to view data

## WARNING
This exposes port 80 to all ips on your computer and forwards it to kibana with no auth. Anyone who is on your network/can access your IP will be able to view all of the data saved here. Edit docker-compose.yml if you would like to tinker with this. If you want to add security, you'll need to install the [x-pack plugin](https://www.elastic.co/downloads/x-pack) and add security. 
More info found [here](https://www.elastic.co/guide/en/x-pack/current/setting-up-authentication.html)
