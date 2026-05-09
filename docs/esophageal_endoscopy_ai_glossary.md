# 食管内镜手术 AI 风险预警系统术语表

> 适用场景：食管 ESD / POEM 术中风险预警系统研发。  
> 核心目标：帮助研发、临床、产品和注册团队统一术语，理解内镜视频、EUS、多普勒、CT/CTA、AI 图像处理和医疗软件产品化之间的关系。

---

## 1. 影像与设备术语

| 术语 | 英文/全称 | 简要解释 | 在本项目中的作用 |
|---|---|---|---|
| CT | Computed Tomography | 计算机断层扫描。 | 用于观察食管、纵隔、肺、主动脉、心脏等整体解剖结构。 |
| 增强 CT | Contrast-enhanced CT | 注射造影剂后的 CT。 | 更清晰显示血管、肿瘤和脏器边界。 |
| CTA | CT Angiography | CT 血管成像。 | 用于重建主动脉、左胃动脉、食管周围血管等术前血管地图。 |
| CTV | CT Venography | CT 静脉成像。 | 用于观察奇静脉、半奇静脉、食管静脉等静脉系统。 |
| MRI | Magnetic Resonance Imaging | 磁共振成像。 | 软组织显示较好，但在食管术前血管导航中通常不如 CT/CTA 直接。 |
| EUS | Endoscopic Ultrasound | 超声内镜，内镜头端带有超声探头。 | 观察食管壁层次、肌层、壁外血管和邻近结构。 |
| B-mode EUS | Brightness Mode Ultrasound | 灰阶超声图像。 | 显示食管壁结构和壁外解剖关系。 |
| Doppler | Doppler Ultrasound | 多普勒超声。 | 判断局部是否存在血流、血流方向和血流强弱。 |
| Color Doppler | 彩色多普勒 | 用颜色显示血流方向和区域。 | 辅助确认可疑血管区域是否有血流。 |
| Power Doppler | 能量多普勒 | 对低速、小血流更敏感。 | 适合发现小血管或低速血流。 |
| PW Doppler | Pulsed Wave Doppler | 脉冲多普勒。 | 定点测量血流速度和波形。 |
| H-Flow | High-definition Flow | 某些 EUS 系统的高敏血流显示模式。 | 可用于显示小血管和低速血流。 |
| WLI | White Light Imaging | 白光内镜图像。 | 第一版 AI 系统的主要视频输入。 |
| NBI | Narrow Band Imaging | 窄带成像。 | 增强黏膜表面和浅表血管显示。 |
| BLI | Blue Light Imaging | 蓝光成像。 | 富士内镜增强成像技术，用于强化黏膜和血管纹理。 |
| LCI | Linked Color Imaging | 联动成像。 | 富士内镜色彩增强技术，有助于病变识别。 |
| RDI | Red Dichromatic Imaging | 红色双光成像，Olympus 技术。 | 增强深部血管和出血点显示，但本身不是 AI 预警。 |
| ACI | Amber-red Color Imaging | 富士 ELUXEO 8000 系列相关增强成像模式。 | 增强出血点和黏膜下血管显示。 |
| HDMI / SDI | Video Interface | 常见视频信号接口。 | 用于将内镜主机图像输入 AI 处理模块或外接盒。 |

---

## 2. 内镜手术术语

| 术语 | 英文/全称 | 简要解释 | 在本项目中的意义 |
|---|---|---|---|
| ESD | Endoscopic Submucosal Dissection | 内镜黏膜下剥离术。 | 第一阶段最适合切入的食管手术场景。 |
| EMR | Endoscopic Mucosal Resection | 内镜黏膜切除术。 | 通常适用于较小或较浅表病变。 |
| POEM | Peroral Endoscopic Myotomy | 经口内镜下肌切开术。 | 可作为第二阶段扩展场景，主要用于贲门失弛缓症等食管动力障碍。 |
| Third-space Endoscopy | 第三空间内镜 | 在黏膜下层或类似潜在间隙中进行内镜治疗。 | 包括 ESD、POEM 等，主要风险是出血和穿孔。 |
| Mucosa | 黏膜层 | 食管最内层。 | 多数早期病变起源于此层。 |
| Submucosal layer | 黏膜下层 | 黏膜与肌层之间的层次。 | ESD 剥离的主要安全层。 |
| Muscle layer / Muscularis propria | 肌层 / 固有肌层 | 食管壁较深的肌肉层。 | 切割过深可能导致穿孔。 |
| Submucosal vessel | 黏膜下血管 | 黏膜下层内的血管。 | ESD 术中出血的重要来源。 |
| Bleeding point | 出血点 | 正在出血的位置。 | AI 可用于定位、提示和术后复盘。 |
| Perforation | 穿孔 | 食管壁被切穿。 | 食管穿孔可能进入纵隔，风险较高。 |
| Coagulation | 凝血 / 电凝 | 使用止血器械封闭血管。 | 系统可提示可疑血管是否需要预凝或确认。 |
| PEC | Post-ESD Coagulation | ESD 后预防性凝血。 | 可用于降低延迟出血风险。 |
| Dissection plane | 剥离层面 | 医生在 ESD 中切开的组织层次。 | AI 需要判断是否仍处于相对安全的黏膜下层。 |
| Knife tip | 刀尖 | 内镜刀最前端。 | 风险评分需要计算刀尖与血管/肌层的距离。 |
| En bloc resection | 整块切除 | 将病灶完整切除。 | ESD 的关键临床优势之一。 |
| Achalasia | 贲门失弛缓症 | 食管下端括约肌不能正常松弛。 | POEM 的主要适应症。 |
| Barrett’s esophagus | Barrett 食管 | 食管下段黏膜发生肠化生。 | 可伴随异型增生或早癌风险。 |

---

## 3. 食管解剖与风险结构

| 术语 | 中文 | 简要解释 | 为什么重要 |
|---|---|---|---|
| Esophagus | 食管 | 连接咽喉和胃的管状器官。 | 本项目的核心器官。 |
| GEJ | 胃食管结合部 | 食管和胃的交界区域。 | POEM、远端食管 ESD 和贲门附近操作的重要定位点。 |
| Aorta | 主动脉 | 人体最大动脉。 | 食管旁最重要的高风险血管之一。 |
| Aortic arch | 主动脉弓 | 主动脉上段弯曲部分。 | 上/中胸段食管邻近的重要结构。 |
| Trachea | 气管 | 呼吸道主干。 | 位于食管前方，穿孔或误伤风险需考虑。 |
| Left main bronchus | 左主支气管 | 通向左肺的主支气管。 | 中胸段食管邻近结构。 |
| Left atrium | 左心房 | 心脏结构之一。 | 中下段食管后方邻近结构。 |
| Pleura | 胸膜 | 包裹肺的膜。 | 食管穿孔可能进入胸腔。 |
| Mediastinum | 纵隔 | 两肺之间的区域，包含心脏、大血管、气管、食管等。 | 食管穿孔后的严重并发症区域。 |
| Azygos vein | 奇静脉 | 胸腔重要静脉。 | 食管周围静脉风险参考。 |
| Hemiazygos vein | 半奇静脉 | 胸腔静脉系统组成部分。 | 食管周围静脉风险参考。 |
| Left gastric artery | 左胃动脉 | 供应胃小弯和远端食管的动脉。 | 远端食管和贲门附近重要血管。 |
| Inferior thyroid artery | 甲状腺下动脉 | 供应颈段食管部分血流。 | 颈段食管手术风险参考。 |
| Esophageal branches of aorta | 主动脉食管支 | 供应胸段食管的小动脉。 | 胸段食管黏膜下血管风险来源之一。 |

---

## 4. AI 与图像处理术语

| 术语 | 英文 | 简要解释 | 在本项目中的作用 |
|---|---|---|---|
| AI | Artificial Intelligence | 人工智能。 | 用于识别血管、肌层、器械和高风险区域。 |
| Deep Learning | 深度学习 | 用神经网络从数据中学习特征。 | 医学图像识别的主要技术路线。 |
| CNN | Convolutional Neural Network | 卷积神经网络。 | 传统医学图像识别基础模型。 |
| Transformer | Transformer | 擅长全局信息建模的网络结构。 | 可用于复杂内镜场景分割。 |
| U-Net | U-Net | 医学图像分割经典网络。 | 可用于分割黏膜下层、血管和肌层。 |
| DeepLabv3+ | DeepLabv3+ | 语义分割模型。 | 可用于组织结构分割。 |
| SegFormer | Segmentation Transformer | 基于 Transformer 的分割模型。 | 可用于实时结构分割。 |
| YOLO | You Only Look Once | 实时目标检测模型。 | 可检测器械、刀尖、出血点。 |
| RT-DETR | Real-Time Detection Transformer | 实时目标检测 Transformer。 | 可用于器械和高风险区域检测。 |
| Semantic Segmentation | 语义分割 | 对每个像素进行分类。 | 标出血管、肌层、黏膜下层。 |
| Instance Segmentation | 实例分割 | 区分同类中的不同目标个体。 | 可区分不同血管或不同器械区域。 |
| Object Detection | 目标检测 | 用检测框定位目标。 | 适合检测器械、刀尖、出血点等。 |
| Keypoint Detection | 关键点检测 | 检测特定点位。 | 可用于定位刀尖。 |
| Optical Flow | 光流 | 估计相邻视频帧之间的像素运动。 | 提高视频连续帧中的标注稳定性。 |
| Video Tracking | 视频跟踪 | 持续跟踪目标。 | 用于血管、刀尖、出血点的时序稳定。 |
| Dice Score | Dice 系数 | 医学图像分割常用评价指标。 | 衡量 AI 分割结果和专家标注的一致性。 |
| mIoU | mean Intersection over Union | 平均交并比。 | 评价分割模型整体性能。 |
| Sensitivity | 敏感性 | 真有风险时能否检出。 | 关注漏报风险。 |
| Specificity | 特异性 | 没有风险时能否不报警。 | 关注误报风险。 |
| False Positive | 假阳性 | 没风险却报警。 | 过多会造成医生报警疲劳。 |
| False Negative | 假阴性 | 有风险却没报警。 | 在医疗场景中风险较高。 |
| Latency | 延迟 | 输入画面到输出结果的时间差。 | 术中系统需要低延迟。 |
| FPS | Frames Per Second | 每秒处理帧数。 | 通常 25–30 fps 更接近实时显示。 |
| Confidence Score | 置信度 | AI 对判断结果的把握程度。 | 低置信度时应提示医生谨慎。 |
| Risk Score | 风险评分 | 综合结构识别、器械距离、画面质量等得到的风险值。 | 用于低/中/高分级预警。 |
| Quality Assessment | 画面质量评估 | 判断是否存在模糊、反光、烟雾、出血遮挡等。 | 防止 AI 在低质量画面中误报。 |

---

## 5. 多模态融合与导航术语

| 术语 | 英文 | 简要解释 | 在本项目中的意义 |
|---|---|---|---|
| Multimodal Fusion | 多模态融合 | 将多种数据源合并分析。 | 内镜视频 + EUS + Doppler + CT/CTA。 |
| Registration | 配准 | 将不同影像对齐到同一坐标系。 | CT、EUS 和内镜视野需要建立空间对应关系。 |
| Co-registration | 共配准 | 多种影像同步对齐。 | CT-EUS 融合导航常用概念。 |
| Rigid Registration | 刚性配准 | 只允许平移和旋转。 | 适合形变小的结构。 |
| Deformable Registration | 形变配准 | 允许组织形变。 | 胃肠道形变较大时更接近真实情况。 |
| Electromagnetic Tracking | 电磁追踪 | 用电磁传感器定位内镜或探头位置。 | 可用于 CT-EUS-内镜融合导航。 |
| Centerline | 中心线 | 管腔的中轴线。 | 食管可基于中心线建立坐标。 |
| Clock-face Orientation | 钟点方位 | 用 12 点、3 点、6 点等描述方向。 | 内镜医生常用方位表达。 |
| Distance from incisors | 距门齿距离 | 内镜插入深度。 | 食管定位常用表达方式。 |
| Risk Map | 风险地图 | 显示某区域周围的危险结构。 | CT/CTA 可生成术前风险地图。 |
| Heatmap | 热力图 | 用颜色表示风险高低。 | 可显示血管、肌层或壁外结构风险。 |
| AR Overlay | 增强现实叠加 | 将提示信息叠加到真实画面上。 | 产品最终显示方式之一。 |
| Pixel-level Overlay | 像素级叠加 | 将风险信息精确叠加到图像像素位置。 | 理想目标，但技术难度较高。 |
| Region-level Warning | 区域级预警 | 提示某个区域存在风险。 | 第一版产品更现实可行。 |
| Workflow Integration | 工作流集成 | 将系统嵌入医生现有手术流程。 | 决定产品能否真正被医生使用。 |

---

## 6. 产品与注册术语

| 术语 | 英文 | 简要解释 | 在本项目中的意义 |
|---|---|---|---|
| SaMD | Software as a Medical Device | 医疗器械软件。 | AI 风险预警软件可能属于此类。 |
| AI-assisted Detection | AI 辅助检测 | AI 帮助医生发现目标。 | 第一版适合定位为辅助检测/辅助提示。 |
| AI-assisted Diagnosis | AI 辅助诊断 | AI 帮助医生判断疾病性质。 | 监管风险高于辅助检测。 |
| AI-assisted Decision Support | AI 辅助决策 | AI 给出治疗建议。 | 早期不宜作为主要注册定位。 |
| FDA 510(k) | 510(k) 上市路径 | 美国常见医疗器械上市路径。 | 可参考已上市内镜 AI 产品。 |
| De Novo | FDA De Novo Pathway | 无同类产品时可能使用的新型器械路径。 | 若无可比产品，可能需要考虑。 |
| NMPA | 国家药品监督管理局 | 中国医疗器械监管机构。 | 国内注册需要考虑。 |
| CE MDR | EU Medical Device Regulation | 欧盟医疗器械法规。 | 欧洲市场准入需要考虑。 |
| Clinical Validation | 临床验证 | 证明系统在真实临床中有效和安全。 | 产品注册和医生认可的关键。 |
| Retrospective Study | 回顾性研究 | 使用历史病例数据验证。 | 第一阶段常用验证方式。 |
| Prospective Study | 前瞻性研究 | 预先设计方案并实时收集病例。 | 证明临床价值更强。 |
| Human Factors / Usability | 人因工程 / 可用性 | 评价医生是否能安全、有效地使用系统。 | 医疗 AI 产品必须考虑。 |
| Alarm Fatigue | 报警疲劳 | 报警过多导致医生忽视提示。 | 手术预警系统必须重点避免。 |
| Audit Trail | 审计追踪 | 记录系统提示、操作和日志。 | 医疗软件合规和复盘需要。 |
| Postoperative Review | 术后复盘 | 术后回看风险点、截图和日志。 | 产品的重要附加价值。 |

---

## 7. 重点掌握的 15 个核心词

1. **ESD**：内镜黏膜下剥离术  
2. **POEM**：经口内镜下肌切开术  
3. **EUS**：超声内镜  
4. **Doppler**：多普勒血流检测  
5. **CTA**：CT 血管成像  
6. **Submucosal layer**：黏膜下层  
7. **Muscle layer**：肌层  
8. **Submucosal vessel**：黏膜下血管  
9. **Perforation**：穿孔  
10. **Registration**：配准  
11. **Multimodal Fusion**：多模态融合  
12. **Risk Map**：风险地图  
13. **Semantic Segmentation**：语义分割  
14. **Dice Score / mIoU**：分割准确率指标  
15. **SaMD**：医疗器械软件  

---

## 8. 项目逻辑一句话

**CT/CTA 提供术前大血管和邻近脏器地图；EUS 观察食管壁层次和壁外结构；Doppler 确认血流；内镜视频 AI 实时识别当前画面中的血管、肌层、器械和风险区域；多模态配准将这些信息关联到同一个手术坐标中，最终形成术中风险预警和术后复盘报告。**

---

## 9. 参考文献与延伸阅读

1. **Feasibility of real-time artificial intelligence-assisted anatomical structure recognition during endoscopic submucosal dissection**. *Endoscopy International Open*, 2025.  
   https://pmc.ncbi.nlm.nih.gov/articles/PMC12223949/

2. **Vessel and tissue recognition during third-space endoscopy using a deep learning algorithm**. *Gut*, 2022.  
   https://pmc.ncbi.nlm.nih.gov/articles/PMC9664130/

3. **A novel fusion imaging system for endoscopic ultrasound**. *Endoscopy International Open*, 2016.  
   https://pmc.ncbi.nlm.nih.gov/articles/PMC4770620/

4. **Doppler Endoscopic Probe Monitoring of Blood Flow Improves Risk Stratification and Outcomes of Patients With Severe Nonvariceal Upper Gastrointestinal Hemorrhage**. *Gastroenterology*, 2017.  
   https://www.sciencedirect.com/science/article/abs/pii/S0016508517301312

5. **Augmented reality navigation systems in endoscopy**. *Frontiers in Gastroenterology*, 2024.  
   https://www.frontiersin.org/journals/gastroenterology/articles/10.3389/fgstr.2024.1345466/full
