# 虚拟机械试验室

```
注：
    1、建议浏览电脑版网页以查看完整内容，目前仅电脑版可查看路线图和使用目录功能；
    2、本页面含有动图，图片总大小约为 15 MB，请耐心等待加载。
```

  - [介绍](#介绍)
  - [下载地址](#下载地址)
  - [安装教程](#安装教程)
  - [使用说明](#使用说明)
  - [路线图及进度](#路线图及进度)
  - [界面截图](#界面截图)
    - [主程序界面](#主程序界面)
      - [启动界面](#启动界面)
      - [组件界面](#组件界面)
      - [关于界面](#关于界面)
    - [工具箱界面](#工具箱界面)
      - [载荷谱处理界面](#载荷谱处理界面)
      - [常数查询界面](#常数查询界面)
      - [单位换算界面](#单位换算界面)
      - [文件浏览器界面](#文件浏览器界面)
      - [三维模型浏览器界面](#三维模型浏览器界面)
    - [设置界面](#设置界面)
      - [性能设置界面](#性能设置界面)
  - [致谢](#致谢)


## 介绍
    
**虚拟机械试验室**旨在作为机械设计工程师的得力工具，帮助工程师快速进行初步零件参数计算、建立机械系统概念模型、搭建详细模型并对系统强度和性能进行仿真。
由于本人技术和精力有限，本软件将长期处于仅能帮助加速进行前期概念模型设计的状态，暂无法取代其他专业软件。
    
**下载使用前请先查看并同意[【许可协议】](Licenses/)**。

## 下载地址

>尚未发布。

## 安装教程

>待做。

## 使用说明

>待做。

## 路线图及进度

>图中带 * 的为未完成项。

```mermaid
graph LR
    VML((*虚拟机械试验室))
    VML --> Basic(*底层)
        Basic --> GUI(*用户界面)
        Basic --> ApplicationArchitecture(*程序架构)
        Basic --> CalculateFunctions(*计算函数)
            CalculateFunctions --> SimilarityCalculateFunction(*相似度计算函数)
            CalculateFunctions --> ITToleranceClc(*IT公差计算)
            CalculateFunctions --> FitToleranceClc(*配合公差计算)
            CalculateFunctions --> SingleGearClcFunc(*单齿轮计算函数)
                GearMaterialDataBase --> SingleGearClcFunc
                GearCutterDataBase --> SingleGearClcFunc
                ITToleranceClc --> SingleGearClcFunc
            CalculateFunctions --> GearPairClcFunc(*齿轮副计算函数)
                GearMaterialDataBase --> GearPairClcFunc
                PreferredNumberDataBase --> GearPairClcFunc
                SingleGearClcFunc --> GearPairClcFunc
            CalculateFunctions --> PlanetaryGearClcFunc(*行星齿轮副计算函数)
                GearPairClcFunc --> PlanetaryGearClcFunc
            CalculateFunctions --> SplineClcFunc(*花键计算函数)
                ShaftMaterialDataBase --> SplineClcFunc
                ITToleranceClc --> SplineClcFunc
                FitToleranceClc --> SplineClcFunc
        Basic --> DataBase(*数据库)
            DataBase --> MaterialDataBase(*材料数据库)
                MaterialDataBase --> ShaftMaterialDataBase(*轴材料数据库)
                MaterialDataBase --> GearMaterialDataBase(*齿轮材料数据库)
                MaterialDataBase --> OilMaterialDataBase(*润滑油材料数据库)
            DataBase --> StandardParameterDataBase(*标准参数数据库)
                StandardParameterDataBase --> GearCutterDataBase(*齿轮刀具数据库)
                StandardParameterDataBase --> PreferredNumberDataBase(*优先数数据库)
    VML --> ToolKit(*工具箱)
        ToolKit --> Reference(*查询)
            Reference --> ConstantsReference(常数查询)
            Reference --> ITToleranceReference(*IT公差查询)
                ITToleranceClc --> ITToleranceReference
            Reference --> FitToleranceReference(*配合公差查询)
                FitToleranceClc --> FitToleranceReference
        ToolKit --> Conversion(*换算)
            Conversion --> UnitsConversion(单位换算)
            Conversion --> HardnessConversion(*硬度换算)
        ToolKit --> Browser(*浏览器)
            Browser --> FileBrowser(文件浏览器)
            Browser --> 3DModelBrowser(*三维模型浏览器)
        ToolKit --> Others(*其他)
            Others --> LoadSpectrumProcess(*载荷谱处理)
            Others --> SimilarityCalculate(*相似度计算)
                SimilarityCalculateFunction --> SimilarityCalculate
    VML --> Modules(*组件)
        Modules --> SingleGearModule(*单圆柱渐开线齿轮)
            SingleGearClcFunc --> SingleGearModule
        Modules --> GearPairModule(*圆柱渐开线齿轮副)
            GearPairClcFunc --> GearPairModule
        Modules --> PlanetaryGearModule(*圆柱渐开线行星齿轮副)
            PlanetaryGearClcFunc --> PlanetaryGearModule
        Modules --> SplineModule(*花键)
            SplineClcFunc --> SplineModule
        Modules --> InterferenceFitModule(*过盈配合)
        Modules --> ShaftModule(*轴)
        Modules --> BearingModule(*轴承)
        Modules --> Bolts(*螺栓)
    VML --> System(*系统)
    VML --> Acoustic(*声学)
```

## 界面截图

### 主程序界面

#### 启动界面
![启动界面](RepositoryResources/StartupImage.png)

#### 组件界面
![组件界面](RepositoryResources/ModulesPageImage.jpg)

#### 关于界面
![关于界面](RepositoryResources/AboutImage.png)

### 工具箱界面

#### 载荷谱处理界面
![载荷谱处理界面](RepositoryResources/LoadSpectrumProcessImage.gif)

#### 常数查询界面
![常数查询界面](RepositoryResources/ConstantsReferenceImage.gif)

#### 单位换算界面
![单位换算界面](RepositoryResources/UnitConversionImage.gif)

#### 文件浏览器界面
![文件浏览器界面](RepositoryResources/FileBrowserImage.gif)

#### 三维模型浏览器界面
![三维模型浏览器界面](RepositoryResources/ModelBrowserImage.gif)
 
### 设置界面

#### 性能设置界面
![性能设置界面](RepositoryResources/PerformanceSettingImage.png)

## 致谢

1. 感谢[@1357310795](https://github.com/1357310795)同学对提出无数低级问题的我的耐心指教。
2. 感谢全世界开源软件贡献者们的无私奉献。