Optimal Power Flow (OPF) Using Pyomo and Gurobi

Overview




<img width="289" alt="image" src="https://github.com/user-attachments/assets/4b0882d4-c632-4e16-81a7-bfeed65ea93b" />



This project solves an Optimal Power Flow (OPF) problem to determine the most cost-effective way to generate and distribute electricity in a power system while maintaining network balance and adhering to operational constraints. The model minimizes generation costs while ensuring that power generation meets demand and that voltage angles and power flow limits are respected.

Key Features

Formulates the OPF problem as a mathematical optimization model

Optimizes generator outputs, power flow, and voltage angles

Ensures power balance at each node

Implements generator and transmission limits

Uses Gurobi for high-performance optimization

Installation

1. Install Required Packages

Ensure you have the following dependencies installed:

pip install pyomo pandas numpy openpyxl

2. Install Gurobi Solver

Since the project uses Gurobi, you must have it installed and licensed.

Check if Gurobi is installed:

gurobi_cl --version

If not installed, download it from: Gurobi Official Website

Alternatively, you can use CBC (open-source solver) by replacing:

opt = SolverFactory('gurobi')

with:

opt = SolverFactory('cbc')

How to Run the Project

Ensure your Excel input file (powerSystem.xlsx) is correctly formatted:

bus sheet: bus_id

generation sheet: bus, cost, pgmax, pgmin

load sheet: bus, load

line sheet: from_bus, to_bus, Bl, plmax

Run the Python script:

python opf_model.py

View the results, which include:

Optimal generator outputs

Power flow across transmission lines

Voltage angles at each bus


License

This project is licensed under the MIT License.

