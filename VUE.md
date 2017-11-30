# vue cli 服务器代理:proxyTable
**配置项与请求是url前缀必须一致（大小写）**
```  proxyTable: {
      '/api': {
        target: 'http://localhost:8060',
        changeOrigin: true
        // pathRewrite: {
        //    '^/api': '/api'
        // }
      }
    }
```
```
this.$http.get('api/Questionnaire/SubjectPartitionTag')
      .then(res => {
        this.levelReason = res.data.slice().map(function (item) { return {text: item.name, id: item.id, type: item.type} })
        this.getSubjects()
      }).catch(e => {
        console.log(e)
        // this.$http.getData()
      })
 ```     
 **两个‘api’必须一致**