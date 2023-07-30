# nvm + pnpm 环境配置



## 安装 nvm

1. 从 [nvm-window github 仓库](https://github.com/coreybutler/nvm-windows/releases) 下载 `nvm-setup.exe` 文件，下载完成后点击进行安装，安装时会自动配置好环境变量

2. 检查是否安装成功：

   ```sh
   nvm -v
   ```

3. **启动**：

   ```sh
   nvm on
   ```

   

## 安装和配置 Node.js

1. 查看可下载的 Node.js 版本：

   ```sh
   nvm list available
   ```

   选择一个版本进行下载（建议选择 LTS 稳定版），例如：

   ```sh
   nvm install 18.17.0
   ```

2. 检查 Node.js 是否安装完成（需要先启动 nvm）：

   ```sh
   node -v
   ```

3. 查看 nvm 安装目录：

   ```sh
   nvm root
   ```

   进入该目录后创建两个文件夹：`node_global` 和 `node_cache`

   然后配置 npm 目录：

   ```sh
   npm config set preifx C:\xxx\nvm\node_global
   npm config set cache C:\xxx\nvm\node_cache
   ```

4. 配置环境变量：右键 此电脑 -> 属性 -> 高级系统设置 -> 环境变量，**系统变量** `Path` 添加上一步配置的路径：`C:\xxx\nvm\node_global` 



## 安装和配置 pnpm

1. 首先全局安装 pnpm：

   ```sh
   npm install -g pnpm
   ```

   检查是否安装完成：

   ```sh
   pnpm -v
   ```

2. 配置

   首先配置 pnpm 的目录：

   ```sh
   pnpm config set store-dir "C:\xxx\nvm\node_global\node_modules\pnpm\storeDir"
   pnpm config set global-dir "C:\xxx\nvm\node_global\node_modules\pnpm\globalDir"
   pnpm config set global-bin-dir "C:\xxx\nvm\node_global\node_modules\pnpm\globalBinDir"
   pnpm config set state-dir "C:\xxx\nvm\node_global\node_modules\pnpm\state"
   pnpm config set cache-dir "C:\xxx\nvm\node_global\node_modules\cache"
   ```

   然后配置环境变量：右键 此电脑 -> 属性 -> 高级系统设置 -> 环境变量，**系统变量** `Path` 添加上一步配置的路径 `C:\xxx\nvm\node_global\node_modules\pnpm\globalBinDir` 

3. 安装依赖

   ```sh
   pnpm add -g typescript
   ```

   检验是否安装完成

   ```sh
   tsc -v
   ```

   
