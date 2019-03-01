---
layout: tutorial_hands_on

title: Running Molecular Dynamics simulations using GROMACS
zenodo_link: ''
questions:
- How do I use the GROMACS engine to run molecular dynamics simulations?
- Which bioinformatics techniques are important to know for this type of data?
objectives:
- Learn about the GROMACS engine provided via Galaxy
time_estimation: 3H
contributors:
- simonbray

---


# Introduction
{:.no_toc}


> ### Agenda
>
> In this tutorial, we will cover:
>
> 1. TOC
> {:toc}
>
{: .agenda}



# Simulation with GROMACS

This process can be accomplished by selected each tools from the tools menu or by importing the workflow. The workflow method is most efficient and the individual tools used in the workflow are discussed below. 

> ### {% icon details %} NVT, NPT and statistical mechanics theory
>
> [See Statistical Mechanics, McQuarrie for more in depth theory ISBN:9781891389153](https://books.google.co.za/books/about/Statistical_Mechanics.html?id=itcpPnDnJM0C&redir_esc=y)
>
{: .details}

## Individual steps

### **preliminaries**
Download a PDB structure file from the Protein Data Bank and make some modifications. We will follow Justin Lemkul's tutorial (HERE) and use lysozyme (1AKI).


> ### {% icon hands_on %} Hands-on:
>
> 1. Go the the PDB website (LINK) and search for the code 1AKI. Download the structure:
> 2. Modify ...
>
{: .hands_on}

### **setup**
{: #setup}

Prepare a topology for a protein structure. 
This tool will:
- convert a PDB protein structure into a GRO file
- create a 'topology' file which ...

> ### {% icon hands_on %} Hands-on:
>
> 1. **setup** {% icon tool %} with the following parameters:
>
>
{: .hands_on}

### **solvate**

Create a 'box' containing the structure and fills it with solvent molecules

> ### {% icon hands_on %} Hands-on:
>
> 1. **solvate** {% icon tool %} with the following parameters:
>
>
{: .hands_on}

### **minimizer**

Reduces the energy of the system by running a minimisation algorithm. 
This tools will:
- Minimise energy using steepest descent
- generate Particle Mesh Ewald (PME)

> ### {% icon hands_on %} Hands-on: 
>
> 1. **minimizer** {% icon tool %} with the following parameters:
>
>
{: .hands_on}

### **nvt**
{: #nvt}
Equilibration using classical NVT dynamics.

> ### {% icon hands_on %} Hands-on: NVT dynamics
>
> 1. **nvt** {% icon tool %} with the following parameters:
>
> This tool runs classical molecular dynamics simulations in GROMACS using an NVT ensemble. The user can run the simulation in small time intervals. The coordinates, velocities and the extended system files can be used to restart the simulations.
> {: .hands_on}

### **npt**
{: #npt}
Equilibration useing classical NPT dynamics.

> ### {% icon hands_on %} Hands-on: NPT dynamics
>
> 1. **npt** {% icon tool %} with the following parameters:
>
> This tool runs classical molecular dynamics simulations in GROMACS using an NPT ensemble. The user can run the simulation in small time intervals. The coordinates, velocities and the extended system files can be used to restart the simulations. 
> {: .hands_on}

### **mdrun**
{: #npt}
'Production' simulation on minimized, equilibrated system.
> ### {% icon hands_on %} Hands-on: Production simulation
>
> 1. **mdrun** {% icon tool %} with the following parameters:
>
> This tool runs classical molecular dynamics simulations in GROMACS. The user can run the simulation in small time intervals. The coordinates, velocities and the extended system files can be used to restart the simulations. 
> {: .hands_on}


## GROMACS MD workflow
{: #namd_md}

This workflow uses GROMACS as a molecular dynamics engine. Preparation, energy minimization and NVT + NPT equilibration are followed by a production simulation.

> ### {% icon hands_on %} Hands-on: Access the workflow
> Access the published workflows
> ![List of published workflows](images/published_workflows_update.png "Published workflows")
> Choose to import the NAMD MD workflow from published workflows
> ![Import workflow](images/import_workflow.png "Import workflow")
> Choose to run a workflow from your available workflows
> ![Your workflows](images/workflows_yours.png "Your workflows")
{: .hands_on}


# Conclusion
{:.no_toc}

