# 闲鱼 Loon 去广告插件（抓包精准版）

基于用户提供的 257 条 HAR 请求分析制作。仅拦截抓包中观察到的广告相关请求，避免大范围封锁淘宝视频 CDN。

## 安装

Loon → 插件 → 添加远程插件，粘贴：

`https://raw.githubusercontent.com/bongnod/xianyuads-loon/main/XianyuAds.plugin`

启用插件后重启闲鱼进行测试。若仓库默认分支不是 `main`，请调整 URL。

## 已覆盖

- `cloud.video.taobao.com/play/` 中 `sBizCode=alimama_tuijian` 的广告视频请求
- `ef-dongfeng.tanx.com` 广告请求
- `bdlog.tanx.com` 广告曝光上报
- `ipm.atm.youku.com` 广告相关请求

## 注意

- 这不是完整的首页信息流广告过滤：HAR 未包含可供验证的首页商品列表 JSON 响应。
- 不拦截 `video.goofish.com`、`tbm-auth.alicdn.com` 等普通视频 CDN。
- 如果 Loon 当前版本不支持 `[Rule]` 中 `URL-REGEX`，请反馈插件日志，以便改成适配规则。
- 不要把原始 HAR 上传到公开 GitHub 仓库；其中可能含有令牌、请求参数等敏感数据。
