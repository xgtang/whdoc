# 大厅


# /app/config/gate
入口
```
req:
   channelID: int #渠道id
   subChannelID: int #子渠道
   appVersion: int #app版号
rep:
   apiKey: string
   resUrl: string
   resVersion: string
   aesKey: string
   serverUrl: string
   socketIp: string
   socketPort: int
   apilist:map
      "visitorLogin": "/app/register/visitorLogin", #游客登录
      "faceBookLogin": "/app/register/faceBookLogin",#fb登录
      "userInfo": "/app/user/info" #用户信息
      "games": "/app/hall/games" #游戏列表
err:
```

### visitorLogin:/app/register/visitorLogin
游客登录
```
req:
   device: string #设备
   deviceId: string #设备标识
   platform: string #客户端来源
   deviceVersion: string #设备版本
   appVersion: 客户端代码版本
rep:
   token: string
   playerId: int
err:
```

### userInfo:/app/user/info
用户信息
```
req:
rep:
   playerId: int
   userName: string
   coin: int
   gem: int
   level: int
   levelExp: float
   vipLevel: int
   vipExp: int
   lounge: int
   shopDealCountDown: int64
err:
```

### games:/app/hall/games
游戏列表
```
req:
rep:
   array[map]
      id: int
      name: string
      state: int #1:即将开放 2:维修中 3:new图标 4:hot图标 5:未解锁 6:super图标
      selectBets: [int64]
err:
```

### hallIcons:/app/hall/icons
大厅图标
```
req:
rep:
   array[map]
      id: int,
      mark: int, #未读数量
      name: string,
err:
```

### hallAdverts:/app/hall/adverts
广告
```
req:
rep:
   id: int,
   name: string,
   startTime: int64,
   endTime: int64,
   level: int,
   orderNo int
err:
```

### bindPlatformRewardList:/app/hall/bindPlatform/rewardList
绑定平台奖励信息
```
req:
rep:
   array[map]
      type:int #fb=1
      assetsType:int #资产类型
      number:int #数量
err:
```

### bindPlatform:/app/hall/bindPlatform
绑定平台
```
req:
   type:int #fb=1
   platformInfo:Json #平台信息
rep:
err:
```

### hallGameInfo:/app/hall/game
游戏信息
```
req:
    gameId: int,
rep:
	bets：#下注区间值
	name：#游戏名称
	id：#游戏id
err:
```

