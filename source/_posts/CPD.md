---
title: 欧洲CPD调研
date: 2025-01-16 10:30:00
tags: [技术, 电子, 汽车]
categories: [调研]
---

# Euro NCAP CPD（Child Presence Detection） 市场与技术调研报告

***

## 一、 引言

儿童被遗留在车内导致的伤亡事故在全球范围内持续发生，尤其在高温或低温环境下，风险极高。传统的驾驶员提醒机制（如钥匙提醒、仪表提示）在实际使用中存在明显不足，无法有效避免事故发生。

在此背景下，Euro NCAP 将 **CPD（Child Presence Detection，儿童存在检测）** 纳入其车辆安全评估路线图，旨在通过自动化检测与主动报警机制，降低儿童遗留车内的安全风险。

对于 Tier1 / Tier2 技术部门而言，CPD 不仅是合规与评分问题，更是一个涉及传感器、算法、系统集成与测试能力的综合技术课题。

***

## 二、 Euro NCAP CPD 背景与体系定位

### 2.1 CPD 定义

CPD（Child Presence Detection）是指在驾驶员离车、车辆关闭状态下，系统能够自动检测车内是否仍存在儿童或婴幼儿，并在检测到目标后触发警示或报警机制的功能。

### 2.2 CPD 在 Euro NCAP 中的定位

- CPD 属于 **Safety Assist（安全辅助）** 评价范畴  
- 当前主要以 **加分项（Incentive / Reward）** 形式存在  
- 随着技术成熟度提升，未来可能演进为：
  - 高权重评分项  
  - 甚至成为五星评级的重要隐性门槛
>根据euro-ncap-cpd-test-and-assessment-protocol-v13.pdf文件中2.1部分：
2.1 Sensing 
2.1.1 
Direct sensing 
The ability to detect the absolute presence of a human inside the vehicle by means of 
tracking heartbeat, respiration, movement, or any other sign of life. Direct sensing may or 
may not allow categorisation and localisation of the subject(s).  
2.1.2 
Indirect sensing 
The ability to derive the potential presence of a subject or object inside the car based on 
logic using information such as door opening, pressure or capacitive sensing etc. Indirect 
sensing does not distinguish between live persons or objects. From 2025 onwards, indirect 
sensing system will NOT be rewarded by Euro NCAP.
> >2.1 感知
2.1.1 直接感知
通过跟踪心跳、呼吸、运动或任何其他生命体征来检测车内绝对存在人类的能力。直接感知可能允许也可能不允许对被感知对象进行分类和定位。
2.1.2 间接感知
基于逻辑（例如使用车门开关、压力或电容传感等信息）推断车内可能存在人或物体的能力。间接感知不区分活人还是物体。从2025年起，间接感知系统将不会获得Euro NCAP奖励。
***

### 2.3 推动 CPD 的核心动因

- 真实事故驱动（儿童被遗忘在车内）
- 欧盟对车辆主动安全持续加码
- 毫米波雷达等非接触式感知技术成熟
- OEM 在安全差异化与 NCAP 评分上的竞争需求

***

## 三、 Euro NCAP CPD 功能与测试关注点

### 3.1 基本功能要求

CPD 系统需具备以下基本能力：

- 在发动机关闭、驾驶员离车后持续工作  
- 能够检测：
  - 新生儿
  - 幼童
  - 睡眠或静止状态下的儿童  
- 在检测到儿童存在时触发清晰、明确的警示：
  - 车内声光报警
  - 车外提示
  - 远程通知（如手机 App）

### 3.2 关键测试关注点

- 深睡眠、低运动状态下的检测能力  
- 误报与漏报控制  
- 对遮挡、车内结构、多径环境的鲁棒性  
- 系统响应时间与稳定性  

这些关注点对技术路线选择具有直接约束作用。

***

## 四、 CPD 技术路线分析

### 4.1 技术路线选择的基本原则

CPD 技术路线选择需同时满足：

- 覆盖 Euro NCAP 重点测试场景（尤其是低运动、深睡眠）
- 具备量产可行性与长期演进能力
- 可通过软件与算法升级应对规则变化
- 在成本、复杂度与性能之间具备工程可接受性

CPD 技术路线的评估应基于**长期技术投入回报**，而非短期可实现性。

***

### 4.2 主推荐技术路线：毫米波雷达 CPD 方案
>https://zhuanlan.zhihu.com/p/12376672021

#### 4.2.1 主流技术原理与能力边界

毫米波雷达 CPD 方案基于：

- 微多普勒效应检测呼吸引起的胸腔微位移  
- 在目标无明显肢体运动情况下识别生命体征  
- 不依赖光照条件，可穿透衣物、毛毯与儿童座椅  

该能力使毫米波雷达成为**当前唯一可在深度睡眠儿童场景下稳定工作的单一传感器方案**。

***

#### 4.2.2 工程实现优势(毫米波雷达方案)

- **软件定义能力强**  
  核心性能可通过算法持续优化，适应 Euro NCAP 测试演进  

- **系统集成灵活**  
  可独立工作，也可与摄像头、座椅传感器融合  

- **测试一致性高**  
  易与标准化 CPD Dummy 配合，利于算法验证与复现  

***

#### 4.2.3 工程挑战与风险点(毫米波雷达方案)

- 低 SNR 场景下算法鲁棒性要求极高  
- 易受车内多径、金属结构影响  
- 对安装位置与标定流程敏感  
- 算法开发与验证周期较长  

***

### 4.3 单一压力 / 重量传感方案

存在以下根本性问题：

- 难以区分儿童与非生命体物体  
- 无法检测呼吸等生命体征  
- 在 Euro NCAP 低运动测试场景中风险极高  
>该方法属于间接感知，无法用此系统来获得Euro NCAP评分
***

## 五、 CPD Dummy 与测试能力建设

### 5.1 CPD Dummy 的战略意义

CPD Dummy 不仅是测试工具，更是：

- 算法开发与验证基础  
- 与 OEM 技术沟通的重要技术背书  
- 应对 Euro NCAP 测试不确定性的关键手段  

在标准尚未完全冻结阶段，Dummy 能力可显著降低后期认证风险。

***

### 5.2 CPD Dummy 的关键工程技术指标

| 维度 | 工程要求 |
|----|----|
| 呼吸模拟 | 低频、小幅度、稳定可控 |
| 雷达等效特性 | 与真实儿童 RCS / 微多普勒一致 |
| 低运动能力 | 长时间仅保持呼吸状态 |
| 材料特性 | 不引入雷达伪影 |
| 姿态支持 | 仰卧、侧卧、蜷缩 |
| 年龄覆盖 | 新生儿 / 幼童 |

>https://www.child-presence-detection.org/

 Human Factors and Technology Integration: All relevant technologies and their integration with human factors, including:
- Realistic Breathing Simulation: Simulates breathing movements to enhance detection accuracy
- Real-Skin-Tissue-Technology: Ensures no unintended radar interference
- Radar Signature Simulation: Provides accurate radar feedback to detect the presence of children
- Infrared and Camera Response: Skin materials with realistic response to infrared and camera detection systems
- Customizable Movement Patterns: Simulates various child behaviors and postures, such as waking up, light sleep, and deep sleep
CPD 项目在这些假人（仿真人体模型）的开发和测试方面取得了显著进展。关键里程碑包括：

- 联盟建设：建立一个涵盖所有相关利益相关方的联盟。

- 数据评估：评估真实数据，包括传感器数据和运动模式。

- 全面文献综述：对医疗技术相关出版物开展系统、深入的文献综述。

- 测量研讨会：组织测量研讨会，并开发一套将分发到全球的假人模型。

- 标准化工作：在综合性文件中描述相关假人的关键属性，作为制定国际标准的基础。

- 人体因素与技术集成：整合所有相关技术并结合人体因素，具体包括：

  - 逼真的呼吸模拟：模拟呼吸运动，以提高检测精度；

  - 真实皮肤组织技术：确保不会对雷达产生非预期的干扰；

  - 雷达特征模拟：提供准确的雷达反馈，用于检测儿童的存在；

  - 红外与摄像头响应：皮肤材料对红外和摄像头检测系统具有真实的响应特性；

  - 可定制的运动模式：模拟多种儿童行为和姿态，例如清醒、浅睡和深睡。
***

### 5.3 CPD Dummy 在算法开发中的作用

- 支撑灵敏度与误报阈值调优  
- 验证不同安装位置与车内结构影响  
- 提前覆盖深睡眠等极限测试场景  

Dummy 能力成熟度直接影响算法开发效率与稳定性。

***

### 5.4 测试与验证能力建设建议


- 通过自研或深度合作方式掌握 CPD Dummy  
- 建立内部 CPD 专用测试环境  
- 将 Dummy 测试作为算法迭代的常规手段  

> 自主测试能力有助于提升与 OEM 及第三方机构沟通中的技术主动权。

***

### 5.5 标准化趋势与前瞻

- CPD Dummy 正从项目制向标准化演进  
- 有望成为未来 ISO / UNECE 标准基础  
- 提前介入有助于抢占技术与话语权先机  

***

### 5.6 本章结论

- CPD Dummy 是 CPD 技术体系的基础设施  
- Dummy 能力决定算法可信度与测试成功率  
- 建议将 Dummy 与测试能力建设纳入整体技术路线规划  

***

## 六、 市场与产业现状概览（简要）

- OEM：高端品牌率先导入 CPD，逐步下沉  
- Tier1：雷达与算法能力成为核心竞争点  
- 测试机构：CPD 测试能力仍在建设中  

***

## 七、 发展趋势与主要挑战

### 技术趋势
- 雷达灵敏度持续提升  
- 多传感器融合增强鲁棒性  

### 主要挑战
- 深睡眠场景检测可靠性  
- 测试方法与 Dummy 尚未完全统一  

***

## 八、 结论与建议

- CPD 是 Euro NCAP 中具备战略意义的安全功能  
- 毫米波雷达是当前最具长期价值的技术路线  
- CPD Dummy 与测试能力是关键技术护城河  
- 建议提前布局，以应对未来评分权重提升与标准冻结风险  

***
