Docker Highcharts server
================================

A instance that can generate Highchart graphs by request

using ~~ancient sorcery~~ phantomjs
 
#### WHY


If your frontend is using highcharts graphs and you need that exact same graph

delivered in your email, look no further

saves a lot of time

#### FLOW

Server only accepts post requests

You send the highcharts config, it ouputs base64_encode(png)

On error the server will not die, you can docker exec to view the error

#### How to get the graph

open the dev console in chrome or ff
```
> JSON.stringify(Highcharts.charts[0].options)
```

thats the JSON you need to send


#### Read more

http://www.highcharts.com/docs/export-module/setting-up-the-server


http://phantomjs.org/documentation/


####  Setting up


```
$ docker-compose up -d
```

#### To consider

1) Don't forget about time zones http://api.highcharts.com/highcharts/global.timezoneOffset

2) I did't made a security audit of this thing, use over a firewall

#### Todo 

- logging 
- containerpilot or s6
- perf test
