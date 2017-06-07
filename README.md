# Grinn examples

This repository contains various examples for [Buildroot][Buildroot] and [liteSOM][liteSOM]
device produced by [Grinn sp. z o.o.][Grinn]

## How to setup project with Grinn examples?

### Download and extract Buildroot release, for example

    wget https://buildroot.org/downloads/buildroot-2017.02.tar.gz
    tar xf buildroot-2017.02.tar.gz

### Clone this repository

    git clone https://github.com/grinn-pub/examples.git

### Configure buildroot to use customizations from this repository

    cd buildroot-2017.02
    make BR2_EXTERNAL=/tmp/examples list-defconfigs

where `/tmp/examples` should point to the repository cloned in the 2nd step.

Target `list-defconfigs` shows list of available _defconfigs_. After _built-in configs_ you 
should see configs provided by the external customizations (like [Grinn examples][Grinn examples]).


    make BR2_EXTERNAL=/tmp/examples list-defconfigs
    Built-in configs:
      acmesystems_aria_g25_128mb_defconfig - Build for acmesystems_aria_g25_128mb
      acmesystems_aria_g25_256mb_defconfig - Build for acmesystems_aria_g25_256mb
      [...]
      
    External configs in "Grinn examples":
      grinn_liteboard_can_defconfig       - Build for grinn_liteboard_can
      grinn_liteboard_lcd_res_defconfig   - Build for grinn_liteboard_lcd_res
      grinn_liteboard_spi_defconfig       - Build for grinn_liteboard_spi
      grinn_liteboard_telit_defconfig     - Build for grinn_liteboard_telit


### Configure build configuration, for example

    make grinn_liteboard_lcd_res_defconfig
    
### Build software

    make all

After successful build in `output/build/images` you will find generated by the [Buildroot][Buildroot] and customized by [Grinn examples][Grinn examples] firmware for your board.

## External links

* Grinn home page: http://grinn-global.com
* Grinn wiki: https://wiki.grinn-global.com
* chiliSOM platform: http://chilisom.com
* liteSOM platform: http://litesom.com

[Grinn examples]: https://github.com/grinn-pub/examples.git
[liteSOM]: http://litesom.com/
[Buildroot]: https://buildroot.org/
[Grinn]: http://grinn-global.com/
