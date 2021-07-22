# Env 环境配置

- vscode 插件 cmake 与 cmake tools
- 系统安装对应 gcc、clang、msvs 都可以
- 每次启动项目时 cmake tools 会查找 CMakeLists.txt。然后初始化项目
  - 需要明确选择工具链，如果选择让 cmake-tools 自己猜测，mac 上 debug 是失败的，提示没有找到 gdb，这样运行与调试都是可快捷操作的。

此外，可以使用 settings.json 的配置，强行置顶 debug 工具 lldb，或者 gdb

# CMakeList.txt

常用命令：

- 找库：
  - find_library (<VAR> name1 [path1 path2 ...])
  - find_package(<LibaryName>)

## find_package(<LibaryName>)

每一个模块都会定义以下几个变量 -

<LibaryName>\_FOUND

<LibaryName>\_INCLUDE_DIR or <LibaryName>\_INCLUDES <LibaryName>\_LIBRARY or <LibaryName>\_LIBRARIES

```cmake
find_package(CURL REQUIRED)
if(CURL_FOUND)
    message(${CURL_INCLUDE_DIR})
    include_directories(${CURL_INCLUDE_DIR})
    target_link_libraries(AWindow ${CURL_LIBRARY})
else(CURL_FOUND)
    message("dfsdfaaaaaaa")
endif(CURL_FOUND)
```
