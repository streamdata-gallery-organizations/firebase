{
  "info": {
    "name": "Firebase Rules Get Name Getexecutable",
    "_postman_id": "a6386855-8a28-4907-86c6-eb658539d003",
    "description": "Get the `Release` executable to use when enforcing rules.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Names",
      "item": [
        {
          "id": "4a6a3ba2-1a13-4a2d-a0cc-06524f63079b",
          "name": "getNameGetexecutable",
          "request": {
            "url": {
              "protocol": "http",
              "host": "firebaserules.googleapis.com",
              "path": [
                "v1",
                ":name:getExecutable"
              ],
              "query": [
                {
                  "key": "executableVersion",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "name",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get the `Release` executable to use when enforcing rules."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "6c83dac6-a3cc-4b08-9360-01f48d2864b1"
            }
          ]
        }
      ]
    }
  ]
}