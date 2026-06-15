# TinyPHP Framework

## 中文

### 简介

一款轻量级、高性能的 PHP MVC 框架，经过日 PV 十亿级别的生产环境检验。

- 主要应用于分布式、高并发的生产环境
- 适应于多人团队协作
- 支持多环境和分布式处理
- 适用于 Web / Console / RPC 等运行环境，包括单一命令行文件打包，多任务的服务端守护进程等

### 相关项目

| 项目 | 说明 | 地址 |
|------|------|------|
| tinyphp | Demo 项目 | [github.com/aigmlab/tinyphp](https://github.com/aigmlab/tinyphp) |
| tinyphp-docs | 中文文档 | [github.com/aigmlab/tinyphp-docs](https://github.com/aigmlab/tinyphp-docs) |
| tinyphp-ui | UI 组件库 | [github.com/aigmlab/tinyphp-ui](https://github.com/aigmlab/tinyphp-ui) |

### 运行环境

#### CentOS (生产环境)

依赖于 lnmp-utils: Linux (CentOS 7 X64) + OpenResty (Nginx) + MySQL + PHP + Redis 一键安装包。

> 项目地址: [https://github.com/aigmlab/lnmp-utils](https://github.com/aigmlab/lnmp-utils)

```shell
git clone https://github.com/aigmlab/lnmp-utils.git
cd ./lnmp-utils
./install.sh -m tinyphp
cd /data/web/tinyphp
php public/index.php
```

#### Docker (开发环境)

```shell
workspace=/data/workspace/tinyphp
docker pull centos:7
docker run -d -p 80:80 -p 10022:22 \
  -v $workspace:/data/web/tinyphp \
  --name="tinyphp" --hostname="tinyphp" --restart=always \
  centos:7 /sbin/init

docker exec -it tinyphp /bin/bash
git clone https://github.com/aigmlab/lnmp-utils.git
cd ./lnmp-utils
./install.sh -m tinyphp-bootstrap
curl http://127.0.0.1
```

### Demo

```shell
composer create-project aigm/tinyphp
cd tinyphp

# 运行
php public/index.php

# 编译
php public/index.php --build

# 开启守护进程
php public/index.php -d

# 编辑配置文件
vi application/config/profile.php
```

### 中文文档

- [Demo](https://github.com/aigmlab/tinyphp)
- [中文文档](https://github.com/aigmlab/tinyphp-docs)
  - [语言基础规范](https://github.com/aigmlab/tinyphp-docs/tree/master/docs/coding)
  - [SQL 设计规范](https://github.com/aigmlab/tinyphp-docs/tree/master/docs/sql)
  - [团队编码规范](https://github.com/aigmlab/tinyphp-docs/tree/master/docs/team)

#### 框架使用手册
- [Index/入口文件](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/index-001.md)
- [Application/应用](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/application-002.md)
- [Properties/应用配置](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/profile-003.md)
  - [Debug/调试模式](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/debug-004.md)
  - [Bootstrap/引导程序](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/bootstrap-005.md)
  - [Lang/语言包](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lang-006.md)
  - [Data/数据源](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/data-007.md)
  - [Cache/缓存](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/cache-008.md)
  - [Router/路由器](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/router-009.md)
  - [Logger/日志收集](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/logger-010.md)
  - [Dispatcher/派发器](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/dispatcher-011.md)
  - [Configuration/配置类](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/configuration-012.md)
  - [Builder/打包](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/builder-013.md)
  - [Daemon/守护进程](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/daemon-014.md)
  - [Filter/过滤器](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/filter-015.md)
  - [Plugin/插件](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/plugin-016.md)
- [Controller/控制器](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/controller-017.md)
- [Model/模型](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/model-018.md)
- [Viewer/视图](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/viewer-019.md)

#### 框架标准库参考
- [Tiny: 工具包](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/tiny.md)
- [Tiny\Runtime: 运行时](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/runtime.md)
- [Tiny\Build: 打包](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/build.md)
- [Tiny\Cache: 缓存](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/cache.md)
- [Tiny\Config: 配置](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/config.md)
- [Tiny\Console: 命令行](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/console.md)
- [Tiny\Data: 数据层](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/data.md)
- [Tiny\Filter: 过滤器](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/filter.md)
- [Tiny\Image: 图片处理](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/image.md)
- [Tiny\Lang: 语言包](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/lang.md)
- [Tiny\Log: 日志处理](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/log.md)
- [Tiny\MVC: MVC](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/mvc.md)
- [Tiny\Net: 网络](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/net.md)
- [Tiny\String: 字符处理](https://github.com/aigmlab/tinyphp-docs/blob/master/docs/manual/lib/string.md)

---

## English

### Overview

A lightweight and high-performance PHP MVC framework, battle-tested at 1+ billion daily PV in production.

- Designed for distributed, high-concurrency production environments
- Suitable for multi-developer team collaboration
- Supports multi-environment and distributed processing
- Works with Web, Console, and RPC runtimes; supports single-file packaging and daemon processes

### Related Projects

| Project | Description | URL |
|---------|-------------|-----|
| tinyphp | Demo project | [github.com/aigmlab/tinyphp](https://github.com/aigmlab/tinyphp) |
| tinyphp-docs | Documentation (Chinese) | [github.com/aigmlab/tinyphp-docs](https://github.com/aigmlab/tinyphp-docs) |
| tinyphp-ui | UI component library | [github.com/aigmlab/tinyphp-ui](https://github.com/aigmlab/tinyphp-ui) |

### Environment

#### CentOS (Production)

```shell
git clone https://github.com/aigmlab/lnmp-utils.git
cd ./lnmp-utils
./install.sh -m tinyphp
cd /data/web/tinyphp
php public/index.php
```

#### Docker (Development)

```shell
workspace=/data/workspace/tinyphp
docker pull centos:7
docker run -d -p 80:80 -p 10022:22 \
  -v $workspace:/data/web/tinyphp \
  --name="tinyphp" --hostname="tinyphp" --restart=always \
  centos:7 /sbin/init

docker exec -it tinyphp /bin/bash
git clone https://github.com/aigmlab/lnmp-utils.git
cd ./lnmp-utils && ./install.sh -m tinyphp-bootstrap
curl http://127.0.0.1
```

### Quick Start

```shell
composer create-project aigm/tinyphp
cd tinyphp

# Run
php public/index.php

# Build single file
php public/index.php --build

# Start daemon
php public/index.php -d

# Edit config
vi application/config/profile.php
```

### Documentation

Full documentation is available at [aigm/tinyphp-docs](https://github.com/aigmlab/tinyphp-docs) (Chinese).

See the [中文文档](#中文文档) section above for the complete manual and standard library reference.
