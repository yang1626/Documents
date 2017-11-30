# 请求：添加Leadership 结果
+ 请求地址：`Quiz/LeaderOrFollowerResult`
- 请求方式：PSOT
* 参数：
---
```json
	{
		msg:String,
		data:
	    {
	        id: Number,
	        name: String,
	        month: Array<String>,
	        categoryStats:
			[
				id:Number,
				name:String,
				count：Number
			],
	        articles:
			[
				id:Number,
				month:String
				cover:String,
				title:String,
				summary:String,
				date:DateTime
			]
	    }
	}