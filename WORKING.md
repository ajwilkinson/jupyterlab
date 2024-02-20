* New venv created in .\venv
* Configuration file is the one in XXX
Then:
'''
pip install -e ".[dev,test]"

which fails.

yarn

succeeded

It uses pyproject.toml which is the "new style" requirements.txt

There must be something in the dev/test config, as 

pip install .

Succeeds.

At this point we need to build jupyterlab. First of all, check in the venv to
make sure that we don't have another version of jupyterlab in there - if so delete
to make sure we use our source one.

python -m jupyterlab build

Remember to do the above whenever adding an extension

We're not using dev-mode as we're not trying to develop an extension (as that is all about
how the generated html etc. is managed on disk)

Can now verify that jupyterlab will start with

python -m jupyterlab


That should work. Now we install a bunch of extensions to make sure that
they are included:

