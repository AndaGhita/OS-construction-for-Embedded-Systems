# Raspberry Pi minimal image

## In order to implement, it is required that you possess:
* computer with 8Gb RAM and 90 Gb free disk space
* Ubuntu OS or another Supported Linux Distribution

## Download software dependencies
We are going to use [Poky] and the layers [ meta-openembedded] and [meta-raspberrypi].
* First we will use Git to clone Poky repro $ git clone -b sumo `git://git.yoctoproject.org/poky.git`
* Enter into the Poky folder `cd poky`
* Use Git to clone the meta-rasperrypi layer repo using the apropriate version branch. `$ git clone -b sumo git://git.yoctoproject.org/meta-raspberrypi`
* Use Git to clone the meta-openembedded layer repo using the apropriate version branch. `$ git clone -b sumo git://git.openembedded.org/meta-openembedded`

## Build the image
* Initialize the build env `$ source oe-init-build-en`
* Modify local.conf file
  - Need to set your machine to MACHINE = "raspberrypi" according to your [Raspberry Pi model].
  - Set the SSTate Mirrors to save time in the builds.
    `SSTATE_MIRRORS = "\
    file://.* http://sstate.yoctoproject.org/dev/PATH;downloadfilename=PATH \n \
    file://.* http://sstate.yoctoproject.org/2.4/PATH;downloadfilename=PATH \n \
    file://.* http://sstate.yoctoproject.org/2.5/PATH;downloadfilename=PATH \n \"`
  - Modify the bbplayers.conf file
    `BBLAYERS ?= " \
    /home/joao/yocto/poky/meta \
    /home/joao/yocto/poky/meta-poky \
    /home/joao/yocto/poky/meta-yocto-bsp \
    /home/joao/yocto/poky/meta-openembedded/meta-oe \
    /home/joao/yocto/poky/meta-openembedded/meta-multimedia \
    /home/joao/yocto/poky/meta-openembedded/meta-networking \
    /home/joao/yocto/poky/meta-openembedded/meta-python \  
    /home/joao/yocto/poky/meta-raspberrypi \
    "`
* Build the image minimal `$ bitbake -k core-image-minimal`


