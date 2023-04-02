#### 1. 准备所需要的工具：Visual Studio 2022，cmake
#### 2. 准备需要的库(wxWidgets是必须的库，其他需要的话需要在CMakeLists.txt中将OFF改为ON)
<table>
<tr>
<td>库名</td><td>下载链接</td><td>配置流程</td><td>cmake路径设置(添加对应语句在opensph源文件CMakeLists.txt中对应库的findpackage指令前)</td>
</td>

<tr>
<td>wxWidgets(建议下载windows installer文件)</td><td><a href="https://www.wxwidgets.org/downloads/">wxWidgets下载地址</a></td><td>以windows installer文件为例<br>1. 将exe文件安装到c:\Temp路径下(建议将所有库统一安装到此目录下)<br>2.在库文件夹中的build\msw文件夹中找到wx_vc17.sln文件并打开<br>3. 选择release然后生成解决方案</td><td>

```json
SET(wxWidgets_LIB_DIR "C:/Temp/wxWidgets-3.2.2.1/lib/vc_x64_lib")
SET(wxWidgets_ROOT_DIR "C:/Temp/wxWidgets-3.2.2.1")
```
</td>
</tr>

<tr>
<td>oneTBB</td><td><a href="https://github.com/oneapi-src/oneTBB">oneTBB下载地址</td><td>直接用cmake进行配置</td><td>

```json
SET(Tbb_INCLUDE_DIR "include文件夹的地址")
SET(Tbb_tbb_LIBRARY_RELEASE "tbb12.lib文件的地址")
SET(Tbb_tbbmalloc_LIBRARY_RELEASE "tbbmalloc.lib文件的地址")
```
</td>
</tr>

<tr>
<td>Eigen</td><td><a href="https://gitlab.com/libeigen/eigen/-/releases/3.4.0">Eigen下载地址</td><td>不需要配置</td><td>

```json
SET(EIGEN_INCLUDE_DIR "库的文件夹地址")
```
</td>
</tr>

<tr>
<td>ChaiScript</td><td><a href="https://github.com/ChaiScript/ChaiScript/releases">ChaiScript下载地址</td><td>不需要配置</td><td>

```json
SET(EIGEN_INCLUDE_DIR "include文件夹的地址")
```
将原本的SET语句注释掉
</td>
</tr>
</table>
#### 3.使用cmake配置opensph(将缺的dll文件放到生成opensph.exe所在的文件夹下)
