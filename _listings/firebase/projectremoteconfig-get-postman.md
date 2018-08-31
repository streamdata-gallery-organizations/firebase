{
  "info": {
    "name": "Firebase Remote Config Get Project Remoteconfig",
    "_postman_id": "776c871a-21a1-4150-91cb-c0f18743e030",
    "description": "Get the latest version Remote Configuration for a project.\nReturns the RemoteConfig as the payload, and also the eTag as a\nresponse header.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Project",
      "item": [
        {
          "id": "654c913a-7fc4-4e3b-841a-38e69d37fa8c",
          "name": "getProjectRemoteconfig",
          "request": {
            "url": {
              "protocol": "http",
              "host": "firebaseremoteconfig.googleapis.com",
              "path": [
                "v1",
                ":project/remoteConfig"
              ],
              "variable": [
                {
                  "id": "project",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get the latest version Remote Configuration for a project.\nReturns the RemoteConfig as the payload, and also the eTag as a\nresponse header."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "360fa15a-1823-402a-9b96-14c8d6ee9bf0"
            }
          ]
        }
      ]
    }
  ]
}