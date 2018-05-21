{
  "info": {
    "name": "Firebase Dynamic Links Get Dynamiclink Linkstats",
    "_postman_id": "ddc4acc3-a47f-4620-8df5-b02f0a59bd1d",
    "description": "Fetches analytics stats of a short Dynamic Link for a given\nduration. Metrics include number of clicks, redirects, installs,\napp first opens, and app reopens.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Dynammic",
      "item": [
        {
          "id": "e28ae65f-9382-460b-ac79-165ef25e5aa1",
          "name": "firebasedynamiclinks.getLinkStats",
          "request": {
            "url": {
              "protocol": "http",
              "host": "firebasedynamiclinks-ipv6.googleapis.com",
              "path": [
                "v1",
                ":dynamicLink/linkStats"
              ],
              "query": [
                {
                  "key": "durationDays",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "dynamicLink",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Fetches analytics stats of a short Dynamic Link for a given\nduration. Metrics include number of clicks, redirects, installs,\napp first opens, and app reopens."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "a3a418ad-98f6-4036-bf26-536bf80b2b33"
            }
          ]
        }
      ]
    }
  ]
}