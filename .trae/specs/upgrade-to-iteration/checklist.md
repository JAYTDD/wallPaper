# Checklist

## 全局配置与样式
- [ ] manifest.json 已替换为迭代版（Vue3、appid、多平台、H5 router base /xxmwall/）
- [ ] pages.json 已替换为迭代版（首页/分类/专题/我的 tabBar + 分类列表/预览/公告/搜索 + subPackages 排行榜/近期上新）
- [ ] App.vue 引入 `@import 'common/style/common-style.scss'` 全局样式
- [ ] common/style/base-style.scss 存在且包含品牌色变量 `$brand-theme-color`
- [ ] common/style/common-style.scss 存在且包含 `.pageBg`、`.loadingLayout`、`.safe-area-inset-bottom`
- [ ] uni.scss 正确引入 `@import "@/common/style/base-style.scss"`

## 工具函数与 API
- [ ] api/apis.js 包含全部接口：banner、randomWall、notice、classify、wallList、setupScore、downloadWall、detailWall、userInfo、userWallList、noticeDetail、searchWall、subjectList、subjectDetail、uptodate、rank
- [ ] utils/request.js 封装 Promise，统一处理 errCode 0/400/其他，含 Toast/Modal 提示
- [ ] utils/system.js 提供 `getStatusBarHeight`、`getTitleBarHeight`、`getNavBarHeight`、`getLeftIconLeft`
- [ ] utils/layout.js 提供 `getStatusBarHeight`、`getTitleBarHeight`、`getNavBarHeight`、`getTabBarHeight`、`getSafeAreaHeight`、`getBottomHeight`、`toHeightStyle`、`getMpMenuRect`
- [ ] utils/common.js 提供 `compareTimestamp`、`gotoHome`、`routerTo`、`goBack`、`showToast`
- [ ] utils/tools.js 提供 `formatUpdateTime`、`addLeadingZero`、`formatNumber`、`getDateRange`

## 组件
- [ ] components/custom-nav-bar/custom-nav-bar.vue 使用 system.js 计算导航栏高度，含搜索入口与渐变背景
- [ ] components/common-title/common-title.vue 支持 `#name` 与 `#custom` 两个 slot
- [ ] components/picture-item/picture-item.vue 接收 `item` 与 `classList`，点击跳转 preview 并写入 storage
- [ ] components/theme-item/theme-item.vue 支持 `isMore` 模式，显示更新时间与更多入口
- [ ] components/subject-item/subject-item.vue 实现旋转拼图预览效果，展示标题/浏览数/数量

## 页面
- [ ] pages/index/index.vue 包含 Banner、公告轮播、快捷入口（排行榜/近期上新）、每日推荐、分类精选、专题推荐、骨架屏、分享
- [ ] pages/classify/classify.vue（或 classfiy）使用 theme-item 展示分类 grid，支持分享
- [ ] pages/classlist/classlist.vue 存在，支持触底加载、loading、noMore、分享参数、缓存清理
- [ ] pages/preview/preview.vue 支持 swiper 预览、遮罩切换、信息/评分/下载弹窗、分享进入加载、预加载策略、返回兜底
- [ ] pages/user/user.vue 展示用户 IP/地址、下载/评分数量、联系客服（条件编译）、订阅更新/常见问题入口
- [ ] pages/subject/subject.vue 专题列表，支持分页加载、分享
- [ ] pages/subject/detail.vue 专题详情，头图毛玻璃背景、壁纸网格
- [ ] pages/search/search.vue 搜索页，含历史记录、热门推荐、搜索结果 grid、触底加载
- [ ] pages/notice/notice.vue 公告列表
- [ ] pages/notice/detail.vue 公告富文本详情，使用 mp-html 渲染
- [ ] pages_quick/ranking.vue 排行榜，支持日期范围选择、Tabs 切换、进度条、骨架屏、分享
- [ ] pages_quick/news.vue 近期上新，支持广告位插入（条件编译）、触底加载、骨架屏、分享

## uni_modules 与静态资源
- [ ] uni_modules 包含 mp-html、uni-search-bar、uni-load-more、uni-tag、uni-datetime-picker、uv-empty、uv-icon、uv-link、uv-skeletons、uv-text、uv-ui-tools
- [ ] static/images/tabBar 包含 home/classify/geng/user 的默认与高亮图标
- [ ] static/images/logo2.jpg 与 xxmLogo.png 存在

## 面试分析文档
- [ ] 导学-咸虾米壁纸.md 已生成，包含前置知识、重点亮点与学习顺序、必备知识点、推荐阅读（含相对路径）、自学提醒、项目技术定位、核心原理解析、关键设计决策、量化与验证
- [ ] 面经-咸虾米壁纸.md 已生成，包含项目简介、简历 bullet、15~25 道面试题（每主题 1 主问 + 2 追问）、每题口播 ≥150 字
