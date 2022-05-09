* optimize, dihdrive, consearch, MCgas, MCGBSA, and linres.

# Conformational Search (consearch)

## Goal

Find conformations of a molecule

## Steps

1. Choose a molecule such as `pentan`
2. Type in `xCS100 pentan`
3. Open the CSV file called `pentan.cs.CSV` to view all conformations
4. To calculate relative energies, subtract all conformational energies by the lowest energy conformer

# Dihedral Drive (dihdrive)

## Goal 

Find energy differences with changes in the dihedral angle in a molecule. 
 
## Steps

1. `cd ~/boss/molecules/small`
2. `cp nitrob.z dihzmat`
3. `open dihzmat`
4. Identify the atom associated with the dihedral angle you care about. Call this atom index `d` e.g. `0015`
5. Remove `d` from the range under `Variable Dihedrals follow`, and add it under `Additional Dihedrals follow` above `AUTO`
6. Add to `d` the rest of the atoms that make up the dihedral, and then append `  -1  -1` to it, e.g. `0015009004003  -1  -1`
7. Save and close
8. `open dih.bat` or `open dih.cmd`
9. Change `set ATOM=00015` to atom `d` from above
10. Change `set LAMBDA= 10.000...` with desired angle increment
11. Save and close
12. `dih`
13. `open dih.csv`
