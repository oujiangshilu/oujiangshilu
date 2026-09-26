# 瓯江诗路 · 文学景观互动地图

温州楠溪江与丽水瓯江上游文学景观互动展示原型：手绘风格地图 + 诗词 + 文旅信息（美食 / 特产 / 非遗 / 景点）。

## 在浏览器直接打开

双击 `index.html` 即可在本地浏览器查看，无需安装任何环境。

## 部署到 GitHub Pages（免费，有独立网址）

1. 在 GitHub 上新建一个仓库，例如 `oujiang-shilu`。
2. 把本文件夹里的 `index.html`（以及 `images` 文件夹等素材）上传到仓库根目录，提交（commit）。
3. 进入仓库的 **Settings → Pages**。
4. 在 "Build and deployment" 里，Source 选择 **Deploy from a branch**，Branch 选择 `main`（或你的默认分支）、目录选择 `/ (root)`，保存。
5. 稍等一两分钟，页面顶部会出现发布好的网址，形如：
   `https://<你的GitHub用户名>.github.io/oujiang-shilu/`
   这个网址可以直接在浏览器打开、分享给别人。

之后每次修改 `index.html` 并 push 到仓库，GitHub Pages 会自动重新发布，一般一两分钟内生效。

## 如何修改内容（给团队所有人看）

打开 `index.html`，搜索 `SITE_DATA` —— 这是全站唯一的数据来源，一个点位对应一个对象：

```js
{
  id:"jiangxinyu", name:"江心屿", region:"温州", type:"山水胜景类 · 中国诗之岛",
  x:74, y:30,              // 在地图上的百分比坐标
  status:"detailed",       // "detailed" 已收录 / "draft" 待补充
  summary:"……",            // 点位简介
  poems:[ { title:"……", author:"……", dynasty:"……", lines:["……","……"], note:"……" } ],
  food:[ {name:"……", desc:"……"} ],
  specialty:[ ... ],
  heritage:[ ... ],
  sights:[ ... ]
}
```

- 新增一个点位：复制上面这样一个对象，粘贴进 `SITE_DATA` 数组，改内容和坐标即可。
- 补充某个点位的诗词 / 美食 / 特产 / 非遗 / 景点：直接往对应数组里加对象。
- 坐标 `x`、`y` 是百分比（0-100），对着地图预览大致调整几次即可对准位置。
- 每首诗词卡片下方留了一个"古今实景照片对照"占位框，之后有照片了，可以在对应 `poem` 对象里加一个 `photo` 字段并在渲染函数里接入 `<img>`，我们可以再来协助接入。

## 地图底图

首页地图现已换成实景手绘地图图片（`images/map-illustration.jpg`），各点位的印记标记叠加在图片上。上传到 GitHub 时务必把 `images` 文件夹和 `index.html` 放在同一层目录，否则图片会显示不出来。

## 待完善事项

- 江心屿、枫林镇、鹤阳村、蓬溪村四个点位的诗词已收录；古堰画乡、仙都-河阳古民居、下樟·岩后村三个点位的诗词与文旅信息仍待补充，结构已就绪。
- 实景/古今照片对照功能：占位已留好，等素材到位后可接入。
