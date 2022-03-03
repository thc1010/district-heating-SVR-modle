# district-heating-SVR-modle
利用支持向量机和时差先惯性分析建立模型 Build district heating model with Svr and different time offset analysis

模型简介：
建立的是一个二级网供热模型，包含三个部分，一是换热站水力模型，二是换热站热力模型，三是单元调控模型

换热站水力模型：根据流量，最小用户压力来计算水泵能耗，在实际工程中可以指导水泵的运行方式，目的热力站能够有效的将热量送到用户端
换热站热力模型：根据室温，室外温度，流量来计算一次网的供热量或者热耗，在实际工程中指导换热站的供热运行方式，目的是确定换热站能够供给足够的热量，使热用户室温满足
单元调控模型：根据室外温度，单元回水温度，室内温度等数据来计算单元供回水压差，在实际工程中可以确定建筑单元的室温得到满足，根本目的是通过单元阀门来进行单元之间热量的分配


算法简介：
改模型建立主要用到 SVR POLY核函数，和自研的核函数
数据维度处理，空值用到的是 随机森林和插值法，数据维度选取时，利用时差相关性分析。
模型参数寻优目前是网格搜索法



Model introduction: established a secondary district heating system model which including three parts . one is the hydraulic model of the heat-exchange station, the other is the thermal model of the heat-exchange station, and the third is the building unit control model

The hydraulic model of the heat exchange station: Calculate the energy consumption of the pump according to the flow rate and the minimum user pressure. In the actual project, it can guide the operation mode of the pump, and the target heat station can effectively send the heat to the user. The outdoor temperature and flow rate are used to calculate the heat supply or heat consumption of the primary network, and guide the heat supply operation mode of the heat exchange station in the actual project. : Calculate the pressure difference between the supply and return water of the unit according to the outdoor temperature, unit return water temperature, indoor temperature and other data. In the actual project, it can be determined that the room temperature of the building unit is satisfied. The fundamental purpose is to distribute the heat between the units through the unit valve.

Introduction to the algorithm: The SVR POLY kernel function and the self-developed kernel function are mainly used in the establishment of the modified model for data dimension processing. Random forest and interpolation method are used for null values. When the data dimension is selected, the time difference correlation analysis is used. Model parameter optimization is currently a grid search method
