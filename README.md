# keras-jupyter

* Source code - [Github][1]
* Author - Gavin Noronha - <gnoronha@hotmail.com>

[1]: https://github.com/gavinln/keras-jupyter.git

## About

This project provides a [Ubuntu (16.04)][10] [Vagrant][20] Virtual Machine (VM)
with the [Keras][30] and [TensorFlow][40] libraries and [Jupyter][50]
(formerly known as IPython) notebooks. Keras also works with [Theano][60].

[10]: http://releases.ubuntu.com/16.04/
[20]: http://www.vagrantup.com/
[30]: https://github.com/fchollet/keras
[40]: http://tensorflow.org/
[50]: http://jupyter.org/
[60]: http://deeplearning.net/software/theano/

Follow the **Requirements** section below for a one-time setup of Virtualbox,
Vagrant and Git before running the commands below. These instructions should
work on Windows, Mac and Linux operating systems.

## Running Keras

### 1. Start the VM

1. Change to the keras-jupyter root directory
```
cd keras-jupyter
```

2. Make sure you have the latest version of vagrant (1.9.1)
```
vagrant -v
```

3. Start the Virtual machine (VM)
```
vagrant up
```

4. Login to the VM
```
vagrant ssh
```

5. Install Jupyter notebook extensions
```
jupyter contrib nbextension install --user
```

6. Optional - Install vim extension
```
cd $(jupyter --data-dir)/nbextensions
git clone https://github.com/lambdalisue/jupyter-vim-binding vim_binding
```

7. Optional - To enable the Vim extension open your browser
to http://192.168.33.10:8888/tree#nbextensions_configurator after you
have started the Jupyter notebook as described below.

### 2. Run your first TensorFlow command line program

First run section 1.

1. Change to the python directory
```
cd /vagrant/python
```

2. Set environment variable to disable warnings
```
export TF_CPP_MIN_LOG_LEVEL=2
```

2. Run the first program
```
python3 first-tensorflow.py
```

3. Make sure the version printed on the first line of the output is the version you expect. The releases are documented on this [page][70]

[70]: https://github.com/tensorflow/tensorflow/releases

### 3. Start the Jupyter notebooks

First run section 1.

1. Change to the notebooks directory
```
cd /vagrant/scripts
```

2. Run the Jupyter notebook server
```
chmod +x jpy-notebook.sh
./jpy-notebook.sh
```

3. Open your browser to http://192.168.33.10:8888/ to view the notebooks

## Learning Keras

This [tutorial][80] by Valerio Maggio presented at [Euro Scipy 2016][90] is
a good introduction to deep learning using Keras.

[80]: https://github.com/leriomaggio/deep-learning-keras-tensorflow
[90]: https://www.euroscipy.org/2016/program/

### To install the tutorial

1. Change to the notebooks directory
```
cd /vagrant/scripts
```

2. Clone the repsitory
```
git clone https://github.com/leriomaggio/deep-learning-keras-tensorflow
```

3. Open your browser to http://192.168.33.10:8888/tree/deep-learning-keras-tensorflow

### Introduction to machine learning with Keras

The presentation by Michela Paganini is an excellent introduction to the topic.

* Introduction to Deep Learning with Keras, from CERN: [video][100], [slides][110]

[100]: http://cds.cern.ch/record/2157570?ln=en
[110]: https://indico.cern.ch/event/506145/contributions/2132944/attachments/1258124/1858154/NNinKeras_MPaganini.pdf


## Install bash_it  (optional)

1. To install bash_it for more features on the command prompt run

```
~/.bash_it/install.sh
```

2. Update ~/.bashrc file to modify the following line set the demula theme

```
export BASH_IT_THEME='demula'
```

3. Load the theme by typing `reload`

## Requirements

The following software is needed to get the software from github and run
Vagrant. The Git environment also provides an [SSH client][200] for Windows.

* [Oracle VM VirtualBox][210]
* [Vagrant][220] version 1.9.1 or higher
* [Git][230]

[200]: http://en.wikipedia.org/wiki/Secure_Shell
[210]: https://www.virtualbox.org/
[220]: http://vagrantup.com/
[230]: http://git-scm.com/
