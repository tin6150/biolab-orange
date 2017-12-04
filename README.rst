# biolab-orange
singularity container for the orange data mining tool from https://orange.biolab.si
unofficial

Utilizes miniconda.  But Orange3 install likely install numpy, scipy, etc.
Need libGL.so, trying to use libgl1-mesa-dev.  Native nvidia package may provide better performance.

Result Singularity image is about 3.6 GB.


Ref: 

- https://www.singularity-hub.org/collections/323
- https://github.com/tin6150/biolab-orange


~~~~


VER=2.4.1
module load container/singularity/${VER}
Singularity=$( which singularity )
sudo    $Singularity build -w ./biolab-orange.img ./Singularity


