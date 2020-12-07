# 西北大学nCov自动填报脚本（支持Github Actions）

## Featurs
- 支持多种运行方式：
    - Github Actions：无需服务器即可免开机定时执行
    - CLI：支持命令行参数调用
    - Server（须配置crontab）
- 可定制填报内容、时间
- 单文件实现
- 支持用户名密码或应用Cookies两种登陆方式

## Usage

### CLI
--help 参数可以查看可用参数及说明
详细内容可用参考程序文件头部注释

### Github Action 运行方法
- Fork本项目
- 在项目中打开Settings->Secrets页面
- 点击“New Secret”，**分别**创建如下五个新的密码（名称均大写）：
    - AUTH_MODE：认证模式，账号密码方式填写"PASSWORD"，cookies方式填写"COOKIES"（不带引号）  
    - USERNAME：用户名，"PASSWORD"模式需要  
    - PASSWORD：密码，"PASSWORD"模式需要  
    - EAI_SESS：Cookies之一，"COOKIES"模式需要  
    - UUKEY：Cookies之一，"COOKIES"模式需要  

    其中，AUTH_MODE为认证模式，即密码（PASSWORD）或cookies（COOKIES）两种方式，依照所选的填写 USERNAME/PASSWORD 或者 EAI_SESS/UUKEY ，不需要的留空即可（写个空格或者随意填写）。两种认证方式只需要选择一种。
    各个参数的意义可以参考前文或代码开头的注释。
    此处配置的信息即便仓库为公开仓库其他人也看不到，日志部分也不会包含任何个人相关信息。上传的Secret会被Github加密保存，只能更新无法查看。
- 启动定时打卡
    进入Actions标签（页面上方），点击该工作流（Auto_Attendance_GitHub_Action），点击Run workflow按钮
    此外，push代码同样会触发该Workflow（只用触发一次即可）
- 之后在Action标签中可以查看每一次执行的情况，每次执行点击左侧Build，然后下拉展开“Run app”这个步骤可以查看具体执行结果

### 内置参数运行
程序开头Settings aera部分包括各类定义，可直接在此处配置并直接运行程序（默认方式，无需显示添加`--cli=False`参数）

---
Github-Actions部分配置参考仓库
[中南大学nCov健康打卡定时自动脚本](https://github.com/lxy764139720/Auto_Attendance)，
特此感谢