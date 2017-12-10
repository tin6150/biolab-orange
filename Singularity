Bootstrap: docker
From: ubuntu:16.04
## docker container for anaconda somehow produced windows without text. missing fonts lib?
##From: continuumio/anaconda3:latest
##From: continuumio/miniconda3

##From: centos:7.3.1611


%help
Orange is a data mining tool from biolab.si
It is a both a GUI program and python modules for advance use.
[unofficial singularity container]

%runscript
	/opt/anaconda3/pkgs/orange3-3.8.0-py36_0/bin/orange-canvas "$@"
	#orange-canvas

%post
	echo singularity container build starts
	touch /THIS_IS_INSIDE_SINGULARITY
	apt-key update
	apt-get update
	apt-get -y --force-yes install vim ncurses-term gedit less wget git tar bzip2 coreutils firefox
	# browser is optional, used for displaying help, tutorial

	# install anaconda3 (python3)
	Anaconda3Ver=5.0.1
	cd /opt
	#test -f Anaconda3-${Anaconda3Ver}-Linux-x86_64.sh || wget https://repo.continuum.io/archive/Anaconda3-${Anaconda3Ver}-Linux-x86_64.sh
	#test -d /opt/anaconda3 || bash Anaconda3-${Anaconda3Ver}-Linux-x86_64.sh -p /opt/anaconda3 -b     # batch mode, accept license w/o user input
	if [ ! -d /opt/anaconda3 ]; then
		wget https://repo.continuum.io/archive/Anaconda3-${Anaconda3Ver}-Linux-x86_64.sh 
		bash Anaconda3-${Anaconda3Ver}-Linux-x86_64.sh -p /opt/anaconda3 -b     # -b = batch mode, accept license w/o user input
	fi


	/opt/anaconda3/bin/conda config --add channels conda-forge
	/opt/anaconda3/bin/conda install orange3
	/opt/anaconda3/bin/conda install -c defaults pyqt=5 qt
	#/opt/conda/bin/conda config --add channels conda-forge
	#pip install --upgrade pip
	#pip install setuptools
	#pip install orange3
	# not sure why the orange-canvas script misdetected python to be in /opt/anaconda1anaconda2anaconda3 .  tmp fix till find root cause.
	ln -s anaconda3 anaconda1anaconda2anaconda3
	# clean up
	rm Anaconda3-${Anaconda3Ver}-Linux-x86_64.sh 
	echo singularity container build ends.


%labels
MAINTAINER  Tin Ho tin(at)lbl.gov

 
# ref https://www.singularity-hub.org/collections/323

