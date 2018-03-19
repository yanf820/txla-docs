## 内容块发布编辑参数说明

### 文章及图集

> ```
>     title：标题  
>     description：描述  
>     mainContent：主内容  
>         [  
>         type：主内容的类型（image,text）  
>         matter：内含的物质
>         title：标题  
>         description：描述（当type为image时可能出现，对于图片的描述）  
>         ]  
>     extends：扩展列表  
>          [  
>          type：扩展类型（servant,product)  
>          ids: 商品或服务的ID列表，图片或视频的url列表 string[]  
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
>     link：内容块点击跳转
>         route：路由规则
>         options：路由选项
>            urlString：路由地址
>     textContent：文本内容
>         [
>         type：主内容的类型（image,text,video,geo）
>         matter：内含的物质
>         title：标题
>         description：描述（当type为image时可能出现，对于图片的描述）
>         ]
>     imageContent：图片内容
>         [
>         type：主内容的类型（image,text,video,geo）
>         matter：内含的物质
>         title：标题
>         description：描述（当type为image时可能出现，对于图片的描述）
>         ]
>     videoContent: 视频内容
>         [
>         type：主内容的类型（image,text,video,geo）
>         matter：内含的物质
>         title：标题
>         description：描述（当type为image时可能出现，对于图片的描述）
>         ]
>     extends：扩展列表  
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



