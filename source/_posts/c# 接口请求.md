---
categories: 
- 编程开发
tags:
- C#
---

C# Http请求接口数据

<!--more-->

### get

```c#
using (var httpClient = new HttpClient ()) {
    //get
    var url = new Uri ("接口网络地址");
    // response
    var response = httpClient.GetAsync (url).Result;
    var data = response.Content.ReadAsStringAsync ().Result;
    return data; //接口调用成功获取的数据
}
```

### post

```c#
using (var httpClient = new HttpClient ()) {
    //post
    var url = new Uri ("接口网络地址");
    var body = new FormUrlEncodedContent (new Dictionary<string, string> { { "参数1", "值1" },
        { "参数2", "值2" },
        { "参数3", "值3" },
        { "参数4", "值4" },
    });
    // response
    var response = httpClient.PostAsync (url, body).Result;
    var data = response.Content.ReadAsStringAsync ().Result;
    return data; //接口调用成功数据
}
```

### 设置header

```c#
httpClient.DefaultRequestHeaders.Add("Accept", "application/json");//设置请求头
```

