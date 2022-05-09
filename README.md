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

???
 
## Steps

0. Go to a folder with molecules, e.g. `cd ~/boss/molecules/small`
1. Choose a molecule, e.g. nitrobenzene. Find its abbreviation, e.g. `nitrob`.
2. `cp nitrob.z dihzmat`
3. Open the file `dihzmat`
4. Identify the atom associated with the dihedral angle you care about. Call this atom index `d` e.g. `0015`
5. Remove `d` from the range under `Variable Dihedrals follow`, and add it under `Additional Dihedrals follow` above `AUTO`
6. Add to `d` the rest of the atoms that make up the dihedral, and then append `  -1  -1` to it, e.g. `0015009004003  -1  -1`
7. Save and close the file. 
8. Open the file `dih.bat` or `dih.cmd`
9. Change the line `set ATOM=00015` with the correct atom number `d` from above.
10. Change the line `set LAMBDA= 10.000...` with your desired angle increment
11. Save and close the file
12. Run the command `dih`
13. Open `dih.csv` to view the energies
