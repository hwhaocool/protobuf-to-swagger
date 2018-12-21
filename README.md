# protobuf-to-swagger
Convert ptotobuf to swagger

## example
here we have a protobuf

```
//Pic Info
message PicInfo {
    string url                 = 1;    //url
    PhotoType photoType        = 2;    //type
    int32 height               = 3;    //height
    int32 width                = 4;    //width
    string cover               = 5;    //cover
}
```

use the python script, can convert it to swagger 

```
{
    "PicInfo": {
        "type": "object",
        "description": "Pic Info",
        "properties": {
            "url": {
                "type": "string",
                "description": "url"
            },
            "width": {
                "type": "integer",
                "description": "width"
            },
            "cover": {
                "type": "string",
                "description": "cover"
            },
            "photoType": {
                "description": "type",
                "$ref": "#/definitions/PhotoType"
            },
            "height": {
                "type": "integer",
                "description": "height"
            }
        }
    }
}
```

## how to use

`python Protobuf2Swagger.py`

