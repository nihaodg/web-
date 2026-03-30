# CTF Web 漏洞可视化学习平台

一个基于 Tailwind CSS + Lucide Icons 构建的 CTF Web 漏洞学习平台，专注于 PHP 反序列化漏洞的交互式学习。

## 在线预览

**https://3f5c6b93977b.monkeycode-ai.online/**

## 项目结构

```
web-
├── index.html                      # 主页面
└── pages/
    ├── php-unserialize-basics.html  # 序列化与反序列化基础
    ├── magic-methods.html           # PHP魔术方法详解
    ├── pop-chain.html              # POP链构造
    ├── phar-unserialize.html       # Phar反序列化漏洞
    ├── native-classes.html         # PHP原生类利用
    ├── example1.html                # 例题1：User类反序列化
    └── example2.html               # 例题2：A/B类联合构造
```

## 技术栈

| 技术 | 说明 |
|------|------|
| Tailwind CSS | 原子化CSS样式框架（CDN引入） |
| Lucide Icons | 开源图标库 |
| 纯HTML/CSS/JS | 无需构建工具，纯静态页面 |

## 学习路径

```
序列化基础 → 魔术方法 → POP链构造 → Phar反序列化 → 原生类利用 → 实战例题
```

## 内容板块

### 1. 序列化基础
- 序列化与反序列化概念
- PHP 中的 serialize/unserialize 函数
- 序列化格式详解（O:4:"User"、s:4:"name" 等）
- 漏洞利用条件

### 2. PHP魔术方法
- `__construct` / `__destruct` - 构造与析构
- `__get` / `__set` / `__isset` / `__unset` - 属性访问
- `__toString` - 字符串操作
- `__call` / `__callStatic` / `__invoke` - 方法调用
- `__sleep` / `__wakeup` / `__serialize` / `__unserialize` - 序列化相关

每个方法都配有 PHP 代码示例 + 运行结果展示。

### 3. POP链构造
- 反向回溯法原理
- 调用链图解
- 单类POP链构造示例
- 多类联合POP链构造

### 4. Phar反序列化
- Phar 文件结构（Stub、Manifest、Content、Signature）
- 漏洞原理与受影响的函数
- 利用技巧：伪装图片绕过上传

### 5. PHP原生类利用
- Error/Exception - XSS利用
- SoapClient - SSRF + CRLF注入
- SimpleXMLElement - XXE
- DirectoryIterator - 目录遍历

### 6. 实战例题
- **例题1**：User类 - `__destruct()` + `__toString()` 触发 `system()`
- **例题2**：A/B类联合 - `__wakeup()` + `__toString()` + `__get()` 触发 `file_put_contents()`

每道例题包含：题目描述、服务端源码、漏洞分析、调用链图解、解题步骤、完整EXP脚本。

## 开发说明

本项目为纯静态页面，直接用浏览器打开 `index.html` 即可运行，无需安装任何依赖。

如需本地预览：

```bash
# Python 方式
python3 -m http.server 8000

# PHP 方式
php -S localhost:8000
```

## 页面示例

```html
<!-- 卡片组件 -->
<div class="bg-gray-800 rounded-xl border border-gray-700 p-5 card-hover">
  <div class="flex items-center gap-3 mb-3">
    <div class="w-10 h-10 bg-blue-900/30 rounded-lg flex items-center justify-center">
      <i data-lucide="box" class="w-5 h-5 text-blue-400"></i>
    </div>
    <div>
      <h3 class="text-lg font-bold text-white">标题</h3>
      <span class="text-xs text-blue-400">副标题</span>
    </div>
  </div>
  <p class="text-gray-400 text-sm">描述内容</p>
</div>
```

## License

MIT
