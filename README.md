# FTDI-BridgeTek-SampleApp-for-CFAF800480E0-050SC-A1
This is the FTDI / Bridgetek PC SampleApp code, with the changes needed to support the Crystalfontz CFAF800480E0-050SC-A1 using the FTDI C232HM MPSSE USB to SPI cable.

The base FTDI / BridgeTek code came from:
https://www.ftdichip.com/Support/SoftwareExamples/FT800_Projects.htm#SampleApp

The FTDI code is multi-targeted. I have only used it under Microsoft Visual Studio Community 2017, Version 15.9.5 . You can download Microsoft Visual Studio Community 2017 at https://visualstudio.microsoft.com/downloads/

The changes to make the Crystalfontz CFAF800480E0-050SC-A1 work are minimal. I have prefaced every change with the line:

//CFAF800480E0-050SC-A1

You can search for this string, or use GIT's diff functions to see the changes. Here is a summary of the changes that were made.

SampleApp\Hdr\Gpu.h:
  Display timings for the CFAF800480E0-050SC and FT813 configutation settings.

SampleApp\Hdr\Msvc\Platform.h:
  Setting the resolution, cable, FTDI chip variant, etc.

SampleApp\Src\SampleApp.c
  Some slight modification to the demo sequence, removed duplicate touch initializations, as an example.
  
SampleApp\Src\AppCommon.c
  Cleaned up pointer usage in App_WrDl_Buffer()
  Added a comment about the SPI clock speeds possible with the FTDI C232HM MPSSE USB to SPI cable
  
SampleApp\Src\Mscv\Gpu_Hal.c
  Added a comment about the SPI modes possible with the FTDI C232HM MPSSE USB to SPI cable
  Brought in Goodix GT911 initialization code from AN_336
  Set FT813 for internal oscillator
  Made more informative FT813 detect loop.
  
Please note that Crystalfontz also has a "bare metal" Adruino sample code set that is targeted at resource-limited embedded systems, which might be better for learning the low-level details of the FT813 operation.

2019-04-18
Brent A. Crosby
Crystalfontz America, Inc.
https://www.crystalfontz.com/
