# 自动刷新房源并发送可租房源到邮件(已失效)

>现在网站每次查询房源都要输入验证码，所以代码暂时不能使用了。

使用教程也可以看我的博客 http://www.cnblogs.com/zhouyangla/p/7402341.html 

![预览图](http://opgxmtsvs.bkt.clouddn.com/934644-20170818173029459-369460812.png)
![预览图](http://opgxmtsvs.bkt.clouddn.com/934644-20170818173212006-1642455094.png)

## 一.安装
1.本地安装node.js。 node.js安装教程(http://jingyan.baidu.com/article/fd8044faf2e8af5030137a64.html)

2.clone代码到本地，在该项目根目录运行
``` npm install ```

3.修改app.js中的邮箱地址
```
 let transporter = nodemailer.createTransport({
        host: 'smtp.163.com',
        secureConnection: true, // use SSL
        port: 465,
        secure: true, // secure:true for port 465, secure:false for port 587
        auth: {
            user: 'xxx@163.com',  //这里替换成你自己的163邮箱。
            pass: 'xxxxxx' // 这里输入你的邮箱授权码 
        }
    });
    
 ```
 设置收件邮箱地址
 
 ```
  // 设置邮件内容（谁发送什么给谁）
    let mailOptions = {
        from: '"xxx" <xxx@163.com>', // 发件人
        to: 'xxx@126.com', // 收件人
        subject: `Hello ✔有可入住的房源啦`, // 主题
        text: 'search house', // plain text body
        html: `<b style="font-size:18px;">已为你搜到可入住的房源啦</b>
        
 ```


## 二.运行

在终端输入

``` node app.js ```
