## 内容块发布编辑参数说明

### 文章及图集

> ```
>     title：标题  
>     description：描述  
>     mainContent：主内容  
>         [  
>         type：主内容的类型（image,text）  
>         matter：内含的物质（type为image时->图片url，为text时->本文内容）
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



