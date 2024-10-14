# RK3588 Linux6.1 SDK Note

---

**Contents**

[TOC]

---

## rk3588_linux6.1_release_v1.1.1_20240920.xml Note

### Summary of Major Updates

- Increase support for setting screen resolution in virtual terminals
- Enhance compilation environment checks
- Optimize the adbd password verification mechanism
- Optimize the user partition configuration mechanism
- Support packaging kernel modules
- Fix Debian power button sleep and wake-up exceptions
- Fix exceptions in the linux-headers development package
- Fix exceptions in usbmount automatic mounting
- Fix compilation exceptions in Ubuntu 24.04

### SDK Component Update Status

| **Module** | **Content** |
| :---------- | :--------------- |
| Buildroot              | 1. Weston upgraded to 13.0.3<br/>2. Fixed individual VNC exceptions in Weston<br/>3. Support for fixing the Year 2038 problem<br/>4. Support for uvc-gadget<br/>5. Configuration of domestic download mirrors<br/>6. Fixed exceptions in non-desktop environments for Weston<br/>7. Added support for Mupen64Plus and RetroArch game emulators, along with configuration and performance optimizations<br/>8. Added RKADK backend support<br/>9. Added Kconfig to synchronize with the official LVGL source code, supporting the automatic generation of lv_conf.h configuration files<br/>10. Fixed opengles image tearing issues in certain cases for lv_drivers<br/>11. Fixed RGA exceptions within lv_drivers<br/>12. Introduced lvgl anti-initialization<br/>13. Added support for rockchip-uvc-app<br/>14. Updated alsa-utils to version 1.2.12 from the Buildroot upstream<br/>15. Updated valgrind to version 3.23.0 from the Buildroot upstream<br/>16. Default GCC updated from 12.3 to 12.4<br/>17. Updated dhcpcd to version 10.0.8 from the Buildroot upstream<br/>18. Updated Rockchip Valhall G610 to version g24p0<br/>19. Updated Chromium to 126.0.6478.126<br/>20. Updated usbmount, using flock instead of lockfile to improve multi-partition mounting speed, ignoring persistent storage such as UFS, adding a fallback mechanism for automatic file system type detection (in case blkid reports incorrectly), and improving recognition of devices using the ATA bus (e.g., sd*)<br/> |
| Debian | 1. Updated the package-patches directory for third-party custom packages<br/>2. Added support for weston/wayland hardware acceleration<br/>3. Updated rkaiq/rknpu2/mpp/gst-rkmpp/rga2/libmali libraries to adapt to the new version of the SDK<br/>4. Upgraded the Chromium browser to the LTS version 126.0.6478.126<br/>5. Added ibus Chinese input method support<br/>6. Added the light-locker package to resolve the lock screen function ineffectiveness issue<br/>7. Added the eject package to resolve the automatic ejection function for some devices |
| Yocto | 1. Updated Yocto to 5.0.3 LTS<br/>2. Upgraded chromium to versions 124, 125, 126<br/>3. Supported Gstreamer 1.22.12 |
| RTOS | 1. Added flexbus, DAC mode, ADC mode, BSP support, and updates to the HAL core library<br/>2. Enhanced USB functionality, including adding phy id parameters, increasing core soft reset time, etc.<br/>3. Updated the ota module to support the new OTA upgrade process<br/>4. Added support for multiple audio devices and drivers |
| RKWIFIBT, RKWIFIBT-APP | 1. Improved the power consumption of audio communication through I2S/PCM during calls, reduced call latency, and enhanced the experience<br/>2. Improved Bluetooth compatibility with Windows 7/10/11<br/>3. Improved the functionality of call AT commands, such as answer/hang up/redial, solving the issue of some Windows systems not sending AT commands<br/>4. Improved the phone book function to fully obtain: complete contacts/call records/missed records, etc.<br/>5. Added a mix description to facilitate customers' management of multi-channel audio<br/>6. Added file transfer functionality and API, enabling bidirectional file transfer with mobile phones and PCs<br/>7. Newly added support for iOS system ANCS notification functionality, similar to smartwatch notification functionality<br/>8. Newly added support for 6.10 kernel Infineon module drivers: including some traditional driver upgrades and new module WiFi6/6E support |
| PREEMPT_RT, XENOMAI | 1. Ported the real-time patch of kernel 6.1.84<br/>2. Documentation updated |
| Optee | 1. Added support for optee's ufs rpmb<br/>2. Updated rk_tee_user<br/>3. Support for reading and writing Non-Protected OEM Zone area OTP data<br/>4. Support for software TA encryption key functionality, allowing customers to use TA encryption functionality without burning keys<br/>5. Support for block reading of RPMB data<br/>6. Disabled Keylad's OTP zero bit count function<br/>7. Support for OTP hardware lock functionality, allowing secure and non-secure OTP to access simultaneously |
| rkscripts | The update of the rkscript repository mainly focuses on the improvement of USB device configuration, including support for custom PID, reducing warnings, fixing typos, prioritizing the ntfs3 driver, UMS fallback mechanism, forcing local loopback, cleaning up old files during initialization, running file system checks when configuring UMS, retrying when starting fails, and adding example hook functions for rndis |
| Gstreamer | 1. Fixed occasional stuttering for some video sources<br/>2. Fixed frame skipping for some de-interlaced video sources |
| libmali | 1. Updated G31/G52/G610 to G13p0-11:<br/>- Fixed the low probability of crash when the dummy backend calls eglChooseConfigs<br/>- Supported SRGB color space FBO as a rendering target<br/>- Mali-G52 GPU added support for wayland-dummy-gbm backend<br/>2. G610 userspace driver upgraded from g13p0-10 to g24p0-3, main updates include<br/>- Supported EGL 1.5 version<br/>- Fixed issues with ARB/EXT_robustness extension interface support in g13p0 version |
| linux-rga | Fixed and improved the functionality of im2d_api, such as format checking, fence processing, and blending support |
|rk ethercat | 1. Adapted the driver program update to kernel version 6.1.84.<br/>2. Optimized the reception of data packets after sending them, which is better than receiving them after nanosleep. |
| lvgl | 1. Adapted to the RKADK backend<br/>2. Added ASR functionality<br/>3. Added sensor detection capabilities<br/>4. Added backlight control<br/>5. Added bubble prompt controls<br/>6. Adjusted the startup logic and settings interface for WiFi and BT<br/>7. Adjusted and fixed some UI interaction logic exceptions. |
| RKADK | 1. Added Picture-In-Picture (PiP) recording functionality<br/>2. Added support for JPEG FBC0/NV16 encoding<br/>3. Added API documentation:<br/>   (1) RKADK_RECORD_Single_Start<br/>   (2) RKADK_RECORD_Single_Stop<br/>   (3) RKADK_RECORD_SetPipAttr<br/>   (4) RKADK_RECORD_FileCacheSetMode<br/>   (5) RKADK_PLAYER_GetSendFrameNum<br/>   (6) RKADK_PLAYER_SetVdecWaterline<br/>   (7) RKADK_PLAYER_SetAoVolume |
| ROCKIT | Updated rockit from version V1.22 to v1.7.25. The main updates are as follows:<br/><br/>AUDIO:<br/>1. Expanded the number of audio channels.<br/>2. Removed JSON parsing from VQE.<br/>3. Updated SFS and EQ parameters to support AI-NR.<br/>4. Added support for parsing EQ features.<br/>5. Added support for parsing AGC of AO (RX) VQE.<br/>6. Added an option to use MONOTONIC for PCM when BOOTTIME fails.<br/><br/>VI:<br/>1. Prevented repeated initialization of the V4L2 device.<br/>2. Implemented post-processing for VI.<br/>3. Fixed frame rate issues with HDMI RX interlaced scanning.<br/>4. Fixed exceptions with HDMI RX YUV422 non-64-byte alignment.<br/>5. Added an API to enable single-frame capture.<br/><br/>VO:<br/>1. Added documentation for RK3576.<br/>2. Removed the dependency of the VO module on the GPU for initializing the Weston desktop.<br/><br/>VENC:<br/>1. Supported resolution changes in VENC.<br/>2. Updated the RC parameters for VENC.<br/><br/>VPSS:<br/>1. Configured the hardware VPSS sequence.<br/>2. Implemented adaptation to the hardware ISP.<br/>3. Updated VPSS documentation to version v1.1.5. |
| AUDIO | 1. Enabled the OUT1/OUT2 switch of the ES8388 sound card by default<br/>2. Added initialization configuration for rk730<br/>3. Added initialization configuration for alsa-utils and alsactl<br/>4. Added support for the ES8388 sound card. |
|RKIPC | 1. ISP white balance/contrast/hdr/frame rate issues<br/>2. VO compatibility with HDMI and MIPI displays, and fixed deinitialization issues<br/>3. Corrected OSD color and frame problems<br/>4. Updated AVS stitching parameters<br/>5. Adapted to rkaiq version 6.8.0, using functional-level APIs for all, fixing dozens of related issues, and improving stability<br/>6. Added rockiva face and human body recognition frame functions<br/>7. Supported HDMI and MIPI displays<br/>8. Optimized OSD-related logic<br/>9. Supported AIISP functionality |
| RKAIQ | Updated RKAIQ version to v6.8.0:<br/>1. Supported ldc/ldch<br/>2. Solved mirror/flip, wb, and other imgproc interface issues<br/>3. AIQ default direct pass-through mode, rk_aiq_uapi2_sysctl_setMulCamConc interface 1103b failure<br/>4. Fixed 4k ae, awb exceptions<br/>5. Updated AF IQ parameters affecting old platforms such as 1106, 3588, etc., cpp versions<br/>6. Solved the reddish bias problem caused by quick start blc<br/>7. Solved some bugs in group mode<br/>8. IQ deleted YME, CPSL<br/>9. Solved cac, ldch memory leaks<br/>10. Updated IQ structure: btnr, hsv, histeq, enh<br/>11. Imgproc: Fixed the issue of not restoring the setting of btnr when preparing to set the mirror/flip<br/>12. Fixed the ae flicker problem of isp3x/isp21 caused by blc since v5.1.3<br/>13. AeHandler: Set the ISO value to the shared information when aiq is prepared<br/>14. Solved the problem of settings like dehaze not taking effect in the 3576 surround view mode<br/>15. RK3576 supports dumpsys, an additional 30kb |
| NPU | Updated RKNN from V2.0.0-beta01 to V2.2.0<br/>1. Supported RK1103B<br/>2. Supported RK2118<br/>3. Supported Flash Attention (Only RK3562 and RK3576), optimized transformer model performance<br/>4. Optimized support for int32 and int64 data types<br/>5. Supported more operator fusion<br/>6. Operator optimizations, such as softmax, hardmax, MatMul, etc.<br/>7. Supported RK3576 W4A16 symmetric quantization<br/>8. Supported installation via PYPI<br/>9. Supported Python 3.12<br/>10. rknn_model zoo supports demos like mobilesam, whisper Chinese, zero copy, etc. |
| MPP | MPP updated to V1.0.7, with the following main changes:<br/>1. Merged encoder tuning branch code<br/>2. Optimized MppTrie structure<br/>3. Supported H.265's mlvec LTR related functions<br/>4. Supported H.264's hdr information parsing<br/>5. Fixed the stream abnormality issue with tsvc short delay output in CAVLC cases<br/>6. Fixed the exception when two consecutive sps occur during info change<br/>7. Fixed the maximum mv length marking issue in H.264 sps<br/>8. Fixed GDR related issues<br/>9. Fixed issues related to low-latency output<br/>10. Fixed some memory leak issues<br/>11. Fixed some decoding issues with av1, H.265, and mpeg2 |
| U-boot, rkbin |  1. Updated RK3576 DDR binary to V1.07, resolving the instability of LPDDR4X 2112MHz on a few boards due to unreasonable rx dqs vref configuration<br/>2. Updated RK356X DDR binary to V1.23, mainly solving the following issues:<br/> a. Added read/write Vref training to improve DDR signal compatibility.<br/> b. Enabled rx odt at LPDDR4/4x 780MHz to improve stability.<br/> c. Solved compatibility issues with some LP4x 324M.<br/> d. Resolved potential capacity detection anomalies or ECC activation bugs for DDR4.<br/>3. Updated the RK3326/PX30/RK3358 DDR binary to V2.11, addressing the issue of DDR4 capacity detection missing by half or a quarter for PX30/RK3326/RK3358.<br/>4. Resolved the failure to enter the U-Boot Loader using the Linux-6.1 kernel on the RK3568 platform.<br/>5. Supported SPI Nand CONT_READ.<br/>6. Added SPI Nor Auto_Merge code to facilitate the convenient operation of applying 2 on-chip SPI Nor flash memories to 1 device.<br/>7. Modified the erase protection function to allow vendor storage data to be erased.<br/>8. Modified MPHY power supply judgment to resolve some UFS support anomalies.<br/>9. Added controller CRU reset to resolve some UFS initialization anomalies. |
| Kernel 6.1 | 1. Resolved the WIFI FW communication anomaly after enabling ASPM L1SS on RK3588 PCIe and resuming from hibernation.<br/>2. Added the function for rk3588 to enable optee to respond to Linux kernel interrupts.<br/>3. Resolved the silent playback issue when switching from 48k sampling rate to 16K/8K on RK809·RK817-(A version) for the first time.<br/>4. [I2STDM] Resolved the low-probability 1-bit shift issue in the RX under TRCM-TX scenario.<br/>5. Resolved the issue of multi-channel audio switching not working and recording anomalies on RK3568 Debian.<br/>6. Resolved the issue of RK3568 SATA not being recognized.<br/>7. Resolved the RK3566 Bluetooth failure anomaly.<br/>8. Resolved the page fault issue when iep2 is in I1O1T mode on some resolutions. |
| Tools | 1. RKDevTool upgraded from v3.31 to v3.32.<br/>2. pin_debug_tool upgraded from v1.13 to v1.16.<br/>3. Updated RKDevInfoWriteTool.<br/>4. Updated RKDevTool rockdev. |
| Documentation | 1. Updated patches related to Real-Time-Performance for kernel 6.1.84.<br/>2. Updated buildroot csv.<br/>3. Imported more customer-demanded development documents such as DMSC\FLEXBUS.<br/>4. Updated the support list for eMMC/DDR/Nand.<br/>5. Added RTT-related documentation.<br/>6. Updated IP-related documents for Linux, general, and other categories.<br/>7. Updated the software development guide, adding support for RK3576 and more features. |

## rk3588_linux6.1_release_v1.1.0_20240620.xml Note

The new features and functionalities of the SDK, along with a comprehensive set of updates, span across a wide array of areas including tool and script updates, configuration file improvements, specific chip support, kernel and system build enhancements, system optimizations, security and permissions updates, support for specific hardware or features, bug fixes, and documentation and example updates. The goal of these updates is to enhance capabilities, fix bugs, improve user experience and system performance, and ensure better security and compatibility.

### Summary of Major Updates

- Tool and Script Updates: Enhanced functionalities, bug fixes, and improved user experiences.
- Configuration File Improvements: Optimized help information and default configurations.
- Chip-Specific Changes: Updates and improvements to configurations for chips like rk3308, rk3588, and rk3562.
- Kernel and System Build: Build script improvements to avoid warnings and fix compilation errors.
- Tool Additions: Addition of new tools such as inotify-tools, adb support, etc.
- System Optimizations: Improvements in system startup, logging, storage checks, etc.
- Security and Permissions: Updates to security scripts and configurations, enhanced kernel security.
- Support for Specific Features: Added support for specific hardware or features like amp_mcu, rk3576 multi-camera support, etc.
- Bug Fixes: Fixed compilation errors, type errors, warning messages, etc.
- Documentation and Example Updates: Updated README files and example codes to reflect the latest changes and features.

### Updates to SDK Components

- Security Upgrades: Security updates for Linux Kernel, Buildroot, Yocto, Debian, etc.
- Buildroot Updates: Fixes for ncurses library, configuration updates for lvgl and lvgl_demo, added support for packages, etc.
- Debian Updates: Solved issues with the Cheese application, updates to mpp/libv4l/gst-rkmpp/rga2 libraries, etc.
- Yocto Updates: Updates to Yocto 5.0 LTS, upgrades to the v4l-rkmpp package, etc.
- RTOS Updates: Multiple updates to Rockchip BSP, including support for platforms like rk3588-64 etc.
- RKWIFIBT Updates: Added compatibility with more wireless network hardware, updates to applications and drivers.
- Updates to PREEMPT_RT, XENOMAI: Real-time patch porting, documentation updates.
- RKSCRIPTS Updates: Fixed UVC errors, updated product ID lists.
- Updates to Xserver, Gstreamer, libmali, liux-rga, IVA, LVGL, RKADK, ROCKIT, RKUPDATE, AUDIO, RKIPC, RKAIQ, NPU, DPDK, MPP, Kernel6.1: Extensive updates including feature additions, performance improvements, bug fixes, etc.
- ROCKCHIP-TEST: Updated reboot test scripts, added support for rknn_demo.
- Tool Updates: Upgraded various tools such as rk_ddrbin_tool, upgrade_tool, etc., and added new tools.
- Documentation Updates: Updated a large number of development documents, including real-time performance, licenses, customer requirements, kernel support, etc.

## rk3588_linux6.1_release_v1.0.0_20231220.xml Note

```
- The first release version
```
