# Install and local playbook run

## Ensuring pip is available
To verify whether `pip` is already installed for your preferred Python:

```
$ python3 -m pip -V
```
If all is well, you should see something like the following:

```
$ python3 -m pip -V
pip 21.0.1 from /usr/lib/python3.9/site-packages/pip (python 3.9)
```
If so, pip is available, and you can move on to the next step.

If you see an error like `No module named pip`, you will need to install `pip` under your chosen Python interpreter before proceeding. This may mean installing an additional OS package (for example, `python3-pip`), or installing the latest `pip` directly from the Python Packaging Authority by running the following:
```
$ curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
$ python3 get-pip.py --user
```
You may need to perform some additional configuration before you are able to run Ansible. See the Python documentation on installing to the user site for more information.

## Installing Ansible
Use pip in your selected Python environment to install the full Ansible package for the current user:
```
$ python3 -m pip install --user ansible
```

## Confirming your installation
You can test that Ansible is installed correctly by checking the version:
```
$ ansible --version
```
The version displayed by this command is for the associated ansible-core package that has been installed.

## Run Ansible Playbook from URL

A combination of `curl` and `ansible-playbook` will do ya:
```
$ curl https://my.server.com/playbook.yml | ansible-playbook -i inventory/ /dev/stdin
```
