labelme: Image Annotation Tool with Python
==========================================

[![Build Status](https://travis-ci.org/wkentaro/labelme.svg?branch=master)](https://travis-ci.org/wkentaro/labelme)


Labelme is a graphical image annotation tool inspired by <http://labelme.csail.mit.edu>.

It is written in Python and uses Qt for its graphical interface.


Dependencies
------------

- [PyQt4](http://www.riverbankcomputing.co.uk/software/pyqt/intro)


Installation
------------

**Docker**

You need install [docker](https://www.docker.com), then just run below:

```bash
wget https://raw.githubusercontent.com/wkentaro/labelme/master/scripts/labelme_on_docker
chmod u+x labelme_on_docker

# Maybe you need http://sourabhbajaj.com/blog/2017/02/07/gui-applications-docker-mac/ on macOS
./labelme_on_docker _static/apc2016_obj3.jpg -O _static/apc2016_obj3.json
```

**Ubuntu**

```bash
sudo apt-get install python-qt4 pyqt4-dev-tools
sudo pip install labelme
```

**OS X**

```bash
brew install qt qt4
pip install labelme
```

**macOS Sierra**

```bash
# on python2
brew install pyqt5 --with-python
pip install git+https://github.com/wkentaro/labelme.git@pyqt5

# on python3
brew install pyqt5
pip3 install git+https://github.com/wkentaro/labelme.git@pyqt5
```


Usage
-----

**Annotation**

Run `labelme --help` for detail.

```bash
labelme  # Open GUI
labelme _static/apc2016_obj3.jpg  # Specify file
labelme _static/apc2016_obj3.jpg -O _static/apc2016_obj3.json  # Close window after the save
```

The annotations are saved as a [JSON](http://www.json.org/) file. The
file includes the image itself.

**Visualization**

To view the json file quickly, you can use utility script:

```bash
labelme_draw_json _static/apc2016_obj3.json
```

**Convert to Dataset**

To convert the json to set of image and label, you can run following:


```bash
labelme_json_to_dataset _static/apc2016_obj3.json
```


Sample
------

- [Original Image](https://github.com/wkentaro/labelme/blob/master/_static/apc2016_obj3.jpg)
- [Screenshot](https://github.com/wkentaro/labelme/blob/master/_static/apc2016_obj3_screenshot.jpg)
- [Generated Json File](https://github.com/wkentaro/labelme/blob/master/_static/apc2016_obj3.json)
- [Visualized Json File](https://github.com/wkentaro/labelme/blob/master/_static/apc2016_obj3_draw_json.jpg)


Screencast
----------

<img src="https://github.com/wkentaro/labelme/raw/master/_static/screencast.gif" width="70%"/>
