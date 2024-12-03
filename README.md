# Vscode-GCC-N32g031
使用Vscode,GCC编译N32g031的开发环境

1、准备工具和资料：
Vscode 
Gcc(arm-non-eabi-gcc) 
EIDE扩展插件

2、nation 官方文档：
https://www.nationstech.com/developer/
N32G031系列GCC开发环境应用笔记

3.1开发环境一：Vscode+GCC+makefile(官方已配置路径)
直接解压官方文档，按官方操作在Vscode终端使用make编译工具。
注意修改编译器路径(在launch.json种的“miDebuggerPath”)

3.2开发环境二：Vscode+GCC+EDIE

3.2.1  参考官方设置GCC，添加扩展插件EDIE，设置EDID应用GCCl路径

3.2.2  在EDIE新建项目,设置项目名和项目路径

3.2.3  在芯片支持包选型 添加官方.pack开发包

3.3.4  在项目资源选项 添加官方源文件(新建虚拟文件夹，分类添加源文件和驱动文件，Gcc环境的启动文件，CM0内核文件)

3.3.5  在构建配置中选择GCC,链接脚本路径:n32g031_flash.ld(需放在项目根目录下)或者直接引用其他链接脚本路径（n32g031_flash.ld可以改名n32g031_flash.lds）

3.3.6  项目属性下的包含目录添加源文件路径和头文件路径

          1）库搜索目录可以依据全面的Driver 源文件情况酌情添加
          2）若Driver 源文件已经包含库文件，则不要添加，     
          3）若无Driver 源文件，则要添加库文件或者库，
          
3.3.7预处理宏定义使用默认的N32G031 USE_STDPERIPH_DRIVER


