---
categories: 
- 编程开发
tags:
- PHP

---

#### go 语言生成100以内的随机数

```
rand.Seed(time.Now().UnixNano())

Tmep:=rand.Intn(100)
```

#### go 生成15-100内的随机数

```
rand.Seed(time.Now().UnixNano())

Tmep:=rand.Intn(76)+15
```

生成范围区间内的随机数(n,m)

```
rand.Seed(time.Now().UnixNano())
Tmep:=rand.Intn(m-n)+n //比如 Tmep:=rand.Intn(100-15+1)+15
```



