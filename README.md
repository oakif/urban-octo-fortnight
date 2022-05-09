* optimize, dihdrive, consearch, MCgas, MCGBSA, and linres.

### General commands

1. Find molecule: `grep nitrobenzene INDEX.txt`

### Conformational Search (consearch)

Find conformations of a molecule

1. Choose a molecule such as `pentan`
2. Type in `xCS100 pentan`
3. Open the CSV file called `pentan.cs.CSV` to view all conformations
4. To calculate relative energies, subtract all conformational energies by the lowest energy conformer

### Dihedral Drive (dihdrive)

Find energy differences with changes in the dihedral angle in a molecule. 

* `d1` = main atom associated with dihedral

1. `cd ~/boss/molecules/small` (or any other folder containing your molecule)
2. `cp nitrob.z dihzmat`
3. `open dihzmat`
4. Determine `d2`, `d3`, `d4` as the atoms on the same line as `d1`
5. Remove `d1` from range under `Variable Dihedrals follow`
6. Make new line under `Additional Dihedrals follow`
7. Insert <pre>`d1d2d3d4  -1  -1`</pre> e.g. line should read <pre>`0015009004003  -1  -1`</pre> Take note of the double spaces.
8. Save and close
9. `open dih.bat` or `open dihcmd`
10. Change `set ATOM=00015` to atom `d` from above
11. Change `set LAMBDA= 10.000...` with desired angle increment
12. Save and close
13. `dih`
14. `open dih.csv`
