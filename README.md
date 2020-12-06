# 西北大学nCov自动填报脚本（支持Github Actions）

## Featurs
- 支持多种运行方式：
    - Github Actions：无需服务器即可免开机定时执行
    - CLI
    - Server（须配置crontab）
- 可定制内容、时间
- 单文件实现
- 支持用户名密码或应用Cookies两种登陆方式

## Usage

### CLI
TBD，可参考代码头部注释
### Github Action 运行方法
- Fork本项目
- 在项目中打开Settings->Secrets页面
- 点击“New Secret”创建如下五个新的密码：
    - AUTH_MODE
    - USERNAME
    - PASSWORD
    - EAI_SESS
    - UUKEY
    其中，AUTH_MODE伪认证模式（密码或cookies），依照所选的填写USERNAME/PASSWORD或者EAI_SESS/UUKEY，不需要的留空即可（写个空格或者随意填写）。
    各个参数的意义可以参考前文或代码开头的注释。
- 启动定时打卡
    进入Actions标签（页面上方），点击该工作流（Auto_Attendance_GitHub_Action），点击Run workflow按钮
    此外，push代码同样会触发该Workflow（只用触发一次即可）
- 之后在Action标签中可以查看每一次执行的情况，每次执行点击左侧Build，然后下拉展开“Run app”这个步骤可以查看具体执行结果

---
Github-Actions部分实现及readme教程参考仓库
[中南大学nCov健康打卡定时自动脚本](https://github.com/lxy764139720/Auto_Attendance)，
特此感谢