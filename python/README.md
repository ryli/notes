### virtualenv
``` shell
pip install --upgrade virtualenv


virtualenv --python python3 env


env/bin/pip install -r requirements.txt -i http://pypi.**.com/simple --trusted-host pypi.**.com

```


### python3
```
pip install virtualenvwrapper
vim ~/.zshrc

  export WORKON_HOME=$HOME/.virtualenvs
  source /usr/local/bin/virtualenvwrapper.sh

source ~/.zshrc
unset PYTHONPATH
mkvirtualenv env --python=python3 # workon env
pip install ipython
ipython
```
