# Stock 页面前端改造待修改清单

更新时间：2026-07-31

## Figma 设计稿

- 文件：NiuOne Stock Redesign - Steven Portfolio Direction
- 链接：https://www.figma.com/design/BshuhOABeNG7Wj3DpPLB9e
- 当前建议采用页面：`Card reference V2`

## 已确认方向

- 卡片语言参考个人网站截图，而不是只做颜色替换。
- 默认卡片使用低亮度深色实底，减少厚重玻璃感。
- 卡片顶部使用 2px 紫色上边框。
- 圆角收敛到约 6px。
- 左上角保留 icon 容器。
- 右上角使用低透明度编号。
- hover / active 态使用紫色渐变面、边框提亮、轻微上浮。
- 手机端应按状态流重新组织，不直接压缩桌面布局。

## 当前代码状态

当前仓库里已经有一版临时视觉皮肤，主要改动：

- `frontend/dashboard.css`
- `frontend/admin.css`
- `frontend/index.html`
- `frontend/admin.html`

这版已经把页面改成深色、紫色、玻璃感，但它仍偏“换皮”，不是最终形态。

下一轮落地时，应以 Figma 的 `Card reference V2` 为准，重构布局和卡片组件，而不是继续堆 CSS 覆盖。

## 下一轮前端任务

- [ ] 抽出统一卡片样式：默认态、hover 态、active 态。
- [ ] 将主看板首屏改成 Figma V2 的结构：
  - hero 状态区
  - 四个核心指标卡
  - 收益曲线主卡
  - 策略队列卡
  - 持仓与日志摘要卡
- [ ] 给关键卡片补 icon，优先使用轻线条图标。
- [ ] 重新整理手机端 `/practice`：
  - 今日状态
  - 快捷操作
  - 账户指标
  - 收益曲线
  - 策略信号
  - 操作日志
- [ ] 修正 Figma V2 手机稿里“策略信号”卡片的文字间距。
- [ ] 减少大面积嵌套卡片，保留更多留白和细线分隔。
- [ ] hover 动效保持克制：2px 上浮、紫色边框提亮、轻微渐变背景。
- [ ] 移动端取消上浮位移，仅保留按压/颜色反馈。
- [ ] 后台 `/admin` 继续保持工具属性，但使用同一卡片语言。

## 远程服务器信息

- 线上入口：https://stevenchan-traveler.cn/stock/
- 服务器 NiuOne 路径：`/opt/niuone`
- 数据路径：`/opt/niuone-data`
- Nginx 已代理 `/stock/` 到本机 `127.0.0.1:8787`
- 外层访问账号：`stock`
- 外层访问密码存放在服务器：`/home/admin/stock_basic_auth_password.txt`
- NiuOne 后台 bootstrap 管理密钥：`/opt/niuone-data/runtime/dashboard_admin_token.txt`

## 换电脑继续工作

1. 克隆仓库：

   ```bash
   git clone https://github.com/Travelerzk/niuone.git
   ```

2. 打开本文件：

   ```bash
   docs/STOCK_REDESIGN_TODO.md
   ```

3. 打开 Figma：

   https://www.figma.com/design/BshuhOABeNG7Wj3DpPLB9e

4. 以后真正落地前端时，以 `Card reference V2` 为目标。
