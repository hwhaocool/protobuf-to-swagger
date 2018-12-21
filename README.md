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
    date createTime            = 6;    //time
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
            },
            "createTime": {
                "type": "string",
                "description": "time",
                "format": "date-time"
            }
        }
    }
}
```

## how to use

`python Protobuf2Swagger.py`

## tips
`protobuf` do not support `Date`  
so I add a type `date`, you can use like this 

```
date createTime =1; //create time
```

the result after convert is  
```
"createTime": {
    "type": "string",
    "description": "time",
    "format": "date-time"
}
```

