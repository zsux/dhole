
  GET /dev-rcm/task/_count

GET /dev-rcm/task/_search
{
  "query": {
    "terms": {
      "units": [
        58,
        32
      ]
    }
  },
  "_source": {
    "includes": [
      "taskId",
      "projectCode",
      "phaseCode",
      "productCode",
      "userId",
      "orderId",
      "name",
      "mobile",
      "idCard",
      "creditTotal",
      "currentOrderMoney",
      "isVIPUser",
      "userAge",
      "userFaceLinks",
      "taskStatus",
      "lastResult",
      "lastStatus",
      "rootUnitId",
      "rootUnitVerId",
      "tuid",
      "updateTime",
      "createTime"
    ]
  },
  "sort": [
    {
      "taskId": {
        "order": "desc"
      }
    }
  ]
}
DELETE /dev-rcm
GET /dev-rcm/task/38584 
GET /dev-rcm/task/_mapping

PUT /dev-rcm
{
  "settings": {
     "number_of_shards": 5
  }
}

PUT /dev-rcm/_mapping/task
{
  "properties": {
    "createTime": {
      "type": "date",
      "format": "yyyy-MM-dd HH:mm:ss"
    },
    "creditTotal": {
      "type": "long"
    },
    "currentOrderMoney": {
      "type": "long"
    },
    "idCard": {
      "type": "keyword"
    },
    "isVIPUser": {
      "type": "byte"
    },
    "lastBackCode": {
      "type": "keyword"
    },
    "lastHeadCode": {
      "type": "keyword"
    },
    "lastResult": {
      "type": "long"
    },
    "lastStatus": {
      "type": "keyword"
    },
    "lastUnitId": {
      "type": "long"
    },
    "mobile": {
      "type": "keyword"
    },
    "name": {
      "type": "keyword"
    },
    "orderId": {
      "type": "long"
    },
    "phaseCode": {
      "type": "keyword"
    },
    "productCode": {
      "type": "keyword"
    },
    "projectCode": {
      "type": "keyword"
    },
    "rootUnitId": {
      "type": "long"
    },
    "rootUnitVerId": {
      "type": "long"
    },
    "taskId": {
      "type": "long"
    },
    "taskStatus": {
      "type": "keyword"
    },
    "tuid": {
      "type": "keyword"
    },
    "updateTime": {
      "type": "date",
      "format": "yyyy-MM-dd HH:mm:ss"
    },
    "avatar": {
        "type":     "keyword"
    },
    "userId": {
      "type": "long"
    },
    "units": {
      "type": "text"
    },
    "codes": {
      "type": "text"
    },
    "unitCodes": {
      "type": "text"
    }
  }
}


GET /dev-rcm/task/_search
{
  "query": {
    "terms":{
      "projectCode":["XJX","JSQB"]
    }
  },
  "_source": {
    "includes": [
      "taskId",
      "projectCode",
      "phaseCode",
      "avatar"
    ]
  },
  "sort": [
    {
      "taskId": {
        "order": "desc"
      }
    }
  ]
}
