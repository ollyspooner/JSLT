# Recursively transform objects to key value pairs

## JSLT

```JSLT
def convert-object(object)
    [
        for($object) {
          "key": .key,
          "value": if(is-object(.value))
            convert-object(.value)
          else
            .value
        }
    ]

{
    "data": convert-object(.data),
    "errors": .errors,
    "extensions": .extensions
}
```

## JSON

```JSON
{
    "data": {
        "createCustomer": {
            "clientMutationId": "MyRef0001",
            "customer": {
                "id": "Y3VzdG9tZXJfODkxOTE4Njc4MTY",
                "legacyId": "89191867816",
                "company": "Test Company",
                "createdAt": "2023-03-15T11:45:03.000000Z",
                "email": "dave@example.com",
                "firstName": "Dave",
                "lastName": "Test0001",
                "phoneNumber": "+44 7700 900666",
                "fax": "+44 7700 900667",
                "website": "https://www.example.com"
            }
        }
    },
    "extensions": {
        "requestId": "0d6ab553-df16-4a44-b4ad-5f20b4859a1d"
    }
}
```

## Result

```JSON
{
    "data" : [
        {
            "key" : "createCustomer",
            "value" : [
                {
                    "key" : "clientMutationId",
                    "value" : "MyRef0001"
                }, {
                    "key" : "customer",
                    "value" : [
                        {
                            "key" : "id",
                            "value" : "Y3VzdG9tZXJfODkxOTE4Njc4MTY"
                        }, {
                            "key" : "legacyId",
                            "value" : "89191867816"
                        }, {
                            "key" : "company",
                            "value" : "Test Company"
                        }, {
                            "key" : "createdAt",
                            "value" : "2023-03-15T11:45:03.000000Z"
                        }, {
                            "key" : "email",
                            "value" : "dave@example.com"
                        }, {
                            "key" : "firstName",
                            "value" : "Dave"
                        }, {
                            "key" : "lastName",
                            "value" : "Test0001"
                        }, {
                            "key" : "phoneNumber",
                            "value" : "+44 7700 900666"
                        }, {
                            "key" : "fax",
                            "value" : "+44 7700 900667"
                        }, {
                            "key" : "website",
                            "value" : "https://www.example.com"
                        }
                    ]
                }
            ]
        }
    ],
    "extensions" : {
        "requestId" : "0d6ab553-df16-4a44-b4ad-5f20b4859a1d"
    }
}
```
