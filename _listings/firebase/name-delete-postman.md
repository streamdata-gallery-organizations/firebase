{
  "info": {
    "name": "Firebase Rules Delete Name",
    "_postman_id": "5d5eb3c4-02d6-46fa-8334-f5d102af3164",
    "description": "Delete a `Release` by resource name.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Name",
      "item": [
        {
          "id": "692170c5-62fc-4abc-ac42-dfe26179e575",
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
              "id": "394726ad-e168-45db-80f9-ec439268ce51"
            }
          ]
        }
      ]
    }
  ]
}