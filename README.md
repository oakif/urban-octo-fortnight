* optimize, dihdrive, consearch, MCgas, MCGBSA, and linres.

### General commands

1. Find molecule: `grep nitrobenzene INDEX.txt`

### Optimizze

1. `cd ~/boss/testjobs/optimize`
2. `grep nitrobenzene ~/boss/molecules/small/INDEX.txt`
3. `cp ~/boss/molecules/small/nitrob.z .`
4. `./xOPT nitrob`

* `open out` to view results
* `grep out "Optimized energy"`

### Conformational Search (consearch)

Output conformations of a molecule

1. `cd ~/boss/testjobs/consearch`
2. `grep ethanediol ~/boss/molecules/small/INDEX.txt`
3. `cp ~/boss/molecules/small/etdiol.z .`
4. `./xCS100F etdiol`

* `open etdiol.cs.sum` to view summary
* `open pentan.cs.CSV` to view conformation energies. To calculate relative energies, subtract lowest energy conformer from each energy

### Dihedral Drive (dihdrive)

Find energy differences with changes in the dihedral angle in a molecule. 

* `d1` = main atom associated with dihedral

1. `cd ~/boss/testjobs/dihdrive`
2. `grep nitrobenzene ~/boss/molecules/small/INDEX.txt`
5. `cp ~/boss/molecules/small/nitrob.z dihzmat`
6. `open dihzmat`
    1. Determine `d2`, `d3`, `d4` as the atoms on the same line as `d1`
    2. Remove `d1` from range under `Variable Dihedrals follow`
    3. Make new line under `Additional Dihedrals follow`
    4. Insert <pre>`d1d2d3d4  -1  -1`</pre> e.g. line should read <pre>`0015009004003  -1  -1`</pre> Take note of the double spaces.
    5. Save and close
7. `open dih.bat` or `open dihcmd`
    1. Change `set ATOM=00015` to atom `d` from above
    2. Change `set LAMBDA= 10.000...` with desired angle increment
    3. Save and close
8. `dih` or `csh dihcmd`

* `open dih.csv` summary of dihedrals and energies

### General Linear Response (linres)

1. `cd ~/boss/testjobs/linres`
2. `grep "ethyl methyl ether" ~/boss/molecules/small/INDEX.txt`
3. `cp ~/boss/molecules/small/emether.z .`
4. `./xLRCMPhere emether`
5. `cd emether`

* `x lrplte25` display simulation box
* `open lrote25` see energies, %GTG
* `open propout` properties including log P which is the partition of drugs in water vs cell membrane
