# tauri-sqlite-vss-demo

tauri-app使用sqlite-vss示例

## 开发环境和依赖

- macOS x86_64
- yarn
- tauri 1.5+
- rusqlite v0.29.0
- sqlite-vss v0.1.2

## 准备工作

原本需要安装libomp和llvm，提前修改libomp.dylib库的链接路径，现在已经把相关库放到src-tauir/libs中，已经写好在脚本中。

```
brew install libomp
brew install llvm
```

## 运行

```
./sh/run.sh
```

## 打包

```
./sh/build.sh
```

## 需要注意的地方

1. cargo.toml中的sqlite-vss依赖如果设置如下`sqlite-vss = {version="0.1.2"}`，就需要添加`LIB_SQLITE_VSS`环境变量指示sqlite-vss-v0.1.2-static-macos-x86_64库的位置；
2. src-tauir/build.rs需要添加针对sqlite-vss的编译语句；
3. rusqlite暂时只能使用0.29.0版本，0.30.0以上的版本会报错；
4. 依赖libomp.dylib库，需要手动修改链接该动态库的链接路径，已经写好在脚本中；
5. 如果有arm64 macos运行报错的地方，请参考x86_64 macos的配置另作修改。
