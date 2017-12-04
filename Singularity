Bootstrap: docker
From: continuumio/miniconda3
##From: continuumio/anaconda:latest

##From: centos:7.3.1611


%help
Orange is a data mining tool from biolab.si
It is a both a GUI program and python modules for advance use.
[unofficial singularity container]

%runscript
	orange-canvas

%post
	/opt/conda/bin/conda config --add channels conda-forge
	/opt/conda/bin/conda install orange3
	/opt/conda/bin/conda install -c defaults pyqt=5 qt
	apt-get -y install libgl1-mesa-dev
	#pip install --upgrade pip
	#pip install setuptools
	#pip install orange3
	echo singularity container build ends.


%labels
MAINTAINER  Tin Ho tin(at)lbl.gov

# template https://singularity-hub.org/containers/567
 

