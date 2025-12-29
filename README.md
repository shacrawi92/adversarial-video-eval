# Adversarial Evaluation of Generative Video Models (Google Veo 3)

### **Project Overview**
This repository documents black-box adversarial testing and prompt engineering strategies for **Google Veo 3**. The research focuses on evaluating the model's robustness, identifying "hallucination" patterns in high-fidelity generation, and optimizing cost-efficiency for independent researchers in resource-constrained environments.

**Researcher:** Abdishakur Mahdi Abdirahman
**Location:** Jijiga, Ethiopia

---

## 📊 Key Findings

### 1. Hallucination Rates in "Studio" Contexts
* **Observation:** Targeted prompts requesting specific studio lighting setups (e.g., "cinematic rim lighting," "softbox key light") resulted in an ~80% failure rate.
* **Failure Mode:** The model frequently hallucinates artifacts or fails to render correct lighting textures when complex lighting descriptors are stacked.
* **Impact:** Validated the limitations of Veo 3 in handling highly specific technical cinematography commands compared to general descriptive prompts.

### 2. Preventative Prompting Framework
I developed a structured prompting methodology to reduce credit waste during experimentation.
* **Result:** Reduced unusable video generations by approximately **30–40%**.
* **Method:** By utilizing specific negative constraints and optimizing token ordering, the framework forces the model to prioritize geometry over stylistic texture in the initial render pass.

---

## 🛠️ Technical Methodology

### Adversarial Testing Protocol
1.  **Baseline Generation:** Establish a control video using standard prompts.
2.  **Stress Testing:** Introduce contradictory variables (e.g., "fast motion" + "low shutter speed" + "high detail") to force model collapse.
3.  **Documentation:** Log failure timestamps and artifact types (blurring, warping, temporal flicker).

### Tools Used
* **Model:** Google Veo 3
* **Environment:** Cloud Inference (Google Labs)
* **Analysis:** Manual frame-by-frame texture consistency analysis.

---

## 🚀 Roadmap
- [ ] **Automated Eval Script:** Building a Python script to automatically detect frame-drops and consistency errors in generated video output.
- [ ] **Texture Consistency Score:** Developing a metric to quantify how well textures hold up during rapid camera movements.
- [ ] **Cross-Model Comparison:** Future benchmarks will compare Veo 3 performance against other SOTA video generation models.

---

## 📬 Contact
**Abdishakur Mahdi Abdirahman**
*Systems Engineer & Independent AI Researcher*
