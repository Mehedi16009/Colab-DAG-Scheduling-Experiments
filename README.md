# Colab-DAG-Scheduling-Experiments
DAG scheduling experiments in Google Colab using forms for parameterized inputs.



# Gang-Task Scheduling and Response-Time Analysis (Colab Experiment)

This project is a Colab-based research demo inspired by Prof. Shareef Ahmed’s recent RTAS’25 paper “Scheduling Processing Graphs of Gang Tasks on Heterogeneous Platforms.”
The notebook implements a mini experimental framework to simulate and analyze gang-task scheduling on heterogeneous CPU–GPU systems.

## 🔑 Key Features

--Synthetic DAG Generation: Randomly generates gang-task DAGs with CPU/GPU execution demands.

--Scheduling Simulation: Implements both Work-Conserving (WC) and Semi-Work-Conserving (SWC) schedulers.

--Response-Time Analysis (RTA): Computes theoretical completion bounds for task graphs.

--Case Study Setup (ResNet18): Prepares for CNN workloads by treating model layers as gang tasks, measured on CPU/GPU in PyTorch.

--Visualization: Histograms comparing WC vs SWC schedulers, utilization curves, and execution timelines.

----
📊 Example Results

->WC scheduler consistently yields lower makespan compared to SWC across random DAG workloads.

->For small DAGs (10–20 nodes), the framework completes in milliseconds, allowing rapid experimentation.

->Supports scalability tests (100+ DAGs) for utilization vs schedulability analysis.
#Note on Case Study (ResNet18):
This notebook currently focuses on synthetic DAG experiments for clarity and runtime efficiency. A CNN-based case study (e.g., ResNet18) was considered, where each layer would be treated as a gang-task node with measured CPU/GPU execution times. However, this adds significant runtime overhead in Colab. The current framework is fully extensible to this case study: one can simply replace the synthetic DAG generator with a ResNet-derived DAG, assign per-layer timings, and run the same RTA + scheduling experiments.

## Files
- `dag_experiments.ipynb` → Main Google Colab Notebook
- `docs/` → PDF references and documentation
- `results/` → Example experiment outputs

---

## 📊 Figurative Results:

Here are five key results generated from the notebook:

### 1. Custom Sweep (High Resolution)
<img width="702" height="410" alt="custom_sweep_high_res" src="https://github.com/user-attachments/assets/33894f0a-0b94-4305-8a21-0d746d2f6d4a" />

### 2. One-Shot Gantt Chart
<img width="702" height="410" alt="one_shot_gantt_high_res" src="https://github.com/user-attachments/assets/f3bd2174-fc13-43a1-9b09-72ad2a3d288a" />


### 3. Random DAG Example
<img width="702" height="410" alt="random_dag_high_res" src="https://github.com/user-attachments/assets/2dcb8078-53f3-4561-add1-f7d034c71042" />


### 4. Schedulability Sweep
<img width="702" height="410" alt="schedulability_sweep_high_res" src="https://github.com/user-attachments/assets/fd0126b0-ff64-4059-a28a-3e008c56da76" />


### 5. Work-Conserving Gantt Chart
<img width="702" height="410" alt="work_conserving_gantt_high_res" src="https://github.com/user-attachments/assets/40f45f5c-0734-408b-9928-c2c9668c3862" />


---
##🎯 Motivation

This project demonstrates a practical entry point into real-time systems research by bridging:

Theory → Response-Time Analysis of gang-task DAGs.

Practice → Lightweight CNN case study (ResNet18 layer-wise DAG).

Experimentation → Simulation framework to explore heterogeneous scheduling policies.
---

##📌 Next Steps

Extend case study with ResNet18 layer timings on CPU vs GPU in Colab.

Compare RTA-derived bounds with measured CNN execution traces.

Explore federated scheduling extensions for multiple DAGs.
---
##📑 Citation

Ahmed, Shareef. “Scheduling Processing Graphs of Gang Tasks on Heterogeneous Platforms.” RTAS 2025.
