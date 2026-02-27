# DEM数据处理教程

## 概述
本教程介绍如何使用ArcGIS Pro处理数字高程模型（DEM）数据，为水文分析做准备。

## 学习目标
- 掌握DEM数据下载与导入
- 学习DEM预处理技术（投影转换、镶嵌、裁剪）
- 理解填洼处理的重要性
- 实践DEM数据质量检查

## 数据集
- **数据源**：SRTM 30m DEM（USGS EarthExplorer）
- **研究区域**：长江中游某流域
- **数据格式**：GeoTIFF (.tif)

## 处理步骤

### 1. 数据导入
```python
import arcpy
from arcpy import env

# 设置工作空间
env.workspace = "C:/data/dem"

# 列出所有DEM文件
dem_files = arcpy.ListRasters("*.tif")
print(f"找到 {len(dem_files)} 个DEM文件")
```

### 2. 投影转换
将DEM数据转换为统一坐标系（如CGCS2000）。

### 3. 数据镶嵌
合并多个DEM图幅，创建连续覆盖区域。

### 4. 填洼处理
消除DEM中的凹陷区域，确保水流连续性。

## 结果验证
- 检查处理后的DEM无异常值
- 确认水流方向计算正确
- 验证河网提取结果合理

## 扩展练习
1. 尝试使用不同分辨率的DEM数据
2. 比较不同填洼算法的效果
3. 探索自动化批处理脚本

---

*最后更新：2026年2月27日*
*所属项目：gis-arcgis-tutorials*
