# 咸虾米壁纸升级至插件市场迭代版 Spec

## Why
项目根目录存在一个基础版 UniApp 壁纸应用，而 `xxm-wallpaper-插件市场迭代版/` 目录包含了功能更完善、组件更丰富、UI 更精致的迭代版本。为了让根目录项目具备完整的产品能力，需要将迭代版的核心功能、页面、组件、工具函数和样式系统合并/升级到根目录，并生成面试分析文档帮助开发者吃透项目。

## What Changes
- **新增页面**：专题(subject)、专题详情(subject/detail)、搜索(search)、公告(notice)、公告详情(notice/detail)、排行榜(pages_quick/ranking)、近期上新(pages_quick/news)
- **新增/升级组件**：picture-item、subject-item、common-title、theme-item、custom-nav-bar
- **升级 API 层**：apis.js 增加专题、排行榜、近期上新、搜索、公告详情等接口
- **升级工具函数**：system.js → layout.js（更完善的导航栏/安全区计算）、tools.js（日期/数字格式化）、common.js（路由/时间/Toast 封装）
- **升级样式系统**：base-style.scss + common-style.scss，引入品牌色变量与 pageBg 等全局样式
- **升级 App.vue**：引入全局公共样式
- **升级 pages.json**：注册新页面、subPackages、tabBar 配置
- **升级 manifest.json**：适配 Vue3、多平台配置
- **新增/升级 uni_modules**：mp-html、uni-search-bar、uni-load-more、uni-tag、uni-datetime-picker、uv-empty/uv-icon/uv-link/uv-skeletons/uv-text/uv-ui-tools 等
- **生成面试分析文档**：导学-咸虾米壁纸.md + 面经-咸虾米壁纸.md

## Impact
- Affected specs: 全端小程序/H5/App 壁纸浏览、下载、评分、搜索、专题、公告、排行榜、近期上新
- Affected code: 根目录 pages/、components/、utils/、api/、common/、uni_modules/、App.vue、pages.json、manifest.json

## ADDED Requirements

### Requirement: 专题系统
The system SHALL 提供专题列表页与专题详情页。
#### Scenario: 用户浏览专题
- **WHEN** 用户进入专题 Tab
- **THEN** 展示专题卡片列表，每张卡片包含旋转拼接的预览图、标题、浏览数、图片数量
- **WHEN** 用户点击专题卡片
- **THEN** 进入专题详情页，顶部为毛玻璃背景头图，下方展示该专题全部壁纸

### Requirement: 搜索系统
The system SHALL 提供关键词搜索与历史记录管理。
#### Scenario: 用户搜索壁纸
- **WHEN** 用户在搜索页输入关键词并确认
- **THEN** 展示搜索结果网格列表，支持触底加载更多
- **THEN** 历史搜索词本地缓存（最多 10 条），支持一键清空

### Requirement: 公告系统
The system SHALL 提供公告列表与富文本详情。
#### Scenario: 用户查看公告
- **WHEN** 用户点击首页公告轮播或公告入口
- **THEN** 可查看公告列表与富文本详情（使用 mp-html 渲染）

### Requirement: 排行榜与近期上新
The system SHALL 提供下载榜/评分榜双 Tab 排行榜，以及近期上新页面。
#### Scenario: 用户查看排行与新壁纸
- **WHEN** 用户点击首页快捷入口
- **THEN** 进入排行榜页，支持日期范围选择与 Tab 切换
- **THEN** 进入近期上新页，展示最新壁纸并支持广告位插入

### Requirement: 评分与下载
The system SHALL 支持用户评分与下载保存到相册。
#### Scenario: 用户互动
- **WHEN** 用户在预览页点击评分
- **THEN** 弹出评分弹窗，支持半星，提交后更新本地状态
- **WHEN** 用户点击下载
- **THEN** 非 H5 端保存图片到系统相册，并处理权限申请与失败兜底

## MODIFIED Requirements

### Requirement: 首页升级
**原**: 基础版首页仅有 Banner、公告、每日推荐、分类精选。
**新**: 增加专题推荐模块、快捷入口（排行榜/近期上新）、骨架屏 loading、更完善的分享配置。

### Requirement: 分类与分类列表升级
**原**: 基础分类展示。
**新**: 分类列表支持触底加载、loading 状态、分享参数携带、本地缓存清理。

### Requirement: 预览页升级
**原**: 基础滑动预览。
**新**: 支持分享进入时单图加载、评分状态回显、下载记录上报、图片预加载策略（readImgsFun 前后三张）、返回失败兜底到首页。

### Requirement: 用户中心升级
**原**: 简单用户信息展示。
**新**: 展示 IP/地址、下载/评分数量、联系客服（小程序 open-type contact / H5 拨打电话）、订阅更新/常见问题入口。

## REMOVED Requirements
- 无功能删除，为基础版的功能增强与扩展。
