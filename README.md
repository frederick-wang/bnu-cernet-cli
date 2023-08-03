# BNU CERNET CLI：北京师范大学校园网命令行客户端 🌐

BNU CERNET CLI 是一款专为北京师范大学校园网用户设计的命令行客户端。自2023年7月1日校园网服务升级后，原有的命令行客户端无法正常使用。为了解决这个问题，我们开发了这款新的客户端，使用户能够在命令行环境下便捷地登录校园网并访问互联网资源。

<div align="center">
  <br>
  <img width="640" alt="image" src="https://github.com/frederick-wang/bnu-cernet-cli/assets/6050869/e5f0982f-71d9-41c8-bd38-5e838ca010db">
  <br>
</div>

## 🚀 主要功能

- 在无图形界面的 Linux 系统下连接互联网；
- 与其他命令行脚本联动使用；
- 在服务器上连接互联网；
- 其他更多可能性等待您的探索。

## 📦 安装指南

### 环境要求

- Python 3.2 或更高版本
- Linux 或 Windows 系统

### 安装步骤（Linux）

1. 点击 [此处](https://ghproxy.com/https://github.com/frederick-wang/bnu-cernet-cli/archive/refs/heads/main.zip) 下载本 Git 仓库的压缩包（下载链接已通过 [GitHub Proxy](https://ghproxy.com/) 进行了代理加速）；
2. 解压该压缩包，得到 `bnu_cernet` 文件；
3. 将 `bnu_cernet` 文件放置到任意目录下；
4. 在终端中进入该目录，执行以下命令为该文件添加可执行权限：

```bash
chmod +x bnu_cernet
```

完成以上步骤后，您可以在该目录下直接执行 `./bnu_cernet` 命令来运行该程序。

> :bulb: 注意：如果您将该文件的路径添加到系统的环境变量中，那么您可以在任意目录下直接执行 `bnu_cernet` 命令来运行该程序。

### 安装步骤（Windows）

1. 点击 [此处](https://ghproxy.com/https://github.com/frederick-wang/bnu-cernet-cli/archive/refs/heads/main.zip) 下载本 Git 仓库的压缩包（下载链接已通过 [GitHub Proxy](https://ghproxy.com/) 进行了代理加速）；
2. 解压该压缩包，得到 `bnu_cernet` 文件；
3. 将 `bnu_cernet` 文件放置到任意目录下；
4. 在命令行中进入该目录，执行以下命令来运行该程序：

```bash
python3 bnu_cernet
```

## 📘 使用指南

> :bulb: 注意：如果您没有将 `bnu_cernet` 添加到环境变量，而是直接在 `bnu_cernet` 程序所在的目录下运行该程序，请在下面的所有命令中将 `bnu_cernet` 替换为 `./bnu_cernet`。

如果您是首次使用该程序，可以通过执行 `bnu_cernet` 命令查看程序的使用方法。

```bash
bnu_cernet
```

执行后，您将看到如下的使用说明：

```bash
usage: bnu_cernet [-h] {login,status,logout} ...

北京师范大学校园网命令行客户端 (作者: Zhaoji Wang <zhaoji.wang@mail.bnu.edu.cn>)

positional arguments:
  {login,status,logout}
    login               登录
    status              查询 IP 状态
    logout              注销

options:
  -h, --help            show this help message and exit

调用示例:

  bnu_cernet status   
  bnu_cernet login   
  bnu_cernet login [-u 用户账号] [-p 校园网登录密码]   
  bnu_cernet logout   

注意事项:

  - 使用 status 命令会显示该 IP 当前的校园网连接状态
  - 使用 login 命令将该 IP 连接到校园网
      -u 后面跟的是你的用户账号，通常是学号（该参数可选）
      -p 后面跟的是你的校园网登录密码（该参数可选）
      如果不指定 -u 和 -p 参数，程序会提示你交互式输入账号和密码
  - 使用 logout 命令会断开该 IP 当前的校园网连接
```

## 🎬 使用示例

### 查询 IP 状态

```bash
bnu_cernet status
```

执行上述命令后，如果该 IP 在线，您将看到类似以下的输出：

```bash
🌐 IP 状态 在线
👤 用户账号 XXXXXXXXXXXX
📈 已用流量 19.19 GB
⏳ 已用时长 53小时3分11秒
💵 账户余额 117.32
📍 IP 地址 XX.XX.XX.XX
📖 产品名称 学生50元包月
```

如果该 IP 不在线，您将看到类似以下的输出：

```bash
💤 IP 状态 离线
📍 IP 地址 XX.XX.XX.XX
```

### 登录

```bash
bnu_cernet login
```

如果您想指定用户账号和密码，可以使用 `-u` 和 `-p` 参数：

```bash
bnu_cernet login -u 你的用户账号 -p 你的校园网登录密码
```

执行上述命令后，您将看到类似以下的输出：

```bash
🎉 认证成功！ (2023-07-03 06:46:28)

🌐 IP 状态 在线
👤 用户账号 XXXXXXXXXXXX
📈 已用流量 19.21 GB
⏳ 已用时长 53小时22分31秒
💵 账户余额 117.32
📍 IP 地址 XX.XX.XX.XX
📖 产品名称 学生50元包月
```

如果该 IP 已经在线，那么您将看到类似以下的输出：

```bash
🤔 IP 已在线，无需重复认证。 (2023-07-03 06:47:07)

🌐 IP 状态 在线
👤 用户账号 XXXXXXXXXXXX
📈 已用流量 19.21 GB
⏳ 已用时长 53小时22分31秒
💵 账户余额 117.32
📍 IP 地址 XX.XX.XX.XX
📖 产品名称 学生50元包月
```

### 注销

```bash
bnu_cernet logout
```

执行上述命令后，您将看到类似以下的输出：

```bash
👤 用户账号 XXXXXXXXXXXX 已注销 (2023-07-03 06:46:14)
📍 IP 地址 XX.XX.XX.XX
```

## 🔄 在线保持

保持服务器校园网常在线。

可参考该 Issue：[#1](https://github.com/frederick-wang/bnu-cernet-cli/issues/1)
