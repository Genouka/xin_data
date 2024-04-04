# 莘应用(自定义数据源)

这是制作莘应用自定义数据源的官方指导文档。

[莘应用官网](https://edsc.top/)

## 缘由
打造一款支持高度自定义、强稳定性的手表应用商店！

自莘应用1.4起开始支持自定义数据源！

## 快速创建
待研究，目前可以根据以下数据格式进行制作。

## 数据格式

### 创建分类表
`category.json`

以下是示例数据：
```json
{
  "categorylist": [
    {
      "name": "工具",
      "category": 1
    },
    {
      "name": "游戏",
      "category": 2
    }
  ]
}
```

### 创建应用列表
`applist.json`

以下是示例数据格式：
```json
{
  "applist": [
     {
      "name": "坚果天气",
      "url": "https://fel.forxhr.top:2022/down.php/b676a21d4d041b8b0e40ad1c9b767362.apk",
      "icon": "https://fel.forxhr.top:2022/view.php/ffc9bc9a46fa3d9a8d9df427463a153d.png",
      "version": "2.6",
      "author": "老豆荚团队",
      "description": "是由老豆荚应用分享团队开发的锤子天气第三方客户端原锤子天气官方外发版本现已停止服务为了让其他安卓用户能够继续体验到锤子天气我们开发了这款客户端",
      "cutphoto": "https://fel.forxhr.top:2022/view.php/aa05b2a24b189b469e107eb42e33cac3.png",
      "category": 6
    },
     {
      "name": "密匣",
      "url": "https://fel.forxhr.top:2022/down.php/0422180a72227a079b45cd1e1ffae54d.apk",
      "icon": "https://fel.forxhr.top:2022/view.php/ad58e5bcaea84a342bc784464ed8776c.jpg",
      "version": "1.0",
      "author": "小趣团队",
      "description": "通过悬浮窗权限覆盖手表UI退出锁定模式需要连续数次长按屏幕可用特定页面覆盖手表UI使手表无法进行操作从而应付各种场景",
      "cutphoto": "https://fel.forxhr.top:2022/view.php/2920ef46a7c8e4e4fcae0ed6f2772ed4.jpg",
      "category": 1
    },
    ...
  ]
}
```

## 高级指南
### 使用一个json囊括分类表和应用列表
符合下列格式即可：
```json
{
  "categorylist": [ ... ],
  "applist": [ ... ]
}
```
很简单，对吧。这个特性有利于你方便的发布单文件数据源！

