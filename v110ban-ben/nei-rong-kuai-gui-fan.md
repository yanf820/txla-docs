## 内容块发布编辑参数说明

### 文章及图集

> ```
>     title：标题  
>     description：描述  
>     mainContent：主内容  
>         [  
>         type：主内容的类型（image,text,video,geo）  
>         matter：内含的物质
>         title：标题  
>         description：描述（当type为image时可能出现，对于图片的描述）  
>         additionProps：附加参数 Map<String,Object>
>         ]  
>     extendContents：扩展列表  
>          [  
>          type：扩展类型（servant,product)  
>          matters: 商品或服务的ID列表json  
>          ]
>     detailContent: string（全部html代码）
>     
>     
>     
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
> title：标题
> detailContent:string（全部html代码）
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
> ```



