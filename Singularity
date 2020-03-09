Bootstrap: docker

From: continuumio/miniconda3

%files
    environment.yml

%environment
    PATH=/opt/conda/envs/$(head -1 environment.yml | cut -d' ' -f2)/bin:$PATH

%post
    echo ". /opt/conda/etc/profile.d/conda.sh" >> ~/.bashrc
    echo "source activate $(head -1 environment.yml | cut -d' ' -f2)" > ~/.bashrc
    /opt/conda/bin/conda env create -f environment.yml

%runscript
    exec "$@"
