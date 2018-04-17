## 内容块发布编辑参数说明

### 文章及图集

> ```
>   {
>   "type": "object",
>   "properties": {
>     "title": {
>       "description": "标题"
>       "type": "string"
>     },
>     "description": {
>       "description": "描述",
>       "type": "string"
>     },
>     "mainContent": {
>       "description":"主内容",
>       "type": "array",
>       "items": [
>         {
>           "type": "object",
>           "properties": {
>             "type": {
>               "description": "主内容的类型（image,text,video,geo,option）",
>               "type": "string"
>             },
>             "title": {
>               "description": "标题(option时，选项的标题放在这里)",
>               "type": "string"
>             },
>             "description": {
>               "description": "描述（当type为image时可能出现，对于图片的描述）",
>               "type": "string"
>             },
>             "matter": {
>               "description": "内含物",
>               "type": "string"
>             },
>             "additionProps": {
>               "description": "附加参数 Map<String,Object>，
>                               type=geo时，包含key：lat，lng;
>                               type=video,包含key: cover;
>                               type=option,包含key: votingType（单选-single,多选-multi），deadline-截至时间（long型时间戳）",
>               "type": "object"
>             }
>           }
>         }
>       ]
>     },
>     "extendContents": {
>       "description": "扩展列表",
>       "type": "array",
>       "items": [
>         {
>           "type": "object",
>           "properties": {
>             "type": {
>               "description": "扩展类型（servant,product)",
>               "type": "string"
>             },
>             "matters": {
>               "description": "内含物",
>               "type": "array",
>               "items": [
>                 {
>                   "description": "商品或服务的ID",
>                   "type": "string"
>                 }
>               ]
>             }
>           }
>         }
>       ]
>     },
>     "detailContent": {
>       "description": "新的html",
>       "type": "string"
>     },
>     "originalContent": {
>       "description": "原始html",
>       "type": "string"
>     }
>   }
> }
> ```

## 内容详情参数

### 文章及图集

> ```
> {
>   "type": "object",
>   "properties": {
>     "title": {
>       "description": "标题",
>       "type": "string"
>     },
>     "embedded": {
>       "description": "是否有嵌入",
>       "type": "boolean"
>     },
>     "detailContent": {
>       "description": "新的html",
>       "type": "string"
>     },
>     "productExtendContent": {
>       "description": "商品扩展",
>       "type": "object",
>       "properties": {
>         "type": {
>           "description": "扩展类型（product,servant）",
>           "type": "string"
>         },
>         "matters": {
>           "type": "array",
>           "items": [
>             {
>               "description": "商品信息",
>               "type": "string"
>             }
>           ]
>         }
>       }
>     },
>     "servantExtendContent": {
>       "description": "",
>       "type": "object",
>       "properties": {
>         "type": {
>           "description": "扩展类型（product,servant）",
>           "type": "string"
>         },
>         "matters": {
>           "type": "array",
>           "items": [
>             {
>               "description": "服务信息",
>               "type": "string"
>             }
>           ]
>         }
>       }
>     }
>   }
> }
> ```

## 内容块预览参数

### 文章及图集

> ```
>     title：标题
>     description：描述
>     templateType：模板类型
>     styleType：样式类型
>     embedded: 是否嵌入（true,false）
>     link：内容块点击跳转
>         route：路由规则
>         options：路由选项
>            urlString：路由地址
>            shareInfo：分享信息
>              title: 分享标题
>              desc: 分享描述
>              thumbnail: 分享缩略图
>            reportInfo: 举报信息
>              reportType：举报目标类型
>              reportTargetId：举报目标ID
>     textContent：文本内容
>         [
>         type：文本内容的类型（text）
>         matter：内含的物质
>         title：标题
>         description：描述（当type为image时可能出现，对于图片的描述）
>         ]
>     mediaContent：媒体内容（图片，视频或地图）
>         [
>         type：媒体内容的类型（image,video,geo）
>         matter：内含的物质
>         title：标题
>         description：描述（当type为image时可能出现，对于图片的描述）
>         additionProps：附加参数Map<String,Object> （地图用到： lat,lng两个参数，值为double; 视频用到cover，作为视频截图，值为string）
>         ]
>     extendContents：扩展列表  
>          [  
>          type：扩展类型（servant,product)  
>          matters: 服务或商品列表（json数组）
>            类型为服务
>                    [
>                      id:
>                      icon:
>                      title:
>                    ]
>             类型为商品
>                    [
>                      id:
>                      name:
>                      picture:
>                      price:
>                      store:
>                      url:
>                     ]
>          ] 
>     actionLayouts：操作按钮布局列表
>         [
>         type：动作类型（link , servant）
>         name：名称
>         title：来源标题
>         icon：来源图标
>         style：样式
>         link：点击链接去向（type为link时）
>            route：路由规则
>            options：路由选项
>               urlString：路由地址
>         ]
>         
>         
>
>         
> {
>   "type": "object",
>   "properties": {
>     "title": {
>       "description": "",
>       "type": "string"
>     },
>     "description": {
>       "description": "",
>       "type": "null"
>     },
>     "templateType": {
>       "description": "",
>       "type": "string"
>     },
>     "styleType": {
>       "description": "",
>       "type": "string"
>     },
>     "embedded": {
>       "description": "",
>       "type": "boolean"
>     },
>     "link": {
>       "description": "",
>       "type": "object",
>       "properties": {
>         "route": {
>           "description": "",
>           "type": "string"
>         },
>         "options": {
>           "description": "",
>           "type": "object",
>           "properties": {
>             "urlString": {
>               "type": "string"
>             },
>             "shareInfo": {
>               "description": "",
>               "type": "object",
>               "properties": {
>                 "title": {
>                   "description": "",
>                   "type": "string"
>                 },
>                 "desc": {
>                   "description": "",
>                   "type": "string"
>                 },
>                 "thumbnail": {
>                   "description": "",
>                   "type": "string"
>                 },
>                 "url": {
>                   "description": "",
>                   "type": "null"
>                 }
>               }
>             },
>             "reportInfo": {
>               "description": "",
>               "type": "object",
>               "properties": {
>                 "reportType": {
>                   "description": "",
>                   "type": "string"
>                 },
>                 "reportTargetId": {
>                   "description": "",
>                   "type": "string"
>                 }
>               }
>             },
>             "sceneAccountId": {
>               "description": "",
>               "type": "null"
>             }
>           }
>         }
>       }
>     },
>     "textContent": {
>       "description": "",
>       "type": "array",
>       "items": {
>         "type": "object",
>         "properties": {
>           "type": {
>             "description": "",
>             "type": "string"
>           },
>           "title": {
>             "description": "",
>             "type": "null"
>           },
>           "description": {
>             "description": "",
>             "type": "null"
>           },
>           "matter": {
>             "description": "",
>             "type": "string"
>           },
>           "additionProps": {
>             "description": "",
>             "type": "object"
>           }
>         }
>       }
>     },
>     "mediaContent": {
>       "description": "",
>       "type": "array",
>       "items": {
>         "type": "object",
>         "properties": {
>           "type": {
>             "type": "string"
>           },
>           "title": {
>             "type": "string"
>           },
>           "description": {
>             "type": "null"
>           },
>           "matter": {
>             "type": "string"
>           },
>           "additionProps": {
>             "type": "object"
>           }
>         }
>       }
>     },
>     "extendContents": {
>       "description": "",
>       "type": "array",
>       "items": {
>         "type": "object",
>         "properties": {
>           "type": {
>             "type": "string"
>           },
>           "matters": {
>             "type": "array",
>             "items": {
>               "description": "",
>               "type": "string"
>             }
>           }
>         }
>       }
>     },
>     "actionLayouts": {
>       "type": "array",
>       "items": {
>         "type": "object",
>         "properties": {
>           "type": {
>             "description": "",
>             "type": "string"
>           },
>           "name": {
>             "description": "",
>             "type": "null"
>           },
>           "title": {
>             "description": "",
>             "type": "string"
>           },
>           "icon": {
>             "description": "",
>             "type": "string"
>           },
>           "style": {
>             "description": "",
>             "type": "string"
>           },
>           "link": {
>             "type": "object",
>             "properties": {
>               "route": {
>                 "type": "string"
>               },
>               "options": {
>                 "type": "object",
>                 "properties": {
>                   "urlString": {
>                     "description": "",
>                     "type": "null"
>                   },
>                   "shareInfo": {
>                     "description": "",
>                     "type": "null"
>                   },
>                   "reportInfo": {
>                     "description": "",
>                     "type": "null"
>                   },
>                   "sceneAccountId": {
>                     "description": "",
>                     "type": "string"
>                   }
>                 }
>               }
>             }
>           }
>         }
>       }
>     }
>   }
> }
> ```



