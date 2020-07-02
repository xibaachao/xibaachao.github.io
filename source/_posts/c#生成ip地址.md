---
categories: 
- 编程开发
tags:
- C#
---
#### 根据ip段批量生成ip地址

````c#
public List<IPAddress> makeip (string sip, string eip) {
    List<IPAddress> list = new List<IPAddress> ();
    uint iStartip = ipTint (sip);
    uint iEndIp = ipTint (eip);
    StringBuilder ip_result = new StringBuilder ();
    if (iEndIp >= iStartip) {
        for (uint ip = iStartip; ip <= iEndIp; ip++) {
            IPAddress iPAddress = IPAddress.Parse (intTip (ip));
            list.Add (iPAddress);
        }
    } else {
        return null;
    }
    return list;
}

public uint ipTint (string ipStr) {
    string[] ip = ipStr.Split ('.');
    uint ipcode = 0xFFFFFF00 | byte.Parse (ip[3]);
    ipcode = ipcode & 0xFFFF00FF | (uint.Parse (ip[2]) << 0x8);
    ipcode = ipcode & 0xFF00FFFF | (uint.Parse (ip[1]) << 0xF);
    ipcode = ipcode & 0x00FFFFFF | (uint.Parse (ip[0]) << 0x18);
    return ipcode;
}
public string intTip (uint ipcode) {
    byte a = (byte) ((ipcode & 0xFF000000) >> 0x18);
    byte b = (byte) ((ipcode & 0x00FF0000) >> 0xF);
    byte c = (byte) ((ipcode & 0x0000FF00) >> 0x8);
    byte d = (byte) (ipcode & 0x000000FF);
    string ipStr = string.Format ("{0}.{1}.{2}.{3}", a, b, c, d);
    return ipStr;
}
````

#### 生成随机ip

```c#
public static string ipsite () {
    Random sj = new Random ();
    var s = "";
    for (int i = 0; i <= 3; i++) {
        var q = sj.Next (0, 255).ToString ();
        if (i < 3) {
            s += (q + ".").ToString ();
        } else {
            s += q.ToString ();
        }
    }
    var zz = Regex.IsMatch (s, "^((25[0-5]|2[0-4]\\d|((1\\d{2})|([1-9]?\\d)))\\.){3}(25[0-5]|2[0-4]\\d|((1\\d{2})|([1-9]?\\d)))$");
    if (zz == true) {
        return s;
    } else {
        return "";
    }
}
```

