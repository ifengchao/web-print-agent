# web打印代理
## 简介
一款静默打印代理工具，通过建立Socket服务，接收打印指令，通过解析打印指令完成打印。
## 功能描述

### 系统功能
* 最小化到状态栏
* 单实例
* 设置默认打印机
* 保留异常日志
* 保留打印日志

### 打印功能
* 自定义纸张大小
* 手动分页
* 打印条形码，二维码
* 打印图片

## 指令示例
使用JSON格式
类型：text/qrcoe/barcode/line
单位：毫米
web->代理
```
{
  "id":1537148688,
  "page":{
      "width":210,
      "height":297
  },
  "content":
  [
    {
      "type":"text",
      "text":"打印的内容",
      "size":20,
      "x":40,
      "y":5
    },
    {
      "type":"line",
      "x1":1,
      "y1":1,
      "x2":1,
      "y2":5
    },
    {
      "type":"qrcode",
      "text":"打印的内容",
      "width":70,
      "height":70,
      "x":55,
      "y":15
    }
  ]
}
```
代理->web
```
{
  id:1537148688,
  status:0,//0成功，1失败
  msg:"返回的消息"
}
```

## 注意
有几个依赖来自于本人自己的NuGet服务，需要的请留言。