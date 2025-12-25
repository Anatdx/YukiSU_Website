# 安装参考

::: details 将会了解 YukiSU 安装过程
[[toc]]
:::

::: danger 警告
**Root 您的设备可能会使保修失效，如果操作不当可能会造成永久性损坏。**
请务必在继续之前创建完整备份，阅读文档确保与您的设备兼容，遵循文档参考，准备好恢复计划
:::

请**全部**参考 [KernelSU 安装指南](https://kernelsu.org/zh_CN/guide/installation.html)

:::

## 开始安装

### 通用 GKI 安装

::: tip
适用于 GKI 2.0 设备，如小米、红米、三星等（不包括内核修改的制造商，如魅族、一加、真我和 OPPO）
:::

#### 步骤

1. 下载 GKI 构建文件

   暂不提供，不好意思，用lkm去吧，要么你自己构建gki

2. 通过 Recovery 刷入

   启动到 `TWRP recovery`，选择 **Install**，导航到下载的 `AnyKernel3 zip` 文件，滑动刷入后重启系统

3. [验证安装](#验证)

::: details 文件格式说明
无后缀的 `.zip` 档案是未压缩的，`gz` 后缀是特定型号使用的压缩格式。
:::

### 一加设备安装

1. 获取设备信息

- 内核版本（前两部分，例如 `5.10`、`5.15`、`6.1`、`6.6`）
- 处理器代号（通常是不含数字的英文）
- 来自一加开源内核仓库的分支和配置文件

2. 创建自定义构建

   随便找个能构建你的设备的SukiSU内核的仓库，把仓库链接换成我的

3. 刷入构建

   下载生成的带有 AnyKernel3 后缀的 zip 文件，启动到 `TWRP recovery`，选择 **Install**，导航到下载的 `AnyKernel3 zip` 文件，滑动刷入后重启系统；没TWRP的手机或者不想用rec的，先刷个LKM，或者面具APatch随便什么，然后给管理器Root权限，点直接安装然后用`刷写AnyKernel3`

::: tip
您只需要填写内核版本的前两部分。自行搜索处理器代号
:::

::: warning 必需的内核配置
为了支持 KPM，添加 `CONFIG_KPM=y`

对于非 GKI 设备，还要添加 `CONFIG_KALLSYMS=y` 和 `CONFIG_KALLSYMS_ALL=y`
:::

## 安装后设置

### 系统更新时保持 Root

> [!IMPORTANT]
> 如何在 OTA 更新后保持 root 访问权限：

#### 步骤

1. 系统更新后重启前

   - OTA 安装后不要立即重启，将 YukiSU Ultra 安装到第二插槽  
   - 打开 YukiSU 管理器，在**刷入/修补内核**界面选择 **GKI/non_GKI install**，选择您的 `AnyKernel3` 内核 `zip` 文件，选择与当前运行插槽相对的插槽然后刷入重启。nb哪个人物教你们这么更新的？用LKM过渡，不然崩了找谁说理去？

2. 替代方案：LKM 模式

   使用 [LKM 模式](#通用-gki) 在 OTA 后安装到未使用的插槽。

::: warning 警告
**非 GKI 设备注意事项：** 此方法不支持所有非 GKI 设备。对于非 GKI 设备，使用 TWRP 是最安全的方法。
:::

## 验证

安装后，验证一切是否正常工作，

- 打开 YukiSU 管理器检查 root 工作状态
- 使用 root 权限的应用程序来验证 root 访问是否工作正常
- 在设置 -> 关于手机中检查内核版本

## 需要帮助？

如果在安装过程中遇到问题：

1. 查看我们的[兼容性指南](./compatibility)了解设备要求
2. 访问我们的 [GitHub 仓库](https://github.com/Anatdx/YukiSU)获取支持
3. 加入我们的 [Telegram 社区](https://t.me/sukiksu)获取帮助

::: danger 安全提醒
**始终有备用计划！** 保留您的原始 `boot.img/init_boot.img` 并知道如何在出现问题时恢复设备。
:::
