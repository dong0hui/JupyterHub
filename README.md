# JupyterHub
Installation of Jupyterhub on Ubuntu

# Enable port
On Azure Portal Enable port 8000

# Install Anaconda Python
cd /tmp
curl -O https://repo.anaconda.com/archive/Anaconda3-2019.07-Linux-x86_64.sh
sh256sum Anaconda3-2019.07-Linux-x86_64.sh
bash Anaconda3-2019.07-Linux-x86_64.sh

The following steps are typed based on Guidance provided by Anaconda
Change installation path to /anaconda3
ctrl+D
ssh

# Install JupyterHub
sudo apt-get install npm
sudo apt-get install nodejs

sudo -s
conda install notebook
conda install -c conda-forge jupyterhub

/anaconda3/bin/jupyterhub
/etc/jupyterhub/jupyterhub_config.py

# Run JupyterHub
sudo /home/anaconda3/bin/jupyterhub --config=/etc/jupyterhub/jupyterhub_config.py
pgrep jupyterhub

sudo vim /lib/systemd/system/jupyterhub.service
sudo systemctl daemon-reload
sudo systemctl start jupyterhub

## jupyterhub script can be found online
add /anaconda3 to PATH in /etc/init.d/jupyterhub
sudo service jupyterhub start

cd /var/log/jupyterhub

# Install k3d
sudo -s
conda install -c conda-forge k3d
jupyter labextension install k3d

# Install ipywidgets
conda install -c conda-forge ipywidgets
conda install -c conda-forge nodejs
jupyter labextension install @jupyter-widgets/jupyterlab-manager

# Install matplotlib for jupyterlab
conda install -c conda-forge ipympl

# Install plotly
Note: plotly comes with Anaconda, we just need to install JupyterLab extension
jupyter labextension install @jupyterlab/plotly-extension

# Install Dash
pip install "jupyterlab>=1.0" jupyterlab-dash==0.1.0a3
jupyter labextension install jupyterlab-dash@0.1.0-alpha.3
jupyter lab build



