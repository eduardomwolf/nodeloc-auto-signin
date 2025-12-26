NodeLoc Check-in Automation

基于 Selenium + undetected-chromedriver 的 NodeLoc 自动签到脚本
适用于 青龙（QingLong）/ Linux Server / 本地 Python 环境

✨ 项目简介

本项目是一个 NodeLoc 论坛自动签到脚本，
通过模拟真实浏览器行为完成每日签到操作，支持：

✅ 多账号顺序签到

✅ 无头 Chrome（Headless）

✅ Cookie 登录（无需账号密码）

✅ 适配青龙面板（QingLong）

✅ 自动规避常见 Selenium 特征检测

项目结构清晰，代码已模块化拆分，同时适合作为 Selenium 自动化学习示例。

📁 项目结构
.
├── browser.py   # 浏览器创建 & Cookie 注入
├── checkin.py   # 登录检测 & 签到逻辑
├── main.py      # 程序入口 & 多账号调度
└── README.md

🧠 技术栈

Python 3.8+

Selenium

undetected-chromedriver

Chrome / Chromium

🚀 使用方式
1️⃣ 安装依赖
pip install selenium undetected-chromedriver


确保系统中已安装 Chrome / Chromium。

2️⃣ 获取 Cookie

使用浏览器登录 https://www.nodeloc.com

打开开发者工具（F12）

在 Network / 请求头 / Application → Cookies 中获取完整 Cookie

复制为一行字符串，例如：

_t=xxxxx; _forum_session=xxxxxx

3️⃣ 设置环境变量（支持多账号）
单账号
export NL_COOKIE="_t=xxxxx; _forum_session=xxxxxx"

多账号（换行）
export NL_COOKIE="
_t=xxxxx; _forum_session=aaaaa
_t=yyyyy; _forum_session=bbbbb
"


如 Cookie 中包含额外字段，无需删除，脚本会自动解析。

4️⃣ 运行脚本
python main.py

⏰ 青龙（QingLong）使用示例
cron: 59 8 * * *

const $ = new Env("NodeLoc 签到");

📌 特性说明

使用 undetected-chromedriver 降低自动化特征

优先使用 WebDriverWait，减少不必要的 sleep

每个账号独立浏览器实例，更安全

自动判断：

已签到

签到成功

状态异常

⚠️ 免责声明（Disclaimer）

请在使用前务必阅读：

本项目仅用于 Python / Selenium / 浏览器自动化技术学习与研究。

本项目 不保证 符合 NodeLoc 或任何网站的用户协议（ToS）

请勿将本项目用于 任何违反目标网站规则的行为

使用本项目造成的：

账号封禁

数据丢失

其他任何后果
均由使用者自行承担，作者概不负责

若目标网站明确禁止自动化行为，请立即停止使用

一旦使用本项目，即视为你已阅读并同意上述声明。

📜 License

本项目采用 MIT License 开源协议。

你可以：

自由使用

自由修改

自由分发

但请保留原作者声明及本免责声明。

🤝 交流与贡献

欢迎 Issue / PR

欢迎用于 Selenium 学习、自动化研究

不接受任何“保证不封号 / 商业用途 / 批量滥用”相关请求

⭐ Star

如果这个项目对你有帮助，欢迎点个 ⭐
你的支持是我继续维护和优化的动力。
