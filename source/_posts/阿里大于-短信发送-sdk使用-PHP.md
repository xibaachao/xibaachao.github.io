---
categories: 
- 编程开发
tags:
- PHP
---

#### 安装sdk

```
composer require alibabacloud/client
```

#### 封装方法

```php
function sendphone($code,$phone){
        AlibabaCloud::accessKeyClient('AccessKeyId', 'AccessKeySecret')->regionId('cn-hangzhou')->asDefaultClient();
        $result = AlibabaCloud::rpc()
            ->product('Dysmsapi')
            ->version('2017-05-25')
            ->action('SendSms')
            ->method('POST')
            ->host('dysmsapi.aliyuncs.com')
            ->options([
                'query' => [
                    'PhoneNumbers' => $phone,
                    'SignName' => "签名",
                    'TemplateCode' => "模板id",
                    'TemplateParam'=>'{"code":"'.$code.'"}'
                ],
            ])
            ->request();
        return $result;
    }
```

#### 其他帮助

[官方SDK_DEMO](https://help.aliyun.com/document_detail/55359.html?spm=a2c4g.11186623.4.5.553a4e6aUAAElB)

[官方调试工具](https://api.aliyun.com/new?spm=a2c4g.11186623.2.13.667619d9f8wHAh#/?product=Dysmsapi&version=2017-05-25&api=SendSms&params={}&tab=DEMO&lang=PHP)



本文更新，切正常使用时间 2020-1-1