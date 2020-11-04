# 邮件协议

### 邮件类型 MailType
* INBOX: 1

### 礼品类型 GiftType
* COIN: 1
* GEM: 2

### mailEdit:/app/mail/edit
修改邮件的个人信息
```
req:
   |nickname: string #名称
   |avatar: string #头像
rep:
err:
```

### mailList:/app/mail/list
邮件列表
```
req:
rep:array
   id:int #邮件id
   type: MailType #邮件类型
   gameId:int #游戏id
   isLock:boolean #是否加锁
   gifts: [{giftType:GiftType,num:int extend:json}] #礼品列表 extend根据giftType不同可能会有值
   time:int64 #时间戳
err:
```

### mailReceive:/app/mail/receive
领取邮件
```
req:
   id:int #邮件id
rep:
err:
```

### mailReceiveAll:/app/mail/receiceAll
领取所有邮件
```
req:
rep:
err:
```


### mailSendGifts:/app/mail/sendGifts
给好友送礼物
```
req:
   type:int #1金币 2卡片
   cardId: int #当type为2时需要发送此字段
   friend:string #好友id或者标志
rep:
err:
```

### mailProps:/app/mail/props
活动道具列表
```
req:
rep:array
   id:int #道具id
   number:int #道具数量
err:
```
