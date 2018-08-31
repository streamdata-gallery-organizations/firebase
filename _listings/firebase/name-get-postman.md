{
  "info": {
    "name": "Firebase Rules Get Name",
    "_postman_id": "b8c497f8-19bf-4137-b83d-aea683867235",
    "description": "Get a `Release` by name.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Name",
      "item": [
        {
          "id": "e2b7980f-80d8-4d36-9f36-0494785bf317",
          "name": "getName",
          "request": {
            "url": {
              "protocol": "http",
              "host": "firebaserules.googleapis.com",
              "path": [
                "v1",
                ":name"
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
            "description": "Get a `Release` by name."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "025f61e6-ffbe-4713-a96c-8dca95dfbeea"
            }
          ]
        },
        {
          "id": "06dc295f-55b8-4423-9d4a-e608eb542ecb",
          "name": "deleteName",
          "request": {
            "url": {
              "protocol": "http",
              "host": "firebaserules.googleapis.com",
              "path": [
                "v1",
                ":name"
              ],
              "variable": [
                {
                  "id": "name",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "DELETE",
            "body": {
              "mode": "raw"
            },
            "description": "Delete a `Release` by resource name."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "59f9dfa8-9d7d-4e22-95e4-37c86dfcbbb4"
            }
          ]
        }
      ]
    }
  ]
}