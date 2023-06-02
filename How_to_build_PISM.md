# Build PISM on HPCC server (undergoing)
``` Edited by jacksd 2023.6.2 ```

## ==================== Load and Install Prerequisities  ====================

### [1] Load Compilers

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

### [2] Load and Install Tools and Libraries
Refer to PISM manual (http://www.pism.io/docs/installation/prerequisites.html)
    
    # cmake
      export PATH="/global/pub/cmake/bin:$PATH"
    
    # FFTW-mpi
      Download: http://www.fftw.org/download.html
    # Configure
      ./configure --prefix=~/apps/fftw-mpi --enable-shared --enable-static --enable-mpi 
      make -j 8
      make install
      make clean
     Add fftw-mpi to PATH and LD_LIBRARY_PATH to .bashrc
    
    # Install gsl-2.5
      Download: https://www.gnu.org/software/gsl/
    # Configure and build
      ./configure --prefix=~/apps/gsl
      make 
      make check 
      make install
      make clean
     Add gsl to PATH and LD_LIBRARY_PATH to .bashrc
     
    # netcdf and netcdf-mpi
      export PATH="/global/pub/netcdf/bin:$PATH"
      export LD_LIBRARY_PATH="/global/pub/netcdf/lib:$LD_LIBRARY_PATH"
      export PATH="/global/pub/netCDF-impi/bin:$PATH"
      export LD_LIBRARY_PATH="/global/pub/netCDF-impi/lib:$LD_LIBRARY_PATH"

