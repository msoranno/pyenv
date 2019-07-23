# Pyenv 

Para gestionar multiples versiones de python

## install

https://realpython.com/intro-to-pyenv/

```
sudo yum install zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl-devel xz xz-devel libffi-devel

curl https://pyenv.run | bash

# NOTA: la instalación se hizo correctamente  pero no podía instlar ninguna versión de python por error en el "openssl" . Al final he desinstalado  openssl-devel y todo ha ido 
# correctamente

```
- configure at startup

```
vi ~/.bashrc

export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

- list version availables for install

```
pyenv install --list | grep "3.7"
```
- list current version installed

```
pyenv versions
```

- install version 3.7.4

```
pyenv install 3.7.4
```

- installations location

```
ls ~/.pyenv/versions/
```

- remove version

```
rm -rf ~/.pyenv/versions/2.7.15

or

pyenv uninstall 2.7.15
``` 

- Change Python version

We can switch the python interpreter version we’re using in 2 ways, globally, or locally.

	- Global

		To change globally to 3.7.4 version

		```
		pyenv global 3.7.4 

		# to test if this version work propertly
		python -m test 

		# to go back
		pyenv global system
		```

	- locally

		```
		pyenv local 3.7.4

		# to go back

		pyenv local system 

		```
    - locally with virtualenv (best option)

    	```
    	# Creamos el entorno tst01 con la versión 3.7.4
    	pyenv virtualenv 3.7.4 tst01
    	
    	# Lo activamos (veremos el cambio en el prompt)
    	pyenv local tst01

    	# volvemos a la versión del sistema
    	pyenv local system

    	# delete virtualenv when no needed
    	pyenv virtualenv-delete tst01

    	```