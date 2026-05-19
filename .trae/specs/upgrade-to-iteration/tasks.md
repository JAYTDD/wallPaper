# Tasks

- [ ] Task 1: 升级全局配置与样式系统
  - [ ] SubTask 1.1: 用迭代版 manifest.json 替换根目录 manifest.json（Vue3、多平台、H5 router base）
  - [ ] SubTask 1.2: 用迭代版 pages.json 替换根目录 pages.json（注册新页面、subPackages、tabBar）
  - [ ] SubTask 1.3: 升级 App.vue 引入 common-style.scss 全局样式
  - [ ] SubTask 1.4: 创建/替换 common/style/base-style.scss 与 common-style.scss
  - [ ] SubTask 1.5: 创建/替换 uni.scss 引入 base-style.scss

- [ ] Task 2: 升级工具函数与 API 层
  - [ ] SubTask 2.1: 创建 api/apis.js 并写入全部接口（含新增专题、搜索、排行榜、近期上新、公告等）
  - [ ] SubTask 2.2: 创建 utils/request.js 封装 uni.request（含 errCode 处理、loading/reject 统一）
  - [ ] SubTask 2.3: 创建 utils/system.js（状态栏/导航栏高度，兼容头条小程序）
  - [ ] SubTask 2.4: 创建 utils/layout.js（更完善的导航栏/安全区/胶囊按钮计算）
  - [ ] SubTask 2.5: 创建 utils/common.js（路由封装、时间对比、返回首页兜底、Toast）
  - [ ] SubTask 2.6: 创建 utils/tools.js（数字格式化、日期范围、补零）

- [ ] Task 3: 升级与新增组件
  - [ ] SubTask 3.1: 替换 components/custom-nav-bar/custom-nav-bar.vue（支持搜索入口、渐变背景）
  - [ ] SubTask 3.2: 替换 components/common-title/common-title.vue（slot 封装）
  - [ ] SubTask 3.3: 新增 components/picture-item/picture-item.vue（图片预览跳转、本地缓存传递）
  - [ ] SubTask 3.4: 替换 components/theme-item/theme-item.vue（支持更新时间标签、更多入口）
  - [ ] SubTask 3.5: 新增 components/subject-item/subject-item.vue（专题卡片、旋转拼图效果）

- [ ] Task 4: 升级现有页面
  - [ ] SubTask 4.1: 重写 pages/index/index.vue（新增专题推荐、快捷入口、骨架屏、分享）
  - [ ] SubTask 4.2: 重写 pages/classfiy/classfiy.vue → 对齐迭代版 classify（grid 布局、分享）
  - [ ] SubTask 4.3: 新增 pages/classlist/classlist.vue（触底加载、loading、分享、缓存清理）
  - [ ] SubTask 4.4: 重写 pages/preview/preview.vue（分享进入加载、评分回显、下载权限、预加载）
  - [ ] SubTask 4.5: 重写 pages/user/user.vue（IP/地址、下载/评分统计、客服、公告入口）

- [ ] Task 5: 新增功能页面
  - [ ] SubTask 5.1: 新增 pages/subject/subject.vue（专题列表、分页加载、分享）
  - [ ] SubTask 5.2: 新增 pages/subject/detail.vue（专题详情头图、毛玻璃、壁纸网格）
  - [ ] SubTask 5.3: 新增 pages/search/search.vue（搜索、历史记录、热门推荐、触底加载）
  - [ ] SubTask 5.4: 新增 pages/notice/notice.vue（公告列表）
  - [ ] SubTask 5.5: 新增 pages/notice/detail.vue（富文本详情，mp-html）
  - [ ] SubTask 5.6: 新增 pages_quick/ranking.vue（排行榜、日期选择、Tabs、进度条、骨架屏）
  - [ ] SubTask 5.7: 新增 pages_quick/news.vue（近期上新、广告位、触底加载、骨架屏）

- [ ] Task 6: 升级 uni_modules 与静态资源
  - [ ] SubTask 6.1: 将迭代版 uni_modules 中新增/升级模块复制到根目录 uni_modules（mp-html、uni-search-bar、uni-load-more、uni-tag、uni-datetime-picker、uv 系列等）
  - [ ] SubTask 6.2: 复制 static/images/tabBar 与 logo 等静态资源到根目录 static/

- [ ] Task 7: 生成面试分析文档
  - [ ] SubTask 7.1: 调用 interview-analyzer-skill 生成 导学-咸虾米壁纸.md
  - [ ] SubTask 7.2: 调用 interview-analyzer-skill 生成 面经-咸虾米壁纸.md

# Task Dependencies
- Task 2 依赖 Task 1（全局配置先就位）
- Task 3 依赖 Task 2（组件使用工具函数）
- Task 4 依赖 Task 3（页面使用组件）
- Task 5 依赖 Task 3（新增页面使用组件）
- Task 6 可与 Task 1~5 并行
- Task 7 依赖 Task 4~5（需要完整项目信息）
