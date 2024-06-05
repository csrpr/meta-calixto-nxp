CALIXTO SYSTEMS PVT LTD Yocto Project BSP <version> Release 
====================================================================
		https://calixtosystems.com/
--------------------------------------------------------------------
Note this is release is not a production release.
Please see the release notes for the quality statement for each baord.


   
Quick Start Guide
-----------------
The following boards were tested in this release.

   * Calixto IMX6ULL-VERSA256 EVB 
   * Calixto IMX6ULL-VERSA512 EVB 
   * Calixto IMX6ULL-VERSA1024 EVB 
   
Quick Start Guide
-----------------
See the Calixto Yocto Project User's Guide for instructions on installing repo.

First install the Calixto Linux BSP repo
Syntax:
$: repo init -u git://github.com/<nxp-imx>/<imx-manifest.git> -b <imx-linux-kirkstone> -m <imx-5.15.71-2.2.0.xml>

Example:
$: repo init -u https://github.com/csrpr/demo_calixto_menifest.git -b main -m calixto-yocto-v0.1.xml


Download the Yocto Project Layers:
$: repo sync

If errors on repo init, remove the .repo directory and try repo init again.

Run Calixto Linux Yocto Project Setup:
Syntax:
$: DISTRO=<distro name> MACHINE=<machine name> source calixto-setup-release.sh -b <build_dir>

where

 <machine> defaults to imx6ull-versa256
 <build folder> specifies the build folder name
 
Example:
$: DISTRO=poky MACHINE=imx6ull-versa256 source calixto-setup-release.sh -b build_cs

After this your system will be configured to start a Yocto Project build.


Contributing
------------

To contribute to the development of this BSP and/or submit patches for
new boards please send the patches against the respective project as
informated bellow:

The following layers are included on this release:

 * poky: base build system and metadata
   Path: sources/poky
   GIT: git://git.yoctoproject.org/poky
   Mailing list: https://lists.yoctoproject.org/listinfo/yocto

 * meta-openembedded: extra packages and features
   Path: sources/meta-openembedded
   GIT: git://git.openembedded.org/meta-openembedded
   Mailing list: http://lists.linuxtogo.org/cgi-bin/mailman/listinfo/openembedded-devel
   Note: Use [meta-oe] in subject to easy the processing

 * meta-freescale: support for Freescale's processors and board
   Path: sources/meta-freescale
   Project: https://github.com/Freescale/meta-freescale
   GIT: git://github.com/Freescale/meta-freescale.git
   Mailing list: https://lists.yoctoproject.org/listinfo/meta-freescale

 * meta-freescale-3rdparty: support for boards using Freescale's processors
   Path: sources/meta-freescale-3rdparty
   Project: https://github.com/Freescale/meta-freescale-3rdparty
   GIT: git://github.com/Freescale/meta-freescale-3rdparty.git
   Mailing list: https://lists.yoctoproject.org/listinfo/meta-freescale
   Note: Use [3rdparty] in subject to easy the processing

 * meta-freescale-distro: distribution images and recipes
   Path: sources/meta-freescale-distro
   Project: https://github.com/Freescale/meta-freescale-distro
   GIT: git://github.com/Freescale/meta-freescale-distro.git
   Mailing list: https://lists.yoctoproject.org/listinfo/meta-freescale
   Note: Use [distro] in subject to easy the processing
   

- tree of meta-calixto-nxp layer :

meta-calixto-nxp
|
├── conf
│   ├── layer.conf
│   └── machine
│       ├── imx6ull-versa1024.conf
│       ├── imx6ull-versa256.conf
│       ├── imx6ull-versa512.conf
│       └── include
│           ├── calixto-imx-base.inc
│           ├── e500mc.inc
│           ├── e500v2.inc
│           ├── e5500-64b.inc
│           ├── e5500.inc
│           ├── e6500-64b.inc
│           ├── e6500.inc
│           ├── fsl-default-settings.inc
│           ├── fsl-default-versions.inc
│           ├── imx8dxl-evk.inc
│           ├── imx8mm-evk.inc
│           ├── imx8mn-evk.inc
│           ├── imx8mp-evk.inc
│           ├── imx8x-mek.inc
│           ├── imx-base.inc
│           ├── qoriq-arm64.inc
│           ├── qoriq-arm.inc
│           ├── qoriq-base.inc
│           ├── qoriq-ppc.inc
│           └── utilities.inc
├── README-CALIXTO-BSP.md
├── recipes-bsp
│   ├── files
│   └── u-boot
│       └── u-boot-calixto-nxp_2022.04.bb 
├── recipes-calixto
│   └── images
│       ├── calixto-image-minimal.bb -[tested]
│       └── calixto-image-multimedia.bb -[progressing]
├── recipes-kernel
│   ├── files
│   │   └── deconfig - [need to be add the latest deconfig file]
│   └── linux
│       └── linux-calixto-nxp_6.1.1.bb 
└── tools
    ├── calixto-setup-release.sh
    ├── install_prerequisites.sh
    └── setup-environment

-> 12 directories, 33 files
