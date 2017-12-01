Bootstrap: docker
From: continuumio/miniconda:latest
##From: continuumio:anaconda

##From: centos:7.3.1611


%help
Orange is a data mining tool from biolab.si
It is a both a GUI program and python modules for advance use.
[unofficial singularity container]

%post
	conda config --add channels conda-forge
	conda install orange3
	conda install -c defaults pyqt=5 qt
	#pip install --upgrade pip
	#pip install setuptools
	#pip install orange3


%labels
MAINTAINER  Tin Ho tin(at)lbl.gov

# template https://singularity-hub.org/containers/567
 

