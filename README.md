# 个人网页导航系统

## 项目概述

这是一个自动化的个人网页导航系统，用于展示和管理您的所有HTML页面。系统会自动从GitHub仓库获取所有HTML文件，并以美观的卡片形式展示，每个卡片包含页面预览图和访问链接。

## 主要功能

### 1. 自动页面发现
- 自动从GitHub仓库获取所有HTML文件（除index.html外）
- 无需手动更新导航页面，添加新HTML文件后自动显示
- 支持动态生成页面标题（根据文件名自动格式化）

### 2. 预览图展示
- 自动从`/image/`目录获取与HTML文件同名的预览图
- 预览图命名规则：与HTML文件同名，扩展名为.png
- 支持图片加载失败时的备用图片机制
- 鼠标悬停时预览图有放大动画效果

### 3. 分页功能
- 每页显示5行3列共15个页面卡片
- 支持上一页/下一页导航
- 页码按钮可直接跳转到指定页
- 当前页码高亮显示

### 4. 鎏金科技风设计
- 现代化UI设计，采用鎏金科技风配色
- 卡片标题栏添加金色闪光动画效果
- 页面标题区域添加流光溢彩效果
- 按钮添加悬停动画和光效

### 5. 自动更新时间
- 显示仓库最后更新时间
- 通过GitHub API获取最新提交时间
- 如API请求失败，自动回退到当前时间

### 6. 响应式设计
- 自适应不同屏幕尺寸
- 在移动设备上自动调整为单列布局

## 配置说明

### 1. 文件结构
```
website/
├── index.html          # 导航页面主文件
├── image/              # 预览图文件夹
│   ├── calculator.png  # 计算器页面预览图
│   ├── alarm-clock.png # 闹钟页面预览图
│   └── default.png     # 默认预览图（当特定预览图不存在时使用）
├── calculator.html     # 计算器页面
├── alarm-clock.html    # 闹钟页面
└── ...                 # 其他HTML页面
```

### 2. 预览图命名规则
- 预览图应放在`/image/`目录下
- 预览图文件名应与HTML文件名相同，只是扩展名为.png
- 例如：`calculator.html` → `/image/calculator.png`
- 特殊情况：`chengdu_trip.html` → `/image/chengdu_trip.png`
- 建议添加一个`default.png`作为默认预览图

### 3. GitHub配置
- 仓库名：website
- 用户名：yourusername
- 部署平台：Cloudflare Pages

### 4. 自定义配置
可以通过修改CSS变量自定义界面风格：
```css
:root {
    /* 鎏金科技风配色 */
    --primary-color: #3498db;      /* 主色调 */
    --secondary-color: #f8f9fa;    /* 次要色调 */
    --text-color: #2c3e50;         /* 文本颜色 */
    --link-color: #2980b9;         /* 链接颜色 */
    --link-hover-color: #1a5276;   /* 链接悬停颜色 */
    --card-shadow: 0 4px 10px rgba(0, 0, 0, 0.15); /* 卡片阴影 */
    --header-bg: linear-gradient(135deg, #3498db, #2c3e50); /* 标题背景 */
    --gold-accent: #f39c12;        /* 金色点缀 */
    --tech-accent: #2ecc71;        /* 科技绿点缀 */
}
```

## 使用方法

### 添加新页面
1. 创建新的HTML文件并上传到GitHub仓库根目录
2. 创建对应的预览图（与HTML文件同名，扩展名为.png）并上传到`/image/`目录
3. 导航页面会自动显示新添加的页面

### 部署更新
1. 将index.html文件上传到GitHub仓库根目录
2. Cloudflare Pages会自动部署更新
3. 访问您的网站域名即可看到更新后的导航页面

## 技术实现

### 前端技术
- HTML5 + CSS3 + JavaScript
- 响应式设计（媒体查询）
- CSS动画和过渡效果
- Flexbox和Grid布局

### API集成
- GitHub API用于获取仓库文件列表
- GitHub API用于获取最后更新时间

### 性能优化
- 分页加载减少一次性渲染的卡片数量
- 图片加载失败处理机制
- 异步加载仓库数据

## 未来改进方向

1. 添加搜索功能，方便快速查找页面
2. 支持页面分类和标签筛选
3. 添加暗色模式切换
4. 支持自定义排序方式（按名称、更新时间等）
5. 添加页面访问统计功能
6. 优化移动端体验

## 界面展示

![image](https://github.com/user-attachments/assets/37131360-a2b6-4050-8fe5-e9a3d91c81cc)




---

*最后更新：2023年5月23日 22:11*
