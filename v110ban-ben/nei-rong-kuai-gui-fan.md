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
>  {
>   "type": "object",
>   "properties": {
>     "title": {
>       "type": "string",
>       "title": "The Title Schema ",
>       "default": "",
>       "examples": [
>         "天下大势男生款"
>       ]
>     },
>     "description": {
>       "type": "string",
>       "title": "The Description Schema ",
>       "default": null,
>       "examples": [
>         null
>       ]
>     },
>     "templateType": {
>       "type": "string",
>       "title": "The Templatetype Schema ",
>       "default": "",
>       "examples": [
>         "map"
>       ]
>     },
>     "styleType": {
>       "type": "string",
>       "title": "The Styletype Schema ",
>       "default": "",
>       "examples": [
>         "m-default"
>       ]
>     },
>     "embedded": {
>       "type": "boolean",
>       "title": "The Embedded Schema ",
>       "default": false,
>       "examples": [
>         true
>       ]
>     },
>     "link": {
>       "type": "object",
>       "properties": {
>         "route": {
>           "type": "string",
>           "title": "The Route Schema ",
>           "default": "",
>           "examples": [
>             "H5"
>           ]
>         },
>         "options": {
>           "type": "object",
>           "properties": {
>             "urlString": {
>               "type": "string",
>               "title": "The Urlstring Schema ",
>               "default": "",
>               "examples": [
>                 "http://scence-page.tianxialashou.com.cn/#/articleShow?contentId=84417589b62d4808&sceneAccountId=b8cfc74c1b224765&contentShowType=article"
>               ]
>             },
>             "shareInfo": {
>               "type": "object",
>               "properties": {
>                 "title": {
>                   "type": "string",
>                   "title": "The Title Schema ",
>                   "default": "",
>                   "examples": [
>                     "天下大势男生款"
>                   ]
>                 },
>                 "desc": {
>                   "type": "string",
>                   "title": "The Desc Schema ",
>                   "default": "",
>                   "examples": [
>                     "我们自己|\\n 创建于 04-16 13:42"
>                   ]
>                 },
>                 "thumbnail": {
>                   "type": "string",
>                   "title": "The Thumbnail Schema ",
>                   "default": "",
>                   "examples": [
>                     "http://img1.lashouimg.com/txls/M00/00/09/CqgBTVppvHmAcTLbAABbTESAGfw651.png"
>                   ]
>                 },
>                 "url": {
>                   "type": "null",
>                   "title": "The Url Schema ",
>                   "default": null,
>                   "examples": [
>                     null
>                   ]
>                 }
>               }
>             },
>             "reportInfo": {
>               "type": "object",
>               "properties": {
>                 "reportType": {
>                   "type": "string",
>                   "title": "The Reporttype Schema ",
>                   "default": "",
>                   "examples": [
>                     "block"
>                   ]
>                 },
>                 "reportTargetId": {
>                   "type": "string",
>                   "title": "The Reporttargetid Schema ",
>                   "default": "",
>                   "examples": [
>                     "84417589b62d4808"
>                   ]
>                 }
>               }
>             },
>             "sceneAccountId": {
>               "type": "string",
>               "title": "The Sceneaccountid Schema ",
>               "default": null,
>               "examples": [
>                 null
>               ]
>             }
>           }
>         }
>       }
>     },
>     "textContent": {
>       "type": "array",
>       "items": {
>         "type": "object",
>         "properties": {
>           "type": {
>             "type": "string",
>             "title": "The Type Schema ",
>             "default": "",
>             "examples": [
>               "text"
>             ]
>           },
>           "title": {
>             "type": "null",
>             "title": "The Title Schema ",
>             "default": null,
>             "examples": [
>               null
>             ]
>           },
>           "description": {
>             "type": "null",
>             "title": "The Description Schema ",
>             "default": null,
>             "examples": [
>               null
>             ]
>           },
>           "matter": {
>             "type": "string",
>             "title": "The Matter Schema ",
>             "default": "",
>             "examples": [
>               "我要把它放在我心里是的哈斯哈哈哈哈？哈哈哈我要的东西吃饭风风光光更发达地区挂职副主任？哈哈哈我也我要把自己弄丢饿饿饿饿饿哒？哈哈哈哈哈，我哈哈哈哈哈，我要去买菜了！哈哈哈我自己了！哈哈哈哈哈。哈哈哈哈哈。哈哈哈我要的生活"
>             ]
>           },
>           "additionProps": {
>             "type": "object"
>           }
>         }
>       }
>     },
>     "mediaContent": {
>       "type": "array",
>       "items": {
>         "type": "object",
>         "properties": {
>           "type": {
>             "type": "string",
>             "title": "The Type Schema ",
>             "default": "",
>             "examples": [
>               "geo"
>             ]
>           },
>           "title": {
>             "type": "string",
>             "title": "The Title Schema ",
>             "default": "",
>             "examples": [
>               "来广营容和路1号院1号楼"
>             ]
>           },
>           "description": {
>             "type": "null",
>             "title": "The Description Schema ",
>             "default": null,
>             "examples": [
>               null
>             ]
>           },
>           "matter": {
>             "type": "string",
>             "title": "The Matter Schema ",
>             "default": "",
>             "examples": [
>               "http://txls-img.bj.bcebos.com/1523857262693.jpg"
>             ]
>           },
>           "additionProps": {
>             "type": "object",
>             "properties": {
>               "lng": {
>                 "type": "string",
>                 "title": "The Lng Schema ",
>                 "default": "",
>                 "examples": [
>                   "116.474814"
>                 ]
>               },
>               "lat": {
>                 "type": "string",
>                 "title": "The Lat Schema ",
>                 "default": "",
>                 "examples": [
>                   "40.021963"
>                 ]
>               }
>             }
>           }
>         }
>       }
>     },
>     "extendContents": {
>       "type": "array",
>       "items": {
>         "type": "object",
>         "properties": {
>           "type": {
>             "type": "string",
>             "title": "The Type Schema ",
>             "default": "",
>             "examples": [
>               "product"
>             ]
>           },
>           "matters": {
>             "type": "array",
>             "items": {
>               "type": "string",
>               "title": "The 0th Schema ",
>               "default": "",
>               "examples": [
>                 "{\"id\":\"350\",\"name\":\"法融调味瓶\",\"picture\":\"http://m1.lashouimg.com/mall/M00/00/C4/CqgBTFmVYOqAInpcAAjXU26xTlo978.png\",\"price\":136.0,\"storeName\":\"南京暇满文化发展有限公司•牛首山文创\",\"url\":\"http://shop.tianxialashou.com.cn/wap/tmpl/product_detail.html?goods_id=350\"}"
>               ]
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
>             "type": "string",
>             "title": "The Type Schema ",
>             "default": "",
>             "examples": [
>               "link"
>             ]
>           },
>           "name": {
>             "type": "null",
>             "title": "The Name Schema ",
>             "default": null,
>             "examples": [
>               null
>             ]
>           },
>           "title": {
>             "type": "string",
>             "title": "The Title Schema ",
>             "default": "",
>             "examples": [
>               "我们自己 · 天下拉手"
>             ]
>           },
>           "icon": {
>             "type": "string",
>             "title": "The Icon Schema ",
>             "default": "",
>             "examples": [
>               "http://img1.lashouimg.com/txls/M00/00/38/CqgBTVqgn12AdmwoAAAERqkmT38560.png"
>             ]
>           },
>           "style": {
>             "type": "string",
>             "title": "The Style Schema ",
>             "default": "",
>             "examples": [
>               "source"
>             ]
>           },
>           "link": {
>             "type": "object",
>             "properties": {
>               "route": {
>                 "type": "string",
>                 "title": "The Route Schema ",
>                 "default": "",
>                 "examples": [
>                   "LSSceneAccountHomePage"
>                 ]
>               },
>               "options": {
>                 "type": "object",
>                 "properties": {
>                   "urlString": {
>                     "type": "null",
>                     "title": "The Urlstring Schema ",
>                     "default": null,
>                     "examples": [
>                       null
>                     ]
>                   },
>                   "shareInfo": {
>                     "type": "null",
>                     "title": "The Shareinfo Schema ",
>                     "default": null,
>                     "examples": [
>                       null
>                     ]
>                   },
>                   "reportInfo": {
>                     "type": "null",
>                     "title": "The Reportinfo Schema ",
>                     "default": null,
>                     "examples": [
>                       null
>                     ]
>                   },
>                   "sceneAccountId": {
>                     "type": "string",
>                     "title": "The Sceneaccountid Schema ",
>                     "default": "",
>                     "examples": [
>                       "b8cfc74c1b224765"
>                     ]
>                   }
>                 }
>               }
>             }
>           }
>         }
>       }
>     },
>     "imageMediaContent": {
>       "type": "null",
>       "title": "The Imagemediacontent Schema ",
>       "default": null,
>       "examples": [
>         null
>       ]
>     }
>   }
> }                      
> ```



