GROMACS 2024.2 MARTINI 3 Alchembed (lambda scaling) reproducer

The problem appears to the forcefield for the MARTINI 3 lipid POPI. Steps,
using GROMACS 2024.2 with this repo:

- `gmx grompp -f alchembed-cg.mdp -c system.gro -p topology.top -o alchembed.tpr -maxwarn 20`
- `gmx mdrun -v -s alchembed.tpr -deffnm alchembed_1x_lipids -nt 1 -ntmpi 1`

which should crash/reproduce:

```
Program:     gmx mdrun, version 2024.2
Source file: src/gromacs/topology/topsort.cpp (line 142)

Fatal error:
Function type Restr. Angles does not currently support being perturbed in free
energy calculations
```
