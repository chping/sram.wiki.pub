# SRAM Metrics Index

差分 6T SRAM 是本文档的基线。各页给出定义、仿真与硅实测、评价方法、DTCO 用途及原文定位。配图中的曲线为无数值示意。

「已核验」表示已复核本文口径、提取方法及关键出处。直接硅测、代理指标与公开实测缺口见各页。统一查阅[各页参考文献](../README.md#参考文献)。

## Device

| 指标 | 文档 | 调研状态 | 人工校对 |
|---|---|---|---|
| Vth & Vth mismatch | [Vth.md](Device/Vth.md) | 已核验 | -·- |
| Ion | [Ion.md](Device/Ion.md) | 已核验 | -·- |
| Ioff | [Ioff.md](Device/Ioff.md) | 已核验 | -·- |
| Isat | [Isat.md](Device/Isat.md) | 已核验 | -·- |

## Bitcell

| 指标 | 文档 | 调研状态 | 人工校对 |
|---|---|---|---|
| Read Current | [Read_Current.md](Bitcell/Read_Current.md) | 已核验 | 已完成 |
| RSNM | [RSNM.md](Bitcell/RSNM.md) | 已核验 | -·- |
| WTV | [WTV.md](Bitcell/WTV.md) | 已核验 | -·- |
| WM (Write Margin) | [WM.md](Bitcell/WM.md) | 已核验 | -·- |
| WSNM | [WSNM.md](Bitcell/WSNM.md) | 已核验 | -·- |
| DRV | [DRV.md](Bitcell/DRV.md) | 已核验 | -·- |
| HSNM | [HSNM.md](Bitcell/HSNM.md) | 已核验 | -·- |
| Cell Area | [Cell_Area.md](Bitcell/Cell_Area.md) | 已核验 | -·- |
| Cell Height & Width | [Cell_Height_Width.md](Bitcell/Cell_Height_Width.md) | 已核验 | -·- |
| CELL_BL RC | [CELL_BL_RC.md](Bitcell/CELL_BL_RC.md) | 已核验 | -·- |
| CELL_WL RC | [CELL_WL_RC.md](Bitcell/CELL_WL_RC.md) | 已核验 | -·- |
| CELL_R_VDD & CELL_R_VSS | [CELL_R_VDD_CELL_R_VSS.md](Bitcell/CELL_R_VDD_CELL_R_VSS.md) | 已核验 | -·- |
| Standby Leakage | [Standby_Leakage.md](Bitcell/Standby_Leakage.md) | 已核验 | 已完成 |

## Subarray

| 指标 | 文档 | 调研状态 | 人工校对 |
|---|---|---|---|
| Read Develop Time | [Read_Develop_Time.md](Subarray/Read_Develop_Time.md) | 已核验 | -·- |
| RD (Read Delay) | [Read_Delay.md](Subarray/Read_Delay.md) | 已核验 | -·- |
| RE (Read Energy) | [Read_Energy.md](Subarray/Read_Energy.md) | 已核验 | -·- |
| Write Time | [Write_Time.md](Subarray/Write_Time.md) | 已核验 | -·- |
| WD (Write Delay) | [Write_Delay.md](Subarray/Write_Delay.md) | 已核验 | -·- |
| WE (Write Energy) | [Write_Energy.md](Subarray/Write_Energy.md) | 已核验 | -·- |
| BL RC | [BL_RC.md](Subarray/BL_RC.md) | 已核验 | -·- |
| WL RC | [WL_RC.md](Subarray/WL_RC.md) | 已核验 | -·- |
| R_VDD & R_VSS | [R_VDD_R_VSS.md](Subarray/R_VDD_R_VSS.md) | 已核验 | -·- |
| WL Slew | [WL_Slew.md](Subarray/WL_Slew.md) | 已核验 | -·- |
| BL Leakage | [BL_Leakage.md](Subarray/BL_Leakage.md) | 已核验 | -·- |

## Peripheral

| 指标 | 文档 | 调研状态 | 人工校对 |
|---|---|---|---|
| SA Offset | [SA_Offset.md](Peripherial/SA_Offset.md) | 已核验 | -·- |
| SA Decision Threshold | [SA_Decision_Threshold.md](Peripherial/SA_Decision_Threshold.md) | 已核验 | -·- |
| SA Standby Current | [SA_Standby_Current.md](Peripherial/SA_Standby_Current.md) | 已核验 | -·- |

## Macro

| 指标 | 文档 | 调研状态 | 人工校对 |
|---|---|---|---|
| EDAP (Energy Delay Area Product) | [EDAP.md](Macro/EDAP.md) | 已核验 | -·- |
| EDP (Energy Delay Product) | [EDP.md](Macro/EDP.md) | 已核验 | -·- |
| Tree Delay/Energy % | [Tree_Delay_Energy_Percent.md](Macro/Tree_Delay_Energy_Percent.md) | 已核验 | -·- |
| Interconnect Length & Area | [Interconnect_Length_Area.md](Macro/Interconnect_Length_Area.md) | 已核验 | -·- |
