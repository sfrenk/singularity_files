BootStrap: docker
From:rocker/ropensci

%labels
    MAINTAINER Stephen Frenk <stephen.frenk@gmail.com>
    DESCRIPTION Container image containing all requirements for variant calling pipeline
    VERSION 1.0

%files
    environment.yaml /

%post
	wget https://repo.anaconda.com/archive/Anaconda3-5.2.0-Linux-x86_64.sh
	bash Anaconda3-5.2.0-Linux-x86_64.sh -b -p /opt/anaconda3
	echo "PATH=/opt/anaconda3/bin:\$PATH" >> $HOME/.bashrc
	echo "export PATH" >> $HOME/.bashrc
	rm Anaconda3-5.2.0-Linux-x86_64.sh
	. $HOME/.bashrc

	/opt/anaconda3/bin/conda install -c r r-essentials

    /opt/conda/bin/conda env create -f /environment.yaml
    /opt/conda/bin/conda clean -a
