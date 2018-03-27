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
>         additionProps：附加参数Map<String,Object>
>         ]
>     extendContents：扩展列表  
>          [  
>          type：扩展类型（servant,product)  
>          matters: 服务或商品列表（json数组）
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



