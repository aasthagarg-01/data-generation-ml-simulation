# Data Generation using Modelling and Simulation for Machine Learning

## Overview
This project demonstrates the use of modelling and simulation to generate synthetic data for machine learning applications. A CPU task scheduling system is simulated using a discrete-event simulation approach. The generated data is then used to train and evaluate multiple machine learning models to predict average task waiting time.

The objective of the project is to:
- Generate data using simulation
- Train multiple ML models on the generated data
- Compare model performance using evaluation metrics
- Identify the best-performing model

---

## Simulation Tool Used
- **SimPy**: A Python-based discrete-event simulation framework used to model CPU task scheduling.

---

## Simulation Description
The simulation models a CPU system where tasks arrive randomly and are processed by a limited number of CPU cores. Each task experiences a waiting time depending on system load and resource availability.

### Simulation Parameters and Ranges

| Parameter | Description | Range |
|---------|------------|-------|
| Task Arrival Rate | Rate at which tasks arrive | 1 to 15 |
| Task Execution Time | Time required to execute a task | 0.5 to 3 |
| Number of CPU Cores | Available CPU cores | 1 to 8 |
| Simulation Time | Total simulation duration | 10 units |

---

## Data Generation
- A total of **1000 simulations** were performed.
- For each simulation, parameters were randomly sampled within their defined bounds.
- The output variable recorded was **Average Task Waiting Time**.

### Generated Dataset
The dataset contains the following columns:
- `task_arrival_rate`
- `task_execution_time`
- `number_of_cpu_cores`
- `average_waiting_time`

The dataset is saved as:
- `simulation_dataset.xlsx`

---

## Machine Learning Models Used
The following machine learning regression models were trained and evaluated:

1. Linear Regression  
2. Ridge Regression  
3. Lasso Regression  
4. Decision Tree Regressor  
5. Random Forest Regressor  
6. Support Vector Regression  

---

## Model Evaluation Metrics
Models were evaluated using:
- **Mean Squared Error (MSE)**  
- **R² Score**

Lower MSE and higher R² indicate better model performance.

---

## Model Comparison Results

| Model Name | Mean Squared Error | R² Score |
|----------|------------------|----------|
| Random Forest | 0.154721 | 0.913816 |
| Support Vector Regression | 0.197646 | 0.889905 |
| Decision Tree | 0.230689 | 0.871499 |
| Ridge Regression | 0.340961 | 0.810073 |
| Linear Regression | 0.340996 | 0.810054 |
| Lasso Regression | 0.762951 | 0.575011 |

The comparison results are saved as:
- `model_comparison_results.xlsx`

---

## Graphical Analysis

### Model Comparison Based on Mean Squared Error
This bar graph compares all models using Mean Squared Error.  
Lower values indicate better predictive performance.

<img width="989" height="489" alt="image" src="https://github.com/user-attachments/assets/efcb0953-c810-465d-98ed-8b8fff0ca5c1" />


---

### Model Comparison Based on R² Score
This bar graph compares models using R² score.  
Higher values indicate better explanation of variance in the data.

<img width="989" height="489" alt="image" src="https://github.com/user-attachments/assets/b74a223a-1f24-448e-b4a5-8d3871016f4e" />


---

### Best Model: Random Forest
The Random Forest Regressor achieved:
- **Lowest Mean Squared Error**
- **Highest R² Score**

This indicates that Random Forest is the most suitable model for predicting average task waiting time for the simulated CPU scheduling system.

---

## Files in the Repository
- `Data_generation.ipynb` – Complete simulation and machine learning implementation
- `simulation_dataset.xlsx` – Generated dataset from simulations
- `model_comparison_results.xlsx` – ML model evaluation results
- `README.md` – Project documentation

---

## Conclusion
This project demonstrates that simulation-based data generation can effectively support machine learning model development. Among the evaluated models, Random Forest performed the best due to its ability to capture non-linear relationships and interactions between system parameters. The approach is useful in scenarios where real-world data is limited or expensive to obtain.
