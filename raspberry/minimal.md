# Raspberry Pi minimal image

## In order to implement, it is required that you possess:
* computer with 8Gb RAM and 90 Gb free disk space
* Ubuntu OS or another Supported Linux Distributions

## Download software dependencies
We are going to use [Poky] and the layers [ meta-openembedded] and [meta-raspberrypi].
* First we will use Git to clone Poky repro $ git clone -b sumo `git://git.yoctoproject.org/poky.git`
* Enter into the Poky folder `cd poky`
* Use Git to clone the meta-rasperrypi layer repo using the apropriate version branch. `$ git clone -b sumo git://git.yoctoproject.org/meta-raspberrypi`
* Use Git to clone the meta-openembedded layer repo using the apropriate version branch. `$ git clone -b sumo git://git.openembedded.org/meta-openembedded`

