# mta_python_juypter

Download the Python Libaries from Software Downloads Center.


```
https://launchpad.support.sap.com/#/softwarecenter/search/XS_PYTHON00_1
```

Copy the XS_PYTHON00_1-70003433.ZIP file to your Docker instance.

```
scp XS_PYTHON00_1-70003433.ZIP root@localhost:/tmp
```

Download the Python ML Libraries with the HXE Download Manager.

Expand the archive file clients_linux_x86_64.tgz

Copy the hana_ml-1.0.3.tar.gz file to your Docker instance.

```
scp hana_ml-1.0.3.tar.gz root@localhost:/tmp
```

```
wget -c -O mta.jar https://tools.hana.ondemand.com/additional/mta_archive_builder-1.1.7.jar
```

Since the HANA WebIDE doesn’t support python as a development language yet and we’ve also turned it off, it would be nice to have a way to play with the python machine learning api.  There is a python project called jupyter that provides this functionality.

pip install jupyter
Here are a few other python ml packages that you might like to explore(optionally).

pip install sklearn
pip install mxnet
pip install tensorflow
pip install python-mnist
Create a default jupyter configuration with this command.

jupyter notebook --generate-config
cp ~/../HDB90/hxe_python_ml/jupyter_config/jupyter_notebook_config.py ~/.jupyter/jupyter_notebook_config.py
cp ~/../HDB90/hxe_python_ml/jupyter_config/jupyter_notebook_config.json ~/.jupyter/jupyter_notebook_config.json
Run the jupyter notebook server.

jupyter notebook

cf push ateamjn -u none --no-start -p python -n a-team-jn -c "jupyter notebook --generate-config"

