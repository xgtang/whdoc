# DailyTask 每日任务

### dailyTaskInfo:/app/dailyTask/info
每日任务信息
```
req:
   lastTime: int #最后结束时间戳毫秒
   weekPoints: int #当前周任务点数
   tasks:map
      id:int #任务id
      total: int #任务完成次数
      rate:int #任务进度
      points:int #获得点数
      state:int #1未完成 2已完成 3已领取
   dayBuffer:array[]map
      id:int #buffId
      state:int #1未完成 2已完成 3已领取
   
rep:
err:
```
