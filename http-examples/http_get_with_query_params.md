# HTTP GET example with query params

Making a GET request on the following URL:

`http://api.tvmaze.com/shows/175?embed=episodes`

```
GET /shows/175?embed=episodes
User-Agent: PostmanRuntime/7.11.0
Accept: */*
Cache-Control: no-cache
Host: api.tvmaze.com
accept-encoding: gzip, deflate
Connection: keep-alive


HTTP/1.1 200
Server: nginx/1.10.3 (Ubuntu)
Date: Wed, 08 May 2019 23:57:46 GMT
Content-Type: application/json; charset=UTF-8
Transfer-Encoding: chunked
Connection: keep-alive
Vary: Accept-Encoding
Access-Control-Allow-Origin: *
Cache-Control: public, max-age=3600
Content-Encoding: gzip

{
  "id": 175,
  "url": "http://www.tvmaze.com/shows/175/house-of-cards",
  "name": "House of Cards",
  "type": "Scripted",
  "language": "English",
  "genres": ["Drama", "Thriller"],
  "status": "Ended",
  "runtime": 60,
  "premiered": "2013-02-01",
  "officialSite": "https://www.netflix.com/title/70178217",
  "schedule": { "time": "", "days": ["Friday"] },
  "rating": { "average": 8.5 }
}
```
