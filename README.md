# Instances-SCFLPS

This repository contains the instances used in the article:

**José Emmanuel Gómez-Rocha, Eva Selene Hernández-Gress, José-Fernando Camacho-Vallejo, and Cipriano Santos**  
*An enhanced Benders decomposition method and a matheuristic algorithm for solving the stochastic capacitated facility location problem with shortages*  
**Expert Systems with Applications**, Volume 255, Part D, 2024, 124802  
ISSN: 0957-4174  
DOI: [10.1016/j.eswa.2024.124802](https://doi.org/10.1016/j.eswa.2024.124802)  
Available at: [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0957417424016695)

## Abstract

The Capacitated Facility Location Problem (CFLP) is a well-known combinatorial optimization problem that has been widely studied in location science due to its relevance in industrial engineering, humanitarian logistics, telecommunications, and other application domains. When customer demand is uncertain, stochastic programming provides a suitable framework for addressing this problem. Under such uncertainty, however, not all customer demand can necessarily be satisfied.

To capture this feature, this work incorporates shortages into the CFLP and proposes a stochastic capacitated facility location problem with shortages under normally distributed demands, where customer loss is penalized in the objective function. To solve the problem, three exact methods and one matheuristic algorithm are proposed. The exact methods are based on Benders decomposition and include: (i) a basic implementation, (ii) a strengthened version with valid inequalities, and (iii) an enhanced Branch-and-Cut approach. The matheuristic follows a Fix-and-Relax style strategy based on pricing ideas, allowing high-quality solutions to be obtained within reasonable computational times.

The proposed methods are evaluated against the deterministic equivalent formulation solved with Gurobi through extensive computational experiments on challenging instances under a sample average approximation framework. In addition, the practical relevance of the model is illustrated through a real case study involving Mobile Health Clinics (MHCs) in Mexico. The results provide useful managerial insights, including the finding that at least 271 MHCs would be required to meet the government’s healthcare coverage goals for acute respiratory infections among socially vulnerable populations.

## Keywords

Facility location; Stochastic programming; Shortages; Benders decomposition; Matheuristics; Mobile health clinics


SCFLPS instance formats
Structure
```text
scflps\_instances\_clean/
  schema.json
  instances/
    100-200-a/
      metadata.json
      demand.csv
      capacity.csv
      fixed\_cost.csv
      transport\_cost\_matrix.csv
      transport\_cost\_long.csv
      instance.json
    ...
  auxiliary/
    candidatos/
      candidatos.csv
      candidatos.json
    clientes/
      clientes.csv
      clientes.json
```
Main instance files
`demand.csv`: demand distribution parameters by market or customer.
`capacity.csv`: plant capacity values.
`fixed\_cost.csv`: fixed opening cost by plant. The `auxiliary\_flag` column preserves an extra 0/1 value present in several original workbooks without imposing an interpretation.
`transport\_cost\_matrix.csv`: plant-by-market cost matrix, convenient for inspection.
`transport\_cost\_long.csv`: long-form cost table with `(plant, market, cost)`, convenient for Python, Gurobi, Pyomo, Julia/JuMP, and database loading.
`instance.json`: complete instance in a nested JSON structure.
`metadata.json`: source file, detected sheets, set sizes, scalar parameters, and validation flags.


