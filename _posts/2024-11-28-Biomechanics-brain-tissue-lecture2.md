---
title: "Modeling and stimulation of brain tissues"
date: 2024-11-28
categories: [Study]
tags: [Biomechanics],[Brain tissue]
---



### literatures
1. [Fifty shades of Brain: A review on the mechanical testing and modeling of brain tissue](https://link.springer.com/article/10.1007/s11831-019-09352-w)

2. [Tissue-Scale Biomechanical Testing of Brain Tissue for the Calibration of Nonlinear Material Models](https://currentprotocols.onlinelibrary.wiley.com/doi/full/10.1002/cpz1.381)
3. [Insight into the microstructural origin of brain viscoelasticity](https://link.springer.com/content/pdf/10.1007/s10659-021-09814-y.pdf)
4. [Neocortical development and epilepsy: insights from focal cortical dysplasia and brain tumours](https://www.sciencedirect.com/science/article/pii/S1474442221002659?via%3Dihub)
5. [A two-field computational model couples cellular brain development with cortical folding](https://www.sciencedirect.com/science/article/pii/S2666522021000058)
6. [Size and curvature regulate pattern selection in the mammalian brain](https://www.sciencedirect.com/science/article/pii/S2352431615000863)
7. [Bulging brains](https://pmc.ncbi.nlm.nih.gov/articles/PMC5687257/)
8. [A comparison of brain retration mechanisms using finite element analysis and the effects of regionally heterogeneous material properties](https://link.springer.com/article/10.1007/s10237-023-01806-2)



## Ultrasoft materials
1. stiffness of different tissues
   - brain tissue
   - adipose tissue 脂肪组织
   - lung tissue
   - skeletal muscle tissue
   - liver tissue
   - myocardium
   - breast tissue
   - atery
   - smooth muscle tissue
   - skin
   - cartilage
   - bone
2. hydrogels 水凝胶
   - biphasic materials comprising a porous, permeable solid and at least 10% of interstitial fluid 间质液
     - solid: water insoluble 不溶于水的 3d netweork of natural or synthetic polymers
     - fluid: mainly water
   - alginate-based hydrogels 海藻酸盐基水凝胶
     - alginate：typically extracted from the cell walls of brown algae褐藻细胞壁
     - great potential to form stable hydrogels with modulated 调节的 mechanical properties


![水凝胶](https://cdn.jsdelivr.net/gh/idadayi/Blogimage@main/Markdown20241204145341.png)

## Modeling time-independent properties
1. Time-indepedent effects
   - nonlinearity
   - compression-tension asymmertry
   - C-cortex
   - CR-corona radiata 放射冠（sample during the experiment）
   - no anisotropy?
   - region-dependency
     - CC - corpus callosum
     - BG - basal ganglia
     - C- cortex
     - CR - corona radiata

   - cortex
   - thalamus
   - basal ganglia基底神经节
   - amygdala 杏仁核
   - corona radiata 放射冠
   - corpus callosum 胼胝体
   - brain stem
   - cerebellar white matter 小脑白质
   - deep cerebellar nuclei 小脑深核

2. Deformation and stress
   - deformation gradient
     - two point tensor
     - one leg in material/reference configuration, one leg in deformed spatial configuration
   - piola stress
     - nominal stress 
     - with respect to the original undeformed coress-section area
   - cauchy stree
     - true stress
     - with respect to the actual deformed cross-section area
   - material model: equation that relates the stress with the deformation (strech or strain)
   - different loading modes
     - Ogden
       - modified one-term Ogden
       - shear modulus
       - nonlinearity parameter
     - neo-Hooke
     - Mooney-Revlin
     - Demiray
     - Gent


3. finite hyperelasticity
   - material respense independent of load history - loading and unloading follow the same path
   - rheological model 流变模型: spring
   - strain energy density
     - as free energy
     - energy stored elastically within a unit volume of the body
     - strain energy only depends on elastic deformation
   - stress follows as derivative with respect to the deformation gradient. (stress is the derivative of strain energy or free energy with respect to the deformation gradient.)


4. multiple loading modes 
   - important to consider multiple loading modes simultaneously 同时
   - parameter identification 参数辨识
5. Deformation and stress for uniaxial compression/tension
   - assumptions:
     - incompressible material
     - homogeneous deformation
   - stretch: 
     - >1-no deformation
     - ><1 - compression
     - >1 - tension
   - deformation gradient with eigenvalues
   - piola stress

6. Modeling region-dependent properties
   - option 1: region-dependent model parameters
     - different regions with different parameters (e.g. shear modulus or nonlinearity parameters in modified one-term Ogden)
   - option 2: include microstructural information

  - modeling regional hyperelastic properties
  - introduce material parameters (shear modulus or nonlinearity parameters in Ogden) as a function of the cell density c
  - a single set of parameters valid for all brain regions


## Modeling time-dependent properties

1. Time-dependent effects
   - hysteresis 滞后
   - recoverable conditioning 
     - viscoelastic effect and no damage

   - stress relaxation
2. Viscoelasticity
   - Material response depends on loading rate and loading history
     - loading $\neq$ loading
     - energy dissipation
   - rheological model: combination of springs and dampers
   - in the linear elastic limit
     - Hooke's Spring (with Young's Modulus)
     - Newton's damper

3. finite viscoelasticity
   - multiplicative split of deformation gradient (F的乘法分割)
   - additive split of strain energy function (应变能的加法分割)
   - eq: cell-density-dependent strain energy
   - microstructure-informed viscosity or relaxation time
   - neq: hyperelastic strain energy

   - during stress relaxation, cells keep moving in the same direction as during loading
   - cell displacement curves: during stress relaxation experiments to determine one of the relaxation time constants
   - time constant: corresponding time constant represents the viscoelasticity of the network of cells and extracellular matrix
   - free model parameter identification through least square optimization
     - microstructural parameter (cell density)
     - predict changes in the macroscopic mechanical response based on microstructural parameters
     - mechanical biomarker for diseases
4. finite poro-viscoelasticity
   - brain tissue = solid component + fluid component = biphasic approximation
   - poroelasticity alone is not sufficient to capture the response of brain tissue and hydrogels
     - poro-viscoelasticity
     - viscoelastic solid component
     - darcy-like law to describe constitutive behavior of the fluid component 达西定律描述流体的本构行为
     - choose the material model depending on the application of interest and the corresponding relevant loading condition

## Finite element simulations
1. inverse parameter identification
   - material response
     - compression
     - tension
     - torsional shear

2. applications: brain development
   - link cellular processes 连接细胞过程 during brain development with cortical folding
   - hypothesis: mechanical instabilities induced by a difference in growth and stiffness between cortex and inner zones (subcortex) drive cortical folding
   - numerical prediction of the link between cellular brain development and cortical folding - cell density
   - model validation: comparison with histologically 组织学 stained 染色的 human fetal brain sections
   - gestational week 孕周
   - final goal: assist diagnosis and treatment of epilepsy 癫痫 through inverse engineering and computational disease modeling
   - How is cortical folding affected by brain size?
   - comparison of different mammalian brains: influence of brain volume

   - notes on material model choice
     - fluid has time to escape and does not contribute to tissue stiffness -> hyperelasticity, conditioned response (==what is the condioned response and unconditioned response?==)(loading=unloading)
     - extremely large deformations -> caution with material nonlinearity
3. applications: neurodegenrative diseases
   - computational model predicts spatio-temporal progression of toxic protein
   - structrucal remodeling at slow time scales -> finite hypereslasticity
4. applications: traumatic brain injury
   - computational models to estimate injury risk and advance injury prevention
   - predictions critically depend on the choice of constitutive model
   - notes on material model chice
     - computational Ogden hyperelastic model showed best agreement with experiments
     - extremly high strain rates
       - hyperelasticity, unconditioned response
       - viscoelastic effects?
5. applications: brain surgery
   - computational model predicts displacements and maximum principal strains during decompressive craniotomy 减压开颅手术
   - unilateral flap 单侧皮瓣 - literature 7
   - how do region-dependent properties affect simulations of brain surgery?
   - Regional properties need to be considered for in silico brain models.
     - homogeneous properties in same region
     - regional properties are different
     - considered brain regions

   - notes on material model choice
     - large deformations imposed on brain tissue at intermediate time scales
     - finite (poro-)viscoelasticity

## Conclusions
1. Computational models of the brain provide important insights into the underlying mechanisms of brain development, injury and disease
2. Challenges: brain tissue response is highly complex and region-dependent
3. Modeling approach and material parameters should be chosen according to the application (loading conditions and interest)
4. Carefully design experiments to appropriately calibrate models
   - inverse parameter identification
5. Microstructural-based models can capture material heterogeneities 材料的异质性