# Pre-UrbanDesign (UrbanXTools)

## **介绍**
### 1. 主要功能
- 基于城市规划设计逻辑，借助算法设计，实现短时间内快速自动生成符合上位规划的城市设计方案；
- 从多专业的角度，即时对城市设计方案计算并生成评估结果。
- 为用户对城市设计方案的调整提供强有力的依据，大大减少方案评估反馈与修改之间的时间，提高设计效率；
### 2. 目标
- 高质量
- 可持续城市发展
### 3. 参与人员
- 杨滔、罗维祯、邓成汝、林旭辉
### 4. 合作单位
- 中国城市规划设计研究院——城市设计分院

## **演示**
### 1. 水管网直径最优计算

### 2. 空间结构交互性评估

### 3. 城市设计方案自动生成

### 4. 城市设计方案多维度评估


## **工具内容**

### 1. 设施计算
> Facility_CoverageArea
- **目的**：
- **输入**：
- **输出**：
- **样例展示**：

> Facility_ToNetwork
- **目的**：
- **输入**：
- **输出**：
- **样例展示**：

### 2. 空间句法计算

> Network_ClearRoadsData
- **目的**：
    - 清洗和分割所有道路曲线，处理情况包括：重叠、形状相同和无效曲线。
- **输入**：
    - 待清洗、分割的道路曲线
- **输出**：
    - 清洗并分割完成的道路曲线
- **样例展示**：

> Network_ClearSitesData
- **目的**：
    - 清洗所有地块曲线，处理情况包括：重叠、形状相同、非平面、非闭合地块曲线。
- **输入**：
    -  待清洗的地块曲线
- **输出**：
    - 清洗完成的道路曲线
- **样例展示**：

> Network_Computing
- **目的**：
    - 计算道路网络性质，包括按米制、按角度制的空间句法，可选择不同半径进行计算
    - 介数中心性(betweenness): 在一定范围内，找出网络中任意两点的最短经，并计算每段道路被经过的次数
    - 紧密中心性(closeness): 在一定范围内，从该点到沿最短路径的指定目标点所需的平均距离
- **输入**：
    - 需要计算的路网曲线
    - 计算半径
    - 是否需要标准化
- **输出**：
    - 米制 介数中心性
    - 米制 紧密中心性
    - 角度制 介数中心性
    - 角度制 紧密中心性
- **样例展示**：

> Network_RoadDensity
- **目的**：
    - 基于特定边界，计算路网密度
- **输入**：
    - 需要计算的路网曲线
    - 对应路网的边界线
- **输出**：
    - 道路网密度（数据）
    - 道路网密度（单位：km/km²）
    - 边界内容道路曲线
- **样例展示**：

> Network_SiteAccessibility
- **目的**：
    - 计算地块可达性
- **输入**：
    - 地块周边路网曲线
    - 周边路网曲线对应数值
    - 需要计算的地块曲线
- **输出**：
    - 由地块曲线围合而成的地块平面
    - 地块可达性得分
- **样例展示**：

### 3. 资源指标计算
> Resources_Energy
- **目的**：
    - 计算自生成设计方案里，每个建筑的能源消耗量
- **输入**：
    - Urban_SiteGeneratePlans 类
- **输出**：
    - 对应楼块的能源消耗量
- **样例展示**：

> Resources_Water
- **目的**：
    - 计算自生成设计方案里，每个建筑的水资源消耗量
- **输入**：
    - Urban_SiteGeneratePlans 类
- **输出**：
    - 对应楼块的水资源消耗量
- **样例展示**：

> Resources_Garbage
- **目的**：
    - 计算自生成设计方案里，每个建筑的固废产生量
- **输入**：
    - Urban_SiteGeneratePlans 类
- **输出**：
    - 对应楼块的固废产生量
- **样例展示**：

> Resources_EnergyCustom
- **目的**：
    - 根据建筑体块及功能，计算每个建筑的能源消耗量
- **输入**：
    - 建筑体块、及其对应的建筑功能
- **输出**：
    - 对应体块的能源消耗量
- **样例展示**：

> Resources_WaterCustom
- **目的**：
    - 根据建筑体块及功能，计算每个建筑的水资源消耗量
- **输入**：
    - 建筑体块、及其对应的建筑功能
- **输出**：
    - 对应体块的水资源消耗量
- **样例展示**：

> Resources_GarbageCustom
- **目的**：
    - 根据建筑体块及功能，计算每个建筑的固废产生量
- **输入**：
    - 建筑体块、及其对应的建筑功能
- **输出**：
    - 对应体块的固废产生量
- **样例展示**：

> Resources_Population
- **目的**：
    - 根据建筑体块，计算每个建筑的可容纳人口量
- **输入**：
    - 建筑体块
- **输出**：
    - 对应体块的容纳人口量
- **样例展示**：

### 4. 空间指标计算
> Spatial_Exposure
- **目的**：
    - 根据道路节点，计算建筑底商的空间曝光率，为商业选址提供空间数据支持
- **输入**：
    - 建筑体块、预设置的可视节点、是否标准化、可视半径、细分程度（该数值越高，结果越准确，计算速度越慢）
- **输出**：
    - 建筑基底轮廓线、轮廓线对应曝光率
- **样例展示**：

### 5. 自动生成
> Urban_DesignCalculator
- **目的**：
    - 计算在特定场地内，可容纳的建筑数量和楼层，以实现给定 FAR 和密度的目标
- **输入**：
    - 输入场地曲线
    - 输入建筑原型的平面线稿
    - 输入每一种建筑类型的层数范围
    - 输入目标容积率FAR
    - 输入目标建筑密度
- **输出**：
    - 可容纳的建筑数量
    - 可容纳的建筑楼层数
    - 现有地块FAR容积率
    - 现有地块建筑密度
- **样例展示**：

> Urban_DynamicSplit
- **目的**：
    - 使用Binary Partition Tree算法，基于容积率，对地块进行精确划分。
- **输入**：
    - 输入准备切分的场地曲线
    - 输入场地对应的目标面积或比例
    - 输入场地对应的优先等级
    - 输入场地边界框的可达性得分
    - 输入场地边界框的角度
    - 在动态切分时，是否改变角度
- **输出**：
    - 输出子地块边线
    - 输出子地块边界框
    - 输出子地块边界性得分
    - 输出子地块角度
    - 输出子地块ID
    - 输出Binary Partition Tree的可视化结果
- **样例展示**：

> Urban_ResidentialLimitation
- **目的**：
    - 输入场地、及所在城市，计算该场地可达到的最大容积率及建筑密度
- **输入**：
    - 输入准备进行计算的场地曲线
    - 输入城市序号，获得气象信息
    - 输入该场地能容纳的最大限高
    - 输入住宅层数高度，默认为3米
    - 输入住宅朝向角度，默认为0度
    - 输入住宅深度，默认为26米
- **输出**：
    - 输出场地可容纳的最大容积率
    - 输出场地可容纳的最大建筑密度
- **样例展示**：

> Urban_SiteParameter
- **目的**：
    - 基于道路、道路可达性得分及场地数据，形成自生成参数
- **输入**：
    - 输入道路曲线
    - 输入道路可达性得分
    - 输入场地曲线
- **输出**：
    - 输出 Urban_SiteParameter 类
- **样例展示**：

> Urban_SiteParameterExtra
- **目的**：
    - 调整地块参数（容积率、建筑密度等），设计参数调整功能
- **输入**：
    - 输入 Urban_SiteParameter 类
    - 输入场地对应的用地属性（R:0, C:1, GIC:2, M:3, W:4）
    - 输入场地对应的容积率FAR
    - 输入场地对应的建筑密度
    - 输入场地对应的混合度
    - 输入场地对应的建筑风格（住宅：风格0_行列式，风格1_点式|| 非住宅：风格0_点式，风格1_围合式，风格2_混合式 ）
    - 输入场地对应的朝向角度
- **输出**：
    - 输出 Urban_SiteParameter 类
- **样例展示**：

> Urban_SiteGeneratePlans
- **目的**：
    - 基于输入参数，建筑体块方案自动生成，得到生成结果
- **输入**：
    - 输入 Urban_SiteParameter 类
    - 输入所在城市序号
- **输出**：
    - 输出 Urban_SiteResult 类
    - 输出原始场地曲线（尚未切分）
    - 输出场地对应的容积率FAR
    - 输出场地对应的建筑密度
    - 输出场地对应的子地块曲线
    - 输出子地块的场地退线
    - 输出每个建筑对应的层数（curve）
    - 输出每个建筑对应的屋顶线 (curve)
    - 输出每个建筑对应的层数（int）
    - 输出每个建筑对应的体块 (brep)
    - 输出每个建筑对应的功能 (string)
- **样例展示**：

### 6. 水管网计算（Coming Soon）
<details>
<summary>水管网计算具体参数</summary>

> Water_InpFileToGeometry
- **目的**：
    - 读取inp文件并生成Rhino中的几何图形
- **输入**：
    - pManager.AddTextParameter("filePath", "inp", "", GH_ParamAccess.item);
    - pManager.AddNumberParameter("tolerance", "tolr", "tolerance for simplifing the pipe links", GH_ParamAccess.item, DocumentTolerance() * 1000);
- **输出**：
    - pManager.AddPointParameter("Junctions", "JNodes", "", GH_ParamAccess.list);
    - pManager.AddPointParameter("Reservoirs", "RNodes", "", GH_ParamAccess.list);
    - pManager.AddCurveParameter("Pipes", "PLinks", "", GH_ParamAccess.list);
- **样例展示**：

> Water_CalculateSiteDemand
- **目的**：
    - 根据泰森多边形计算每个节点的需水量
- **输入**：
    - pManager.AddCurveParameter("Blocks", "curves", "Blocks of land plan", GH_ParamAccess.list);
    - pManager.AddTextParameter("LanduseType", "type", "The type of all the landuse", GH_ParamAccess.list);
    - pManager.AddNumberParameter("TotalDemandByType", "demand", "The total water demand for each type", GH_ParamAccess.list);
- **输出**：
    - pManager.AddNumberParameter("SiteWaterDemand", "siteDemand", "The water demand for each site.(LPS)", GH_ParamAccess.list);
- **样例展示**：

> Water_NetworkOptimization
- **目的**：
    - 算法优化供水管网各管段参数
- **输入**：
    - pManager.AddPointParameter("junctions", "pts", "Jucntion nodes without water source", GH_ParamAccess.list);
    - pManager.AddCurveParameter("links", "lks", "All the water pipelines", GH_ParamAccess.list);
    - pManager.AddPointParameter("sources", "sources", "", GH_ParamAccess.list);
    - pManager.AddNumberParameter("diameters", "d", "", GH_ParamAccess.list);
    - pManager.AddNumberParameter("pipeCost", "c", "", GH_ParamAccess.list);
    - pManager.AddRectangleParameter("Boundary", "box", "", GH_ParamAccess.item);
    - pManager.AddCurveParameter("PlanSite", "polyline", "Polylines for all the site", GH_ParamAccess.list);
    - pManager.AddNumberParameter("SiteWaterDemand", "siteDemand", "The water demand for each site.(LPS)", GH_ParamAccess.list);
- **输出**：
    - pManager.AddNumberParameter("flowRate", "f", "", GH_ParamAccess.list);
    - pManager.AddNumberParameter("diameter", "f", "", GH_ParamAccess.list);
    - pManager.AddCurveParameter("pathCurves", "c", "", GH_ParamAccess.list);
    - pManager.AddCurveParameter("Cell", "c", "", GH_ParamAccess.list);
    - pManager.AddNumberParameter("Demand", "LPS", "", GH_ParamAccess.list);
- **样例展示**：

</details>






## **许可证**
### ***GNU General Public License v.3***
*Copyright (C) 2020  Tao Yang, Weizhen Luo, Chengru Deng, Xuhui Lin*

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details.
