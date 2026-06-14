# 学生成绩管理系统

这是一个使用 C/C++、EasyX 和链表实现的图形化学生成绩管理系统。

## 功能

- 添加、修改、删除和搜索学生
- 按成绩或学号排序
- 查看成绩统计
- 保存、重新加载和备份数据
- 导出文本报表

## 项目结构

```text
学生成绩管理系统课程设计提交/
|-- CMakeLists.txt
|-- CMakePresets.json
|-- README.md
|-- Visual Studio 2026运行说明.txt
|-- 学生成绩管理系统课程设计报告.docx
|-- src/
|   |-- main.cpp
|   |-- app_logic.c
|   |-- creator_info.c
|   |-- student.c
|   |-- file.c
|   `-- analysis.c
|-- include/
|   |-- app_logic.h
|   |-- creator_info.h
|   `-- student.h
|-- data/
|   `-- data.txt
```

`main.cpp` 仅负责 EasyX 图形界面和 Windows 事件。
筛选、分页、统计、输入校验、链表、文件和排序等业务逻辑均由 C 语言模块实现。

三位制作者的院系、学号和姓名统一填写在 `src/creator_info.c` 中，
程序可通过侧边栏的“关于”按钮查看这些信息。

## Visual Studio 2026

1. 确认 EasyX 已安装到 Visual Studio 2026。
2. 在 Visual Studio 中选择“打开本地文件夹”。
3. 打开本文件夹，也就是包含 `CMakeLists.txt` 的目录。
4. 选择 CMake 预设 `vs2026-x64`。
5. 将启动项设为 `GradeSystem.exe`，然后按 `F5`。

命令行构建：

```powershell
cmake --preset vs2026-x64
cmake --build --preset vs2026-debug
```

生成的程序和运行数据位于：

```text
out/build/vs2026-x64/
```

程序使用 UTF-8 源码，并由 MSVC 以 UTF-8 编译。数据保存在 `data.txt`，保存前的旧数据会备份到 `backup.txt`。

`out/` 和 `.vs/` 是 Visual Studio/CMake 自动生成的缓存与构建目录，不属于课程设计源文件，
需要时会自动重新生成，因此未包含在提交内容中。
