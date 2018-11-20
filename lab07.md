## 游戏策划

这是一个60秒的生存小游戏，在这段时间内，底部额炮台会不断发射炮弹，且这些弹药会不断追踪玩家，玩家可以通过收集黄色球来获取分数和生命值，撑过这60秒就赢了。

## 游戏设计

| Object：玩家       |          | |
|:-------------|:------------------|:------|
| Attribute：图片，帧动画，位置 |
| Collaborator：精灵 | Event & Actions：钉住 & 动画的切换 |   |



| Object：玩家       |        ||
|:-------------|:------------------|:------|
|Attributes：图片，位置  |
|Collaborator | Events & Actions         |
|       精灵   | 跳跃 & 自由落体 & 左右移动 |



| Object Name：机关  |
|:-------------|:------------------|:------|
| Attributes：图片 & 位置       |
| Collaborator  Events & Actions |

| Object Name：炮弹    |
|:-------------|:------------------|:------|
| Attributes：图片 & 位置 :追踪玩家      |
| Collaborator  Events & Actions |
|  精灵  碰撞 & 销毁自己 |

| Object Name：地板 & 墙壁         |  
|---------------------------------|
| Attributes：图片 & 位置          |
| Collaborator Events & Actions |
|   精灵     实心固体   

![](images\沙雕1.gif)

![](images\沙雕2.gif)