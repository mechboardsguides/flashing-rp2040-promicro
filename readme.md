# How to flash an rp2040 pro micro

We strongly recommend flashing these before soldering.

You will need to have a QMK command line environment installed- see here: https://docs.qmk.fm/newbs_getting_started

You **do not** need QMK toolbox to flash RP2040 controllers.

Compile your firmware, using the converter feature:

```qmk compile -kb crkbd -km via -e CONVERT_TO=rp2040_ce```

```qmk compile -kb lily58 -km via -e CONVERT_TO=rp2040_ce```

Find the `uf2` file that produced in your `/qmk_firmware` folder on your computer.

Plug in the controller holding the `BOOT` button. A folder called `RPI-RP2` should pop up. Some linux distros may need to manually mount the drive.

Drag and drop the `uf2` file onto this `RPI-RP2` folder. It should automatically disconnect, then connect as a keyboard.

![B043C5C6-089F-4AC5-B128-9258FA37E373_1_105_c](https://github.com/mechboardsguides/flashing-rp2040-promicro/assets/19674258/367d8305-6a93-4c2d-9ae4-c1cbea88c07f)


If you have forgotten to flash the controller for the first time before soldering, you can enter bootloader by connecting the `BOOT` hole on the back to `GROUND` as indicated here:

![8209F136-FC1D-4159-931C-556819390EB9_1_105_c](https://github.com/mechboardsguides/flashing-rp2040-promicro/assets/19674258/c912c9e6-eb5f-41c8-9971-c1cdc03a8c84)

After flashing for the first time with QMK you can then enter bootloader with the usual QMK methods (reset switch, bootmagic, QK_BOOT keycode).
