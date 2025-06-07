---
icon: fas fa-tag
order: 1
---

## Downloads
<!-- (https://github.com/Piecer-plc/piecer-plc) -->
[**CROSS2OH**](https://github.com/CROSS2OH/CROSS2OH.github.io)
## Run CROSS2OH

- Step 1

This tool runs in a Linux environment and requires prior configuration of the [OHOS SDK](https://gitee.com/openharmony-sig/tpc_c_cplusplus/blob/master/lycium/doc/ohos_use_sdk/OHOS_SDK-Usage.md) and downloading the [Lycium](https://gitcode.com/openharmony-sig/tpc_c_cplusplus) cross-compilation tool.
```java
git clone https://gitcode.com/openharmony-sig/tpc_c_cplusplus.git
```
- Step 2


Download and configure CROSS2OH's dependencies
```java
//The list of dependencies for CROSS2OH
mysql
CTags
curl
cmake
gcc, cmake, make, pkg-config, autoconf, autoreconf, automake
...(toolchains)
//eg:
sudo apt install cmake
```
<span style="color: #2697fa; font-weight: bold;">Note:</span> The installation path of CTags must be explicitly recorded, as CROSS2OH requires this path to be configured for proper functionality during tool execution.
- Step 3

<!-- 配置path信息 -->
Define the values of the following variables in PathUtil.java

```java
    // The output path for detected CPI issues.
    public static final String RESULTPATH = "aa/bb/cc";
    // The tpc_c_cplusplus/thirdparty directory serves as the execution path for the cross-compilation process.
    public static final String THIRDPARTY_PATH = "aa/bb/cc/tpc_c_cplusplus/thirdparty";
    // The installation directory of the Lycium repository.
    public static final String PATH = "aa/bb/cc/tpc_c_cplusplus";
    // OHOS_SDK_PATH
    public static final String OHOS_SDK_PATH = "aa/bb/cc/ohos_sdk_your_version/linux";
    // The path to Lycium’s core execution script build.sh.
    public static final String SCRIPT_PATH = "aa/bb/cc/tpc_c_cplusplus/lycium/build.sh";
    // The path of CTags
    public static final String CTAGS_PATH = "aa/bb/cc/ctags-your_version/ctags";
    // The output path to generate CTags tag file.
    public static final String CTAGS_OUTPUTFILEPATH = "aa/bb/cc/dd";
    // The path for copying source files during patch generation.
    public static final String TEMPDIRECTORYPATH = "aa/bb/cc/ee";
```
- Step 4

Package the configured CROSS2OH into a JAR file.
```java
mvn clean package
```
- Step 5

Provide one or more download links to GitHub-hosted C/C++ libraries with specified version tags.
```java
//example
//https://github.com/zsummer/log4z/archive/refs/tags/v3.4.0.zip
```
- Step 6

Run.
```java
java -jar CROSS2OH-1.0-SNAPSHOT-jar-with-dependencies.jar https://github.com/zsummer/log4z/archive/refs/tags/v3.4.0.zip
```
Finally, CROSS2OH downloads the provided compressed package, completes the detection of CPI issues, applies fixes to the identified problems, and generates corresponding *.patch files, which are stored in the configured THIRDPARTY_PATH.
<div id="d-help-win" class="d-help-win" >
    <div id="win-title">Help
        <span id="d-help-colse" clss="close_2" class="close_2">
            × 
        </span>
    </div>
    <div id="win-content">
        <!-- 我们提供了xxx数据集。
        1.
        2.
        3.
        4.
        查看详细复现结果：
        动图！ -->
        <!-- <img src="/assets/images/Pipeline-Bug.gif"> -->
    </div>
</div>
 <div id="d-help-win" class="d-help-win" style="display: none;">
      <div id="win-title">Help
          <span id="d-help-colse" clss="close_2" class="close_2">
              × 
          </span>
      </div>
      <div id="win-content">
          <blockquote class="prompt-tip"><div><p> xxx</p></div></blockquote>
          <!-- <div>
              <ol>
                  <li>Go to <strong><font color="#FF0000">Empirical Findings</font></strong> page</li>
                  <li>Select a bug and click on <strong><font color="#FF0000">reproduce result link</font></strong>.</li>
                  <li>You can find the reproduction results of each version and the related reproduction code.</li></ol>
          </div> -->
          <!-- <img src="/assets/images/Pipeline-Bug.gif" alt="avatar"> -->
      </div>
  </div>