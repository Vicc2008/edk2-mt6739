# EDK2 UEFI Firmware For Xiaomi MI 8 (Dipper)
Attempt to create a normal EDK2 for Xiaomi MI8 - dipper.

Based on zhuowei's port for [Pixel3XL](https://github.com/Pixel3Dev/edk2-pixel3/).

## The Most Important
DO NOT FLASH THIS UEFI FIRMWARE IN YOUR MAIN PHONE !!!

It's very unstable and you may lost your data.

## Status 
 UFS WORK！

 Can boot Linux Arm

 Clock WORK!

 Test ACPI etc. tables removeed.

 And can load Windows PE.

## Dev Logs
2020.1.6 Fix 5 compiler error.

2020.1.7 Start work and successfully run on my phone.

2020.1.8 Fix Display.

2020.4.17 Fix UFS drive and Fix MemoryMap（Thanks [Lemon1Ice](https://github.com/Lemon1Ice)）.

2020.4.19 Add ACPI etc. Tables and Fix DSDT 24 Errors. （PS.The ACPI and SSDT etc. Tables Provided by [Lemon1Ice](https://github.com/Lemon1Ice)）

2020.4.24 Fix Clock and The Clock is work well && Add SmemDxe SPI SPMI HWIODxeDriver PmicDxe ButtonsDxe ChipInfoDxe to Binary && Add USB driver

2020.4.30 Re added MemoryMap and can boot Windows to BlueScreen（Stop Code：Memory Managent） and （Stop Code：IRQL NOT LESS OR EQUAL）

2020.5.6 Fix A Lot but Nothing.

2020.5.8 Fix A Lot but Nothing.

2020.5.10 Can boot WindowsPE . Thank for [Lemon1Ice](https://github.com/Lemon1Ice) patience and great help！

## To-Do
1.Fix fts touchscreen

## Dependencies

Ubuntu 18.04:

```
sudo apt update
sudo apt install build-essential uuid-dev iasl git nasm python3-distutils gcc-aarch64-linux-gnu
```
Or
```
sudo apt update
sudo apt install build-essential
sudo apt install uuid-dev
sudo apt install iasl
sudo apt install git
sudo apt install nasm
sudo apt install python3-distutils
sudo apt install gcc-aarch64-linux-gnu
```


## Building
1.Clone edk2 and edk2-platforms (Place three directories side by side.)
```
mkdir workspace
cd workspace
git clone https://github.com/tianocore/edk2.git --recursive
git clone https://github.com/tianocore/edk2-platforms.git
```

2.Clone this project
```
git clone https://github.com/NekokeCore/edk2_dipper_SDM845_Xiaomi_mi_8.git
```

3.Build eenvironment
```
bash firstrun.sh
```

4.Build this project
```
bash build.sh
```
5.Debug and use
```
fastboot boot uefi.img
```

## Credits
MemoryMap and ACPI etc. tables thanks [Lemon1Ice](https://github.com/Lemon1Ice).

Orther edk2 project [EngLearnsh](https://github.com/EngLearnsh/edk2-dipper).

SimpleFbDxe screen driver is from imbushuo's [Lumia950XLPkg](https://github.com/WOA-Project/Lumia950XLPkg).

Also thanks [edk2 website](https://github.com/tianocore/tianocore.github.io/wiki/Using-EDK-II-with-Native-GCC#Install_required_software_from_apt).
