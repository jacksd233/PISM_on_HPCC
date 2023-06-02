# Build PISM on HPCC server (undergoing)
``` Edited by jacksd 2023.6.2 ```

## ==================== Load and Install Prerequisities  ====================

### Load Compilers

Use intel compiler in .bashrc:
  
    export PATH="/global/apps/intel/2020u1/bin:$PATH"
    export PATH="/global/apps/intel/2020u1/compilers_and_libraries_2020.1.217/linux/bin:$PATH"
    export LD_LIBRARY_PATH="/global/apps/intel/2020u1/compilers_and_libraries_2020.1.217/linux/compiler/lib/intel64:$LD_LIBRARY_PATH"
    export PATH="/global/apps/intel/2020u1/compilers_and_libraries_2020.1.217/linux/bin/intel64:$PATH"
    
Use mpich in .bashrc:
(mpi in `"/global/apps/intel/2020u1/compilers_and_libraries_2020.1.217/linux/mpi` doesn't work)
    
    # mpich
    export PATH="/global/apps/mpich/bin:$PATH"
    export LD_LIBRARY_PATH="/global/apps/mpich/lib:$LD_LIBRARY_PATH"
