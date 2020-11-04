# pass协议

### passInfo:/app/pass/info
获取pass信息
```
req:
rep:
   number: int #季赛编号
   endTime: int #结束时间
   isVip: int #是否vip 如果是vip开启rewards second的奖励
   level: int #等级
   exp: int #经验 当大于100级时 这个可以用作购买pass商店物品
   uplevelExp: int #升级所需经验
   buyVipInfo: map
      first: map
         oldPrice: int #老的价格
         price: int #当前价
      second: map
         oldPrice: int #老的价格
         price: int #当前价
   rewards:map #可以领取的奖励集合
      level:int
      first:bool
      second:bool
   dayTasks:array
      id: int #任务编号
      rate: int #进度
err:
```

### passBuyVip:/app/pass/buyVip
购买VIP
```
req:
   type:int # 1:first 2:second
rep:
err:
```

### passBuyShop:/app/pass/buyShop
购买商品
```
req:
   id: int #商品id
rep:
err:
```
