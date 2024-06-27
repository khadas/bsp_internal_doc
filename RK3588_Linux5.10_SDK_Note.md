# RK3588 Linux SDK Note

---

**Contents**

[TOC]

---

## rk3588_linux_release_v1.5.0_20240620.xml Note

The new features and functionalities of the SDK, along with a comprehensive set of updates, span across a wide array of areas including tool and script updates, configuration file improvements, specific chip support, kernel and system build enhancements, system optimizations, security and permissions updates, support for specific hardware or features, bug fixes, and documentation and example updates. The goal of these updates is to enhance capabilities, fix bugs, improve user experience and system performance, and ensure better security and compatibility.

### Summary of Major Updates

- Tool and Script Updates: Enhanced functionalities, bug fixes, and improved user experiences.
- Configuration File Improvements: Optimized help information and default configurations.
- Chip-Specific Changes: Updates and improvements to configurations for chips like rk358.
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
- Yocto Updates: Updates to Yocto 4.0.17 LTS, upgrades to the v4l-rkmpp package, etc.
- RTOS Updates: Multiple updates to Rockchip BSP, including support for platforms like rk3588-64 etc.
- RKWIFIBT Updates: Added compatibility with more wireless network hardware, updates to applications and drivers.
- Updates to PREEMPT_RT, XENOMAI: Real-time patch porting, documentation updates.
- RKSCRIPTS Updates: Fixed UVC errors, updated product ID lists.
- Updates to Xserver, Gstreamer, libmali, liux-rga, IVA, LVGL, RKADK, ROCKIT, RKUPDATE, AUDIO, RKIPC, RKAIQ, NPU, DPDK, MPP, Kernel5.10: Extensive updates including feature additions, performance improvements, bug fixes, etc.
- ROCKCHIP-TEST: Updated reboot test scripts, added support for rknn_demo.
- Tool Updates: Upgraded various tools such as rk_ddrbin_tool, upgrade_tool, etc., and added new tools.
- Documentation Updates: Updated a large number of development documents, including real-time performance, licenses, customer requirements, kernel support, etc.

## rk3588_linux_release_v1.4.0_20231220.xml Note

This version mainly describes the addition of new features, improvements to existing functionalities, and updates to various components in the SDK.

### SDK New Features and Feature Improvements

- **Comprehensive Core Component Upgrade:** The core components of the SDK have been thoroughly updated to adapt to a wider range of functional requirements and significantly improve system security and performance.

- **New Repositories:** Added numerous new repositories to the SDK, such as uvc_app, uac_app, amp, rtthread, etc., to meet the development needs of various products more comprehensively.

- **New Patches Directory:** This directory contains enhanced features like PREEMPT_RT, XENOMAI, etc., aimed at improving the customizability and optimization efficiency of the SDK.

- **Convenient Log Generation Command:** With the generate_logs command, users can now package log information more conveniently, simplifying the fault diagnosis and analysis process.

- **SDK Version Information Display:** Added version information display during the compilation process, making it easier for users to effectively manage and track different versions of the SDK.

- **Enhanced Dependency Check and Prompt:** Introduced a compilation dependency check and prompt feature in the SDK to ensure the completeness and consistency of the development environment.

- **Integration of More Debugging Tools:** More practical debugging tools have been built into the SDK, helping users to debug applications and optimize performance more efficiently.

- **Unified Color Coding of Log Prompts:** During the compilation process, log prompts have been color-coded to distinguish between messages, warnings, errors, and other levels.

- **Updated wifibt Script:** Updated the wifibt script, including commands like wifibt-chip, wifibt-info, and more, further enhancing wireless and Bluetooth functionality.

- **Support for the clean Module:** Introduced the clean module, helping users to clean the SDK environment more conveniently, maintaining the system's consistency and stability.

- **Input-event-daemon Key Function:** Added input-event-daemon key processing function, unifying the handling of power and other keys.

- **Support for Auto-Resize of ubi Partitions:** Supports the auto-resize function of ubi partitions, providing more flexible storage management options.

- **Package-file Editing Command:** Allows editing of package-file through the SDK, enabling custom management of software packages.

- **yocto Support for Customizing local.conf:** Added support for customizing local.conf in yocto.

- **Enhanced rootfs Configuration:** Comprehensive optimization and updates have been made to various rootfs-related configurations.

- **Integration of Precompiled android-adbd:** Replaced the original android-tools with precompiled android-adbd, improving system compatibility and efficiency.

- **Default Compilation Target Adjustment:** Modified the default compilation target setting, now defaulting to compile only release firmware.

- **Support for Boot Animation Configuration:** Added support for configuring boot animations, enhancing user experience.

- **Optimized Packaging Process for misc Firmware:** Organized and optimized the packaging process for misc firmware, improving efficiency.

- **Independent Kernel Configuration Support for recovery:** Added support for using an independent kernel configuration for recovery.

- **Support for Setting Specific rootfs Format for recovery:** Allows users to set a specific rootfs format for recovery.

- **Updated Security Compilation Mechanism:** Updated the compilation mechanism for security components, making it more convenient to enable and debug.

- **Added RT-LINUX Support:** Added support for Real-Time Linux (RT-LINUX), meeting the real-time system requirements of some products.

- **Fixed sysv System Service Level Error:** Resolved the error in automatically generating sysv system service levels.

- **Fixed yocto Repeated Compilation Issue:** Solved the abnormal problem of repeated compilation in the yocto environment.

- **Fixed AB Partition Packaging Issue:** Resolved the issue with AB partition packaging, ensuring more stable and reliable partition management.

- **Data Storage Migration:** Migrated the SDK platform data from Baidu Enterprise Network Disk to Lenovo Network Disk Filez (New), ensuring data stability and accessibility.

### Updates on SDK Components

#### Security Updates

Recent systems and software frameworks have released important security updates, including fixes for security vulnerabilities and version upgrades of some key components. The details are as follows:

1. **OP-TEE OS:** Fixed security vulnerabilities, details can be found in [Patch Brief #435185](https://redmine.rock-chips.com/issues/435185).

2. **Linux Kernel:** Security update from 5.10.160 to 5.10.198.

3. **Yocto:** Security update to version 4.0.13. More information can be found in the [official documentation](https://docs.yoctoproject.org/migration-guides/release-notes-4.0.13.html).

4. **Debian:** Security update to version 11.8. Detailed information is available in the [official documentation](https://docs.yoctoproject.org/migration-guides/release-notes-4.0.13.html).

5. **Buildroot:** Security update to the 2023.08 version, mainly updating core components related to the platform.

Here are the version updates for some key components:

- glmark2: Updated from 2021.02 to 2023.01
- glibc: Updated from 2.36.81 to 2.37.2
- valgrind: Updated from 3.18 to 3.21
- binutils: Updated from 2.38 to 2.40
- meson: Updated from 1.0.0 to 1.2.0
- wayland-protocols: Updated from 1.31 to 1.32
- wayland: Updated from 1.21 to 1.22
- seated: Updated from 0.7.0 to 0.8.0
- weston: Updated from 11.0.1 to 13.0.0
- gcc: Updated from 11.3 to 12.3
- pixman: Updated from 0.40.0 to 0.42.2
- gstreamer: Updated from 1.20 to 1.22
- libglib2: Updated from 2.68.4 to 2.76.1
- util-linux: Updated from 2.37.2 to 2.39.1
- irqbalance: Updated from 1.8.0 to 1.9.0
- Updates also for xorg-xserver, memtester, bluez-alsa, pulseaudio, bluez5_utils, hostapd, wpa_supplicant, neatvnc, etc.

These updates have enhanced the system's security and stability. It is very important for users of these software or operating systems to apply these updates promptly to protect the system from known vulnerabilities.

#### Update Buildroot

- Updated memtester and stressapptest, adding DDR stress testing and facilitating problem localization
- Updated Buildroot Launcher, adding a configurable status bar
- Weston added functions to shut down and restart the display service
- Added support for setting ubifs size
- Added archives directory structure, preloading some download packages
- Added support for lvgl and lvgl_demo
- Added ROS2 support
- Updated packages such as bluez-alsa/pulseaudio/bluez5_utils/hostapd/wpa_supplicant, adding support for features like hfp backend and wpa3
- Updated rkwifibt-app
- Upgraded Chromium version to 114.0.5735.198, adding support for H265/AV1 decoding, enabling WebGPU, and enhancing Chromium performance
- Updated Secureboot's AVB and FIT, improving compatibility
- Updated core components such as Gstreamer, weston, wayland, glibc

#### Update Debian

- Optimized Debian's Cheese app

1) Fixed the issue where Cheese camera, after opening for recording and then closing, enters a loop when reopened.
2) Added support for H264 encoding. Since Cheese only supports VP8 encoding by default, and many RK chips have weak or no support for VP8 encoding, H264 encoding support is added by default.

- Updated Xserver

1) Filtered out error messages for Mali DDK not supporting GBM_FORMAT_R8
2) Fixed the sliding lag issue in the top-left menu bar of the Xfce desktop
3) Fixed the issue where FlipFB, when enabled to prevent tearing, caused rotation functionality to malfunction
4) Fixed hardware mouse position error in cropped screens
5) Resolved screen rotation functionality issues
6) Increased the number of xv videos from 16 to 128
7) Added support for ARM Mali-4xx utgard DDK

- Updated rkwifibt with new scripts for enhanced functionality and compatibility

- Updated chromium-x11 version from 91.0.4472.164 to 114.0.5735.198

1) Support for HEVC (H265)
2) Enable VEA
3) Support for AV1 in V4L2 VDA
4) Enable WebGPU

#### Update Yocto

- Implemented automatic login for serial port
- Implemented automatic mounting for USB peripherals
- Implemented automatic pairing for wifibt
- Added default desktop icon layout in Yocto (synchronized with buildroot)
- Added support for pulseaudio
- Added support for ntp time synchronization

#### Update Kernel/rkbin

- Resolved reboot freeze issue.
- Added Kernel EDAC driver support for DDR ECC information.
- Added ISP driver sleep and wake-up interface functions.
- Updated RKNPU driver to 0.9.3.
- Enabled CONFIG_ARM64_USE_LSE_ATOMICS for better performance of LSE over LL/SC on ARMv8.
- Added minidump support.

#### Update libmali

1. Updated G31/G52/G610 libraries to g13p0-10.

- Fixed Mali alpha blending UI error, reverted previous alpha blending workaround.
- Added EGL config for OPENGL ESRGB888, Depth=24, Alpha=0 --visual-config='a=0:buf=24'.
- Support for gbm_bo_import GBM_BO_IMPORT_WL_BUFFER (NV12).
- Support for gbm_bo_create DRM_FORMAT_R8.
- Fixed alpha bending issue in glmark2 terrain scene.
- Adaptation for gl4es.
- Resolved file descriptor leak: gbm_device_get_fd returns fd directly, no dup.

2. Updated libmali headers.

- OpenCL Bump to tag [v2023.04.17](https://github.com/KhronosGroup/OpenCL-Headers.git)

#### Update RKAIQ

Updated RKAIQ to V5.0x4.1, significantly reducing CPU usage and memory consumption, with new API additions for ccm and awb calibration interfaces, and added support for AFD (Auto Flicker Detection) algorithm. Main changes include:

- Fixed longFrameMode parameter error in image processing.
- Resolved crashes when testing entering and exiting group mode.
- Supported periodic awakening from sleep state to process image data, achieving one frame per second functionality.
- Optimized startup process for quick start and one frame per second processing.
- Added Artificial Intelligence Noise Reduction (AI NR) feature.
- Enabled device-side JSON to BIN data conversion.
- Supported single or dual AIQ feature loading during quick startup.
- Enabled mapping AWB IQ parameters from primary to secondary camera.
- Addressed bugs in processing 8K images.
- Fixed issues with Auto Exposure (AE) not functioning on all platforms.
- Resolved issues with setting maximum frame rate.
- Addressed absence of Auto Focus (AF) statistics during quick start.

> Note:
> Kernel needs to match; ISP and VICAP drivers require a series of sleep-wake patches.
> AIQ unified the quick start and sleep-wake processes. The application process for quick start needs to be modified to only start AIQ once.

#### Update MPP

- Supported Kernel 6.1, fixed dma-heap issues on Kernel 6.1.
- Changed input/output buffer from uncache to cachable to improve CPU efficiency.
- Supported single-channel four-frame JPEG parallel encoding on RK3588.
- Added encoder support for variable frame rates.
- Added different mode buffer samples in mpi_dec_test.
- Optimized VP8 decoder's debug feature.
- Eliminated the need for the HAVE_DRM flag.
- Fixed frame dropping issue during MPEG4 stream switching.
- Addressed MPEG2 decoder pts update mechanism issue.
- Fixed segment info missing in encoder skip mode path.
- Resolved issue with the AV1 decoder handling empty EOS packets.
- Added markdown documentation for MPP development reference in the codebase.
- Encoder can output more statistical information.
- Addressed issues with unsupported 444 lossless mode.
- Fixed repeated release issue in camera_source.
- Resolved VP9 decoder switching between FBC and non-FBC issue.
- Addressed issues with using ion allocator despite dma_heap presence.
- Added frame-level qp configuration and qbias configuration to encoder.
- Fixed prolonged encoding time in 3588 tsvc configuration.
- Addressed long GOP encoding stream errors.
- Defined default value for MppFrame color space.
- Fixed some issues related to GDR encoding and decoding.

#### Update gstreamer-rockchip

- Fixed playback issues with some special sources.
- Supported asynchronous encoding.
- rkximage now supports NV16_10B.

#### Update rkwifibt

- Added more WIFIBT debugging information.
- Updated firmware to support more older modules.
- Updated bcmdhd driver to 101.10.591.x, adding Kernel 6.1 support and some bug fixes.

#### Update RKNN

Updated RKNN to V1.6.0, with the following main fixes:

- Optimized transformer support.
- Enhanced dynamic shape support.
- Improved standalone API support for Matmul.
- Optimized default parameter for rknn.config's target_platform.
- Enhanced support for GRU/LSTM/transpose/reshape/softmax/maxpool, etc.
- Improved support for high-resolution models.
- Enhanced LLM support.
- Boosted multi-batch support.
- Added GPU backend framework support in rknn runtime, implementing some operators like matmul.
- Reduced initialization time and memory usage of rknn_init.
- Supported OPSET 12~19 ONNX models.
- Enabled support for custom operators (including CPU and GPU).
- Enhanced operator support like convolution with dynamic weights, Layernorm, RoiAlign, Softmax, ReduceL2, Gelu, GLU, etc.
- Added support for Python 3.7/3.9/3.11.
- Added rknn_convert functionality.
- Enhanced MatMul API, e.g., increased K limit length, RK3588 supports int4 * int4 -> int16 computation.
- Updated user manual.
- Restructured rknn model zoo, adding support for detection, segmentation, OCR, license plate recognition, etc.

#### Update Tools

- Resolved system upgrade issues caused by partition alignment.
- Updated SD tool to V1.76.
- Updated RKDevTool to V3.19.
- Updated Windows upgrade_tool to V2.23.
- Updated Rockchip_HdcpKey_Writer to V1.0.5.

#### Update Documentation

- Updated SDK application process and Redmine system usage instructions.
- Updated DDR-related documentation, integrated into a single development document.
- Added Common/Security and other document directories.
- Added ROS2 documentation.
- Added English documentation for Rockit.
- Added RT performance testing and analysis documentation.
- Added MCU_RGB and MIPI_DSI2 display development documentation.
- Updated development documentation for AVL/USB/PCIE/MMV/USB/NVM/SPI/PERF/WESTON, etc.
- Updated RK3588 release documentation.

## rk3588_linux5.10_release_v1.3.0_20230920.xml Note

1 **Update Debian**

- Optimize Debian's Cheese app

1) Fixed a loop issue when the Cheese camera was turned on for recording and then turned off again
2) Add H264 encoding support, as Cheese only supports VP8 encoding by default, but many RK chips have    weak or unsupported VP8 encoding So by default, support for H264 encoding is added

- Update Xserver

1) Filtering Mali DDK does not support GBM_FORMAT_R8 error issue
2) Fix the issue of the menu bar sliding and getting stuck on the top left side of the Xfce desktop
3) Fix the issue of abnormal rotation function after opening the anti tearing FlipFB

- Update rkwifibt with new script processing for more complete functionality and compatibility

- Update Chromium x11 version from 91.0.4472.164 to 111.0.5563.147

1) Drop is_official_build=false GN arg for optimization
2) Support HEVC (H265)
3) Enable VEA
4) Support AV1 in V4L2 VDA

2 **Update Buildroot**

- Update Buildroot Launcher and add status bar for configuration

- Weston adds features for closing services and restarting display services

- Increase support for ubifs size setting

- Add the archives directory structure and preset some download packages in advance

- Update lvgl_demo

- Update components (glmark2\glibc\wayland\weston...)

3 **Update Yocto**

- Implement automatic login serial port function

- Implement the automatic mounting function of USB peripherals

- Implement the automatic configuration function of wifibt

4 **Update rockit**

- update rockit version to v1.7.12

5 **Update libmali**

- Update G31/G52/G610 to g13p0-8

1) support the gbm_bo_import GBM_BO_IMPORT_WL_BUFFER
2) add the gbm_bo_create DRM_FORMAT_R8
3) Error in glmark2 terrain scene alpha binding screen
4) Adaptation of gl4es
5) Solving fb leakage:gbm_device_get_fd directly returns fd without executing dup

- Update libmali header file

6 **Update rkbin**

- Update RK3588 BL31 to V1.42

1) Optimize the time of system resume.
2) Support any cpu to do system suspend/resume.
3) Support all pwm int to wakeup when virtual-poweroff.
4) Support L3 partition.
5) Update configuration of ddr vref_inner.
6) Support to config MCU sleep parameter through DTS.
7) Add support to reset vop sub mem pd.

- Update  RK3588 BL32 to V1.14

1) Pseudo random number seed will be set by default.
2) Supports read and write security flag interfaces.
3) Support check ta encryption key is written.
4) Fixed hardware crypto probability crash issue after enabling dynamic memory

7 **Update Kernel**

- enable cluster frame reset for rk3588 vop2

- amend to improve USB compatibility for rk3588

- add rk3588 evb7 v11 dts to support

8 **Update rkaiq/rkisp**

Update RKAIQ version to V5.3.0, RKISP driver version to V2.3.0

- fix drc and hdrmge err for multi sensor
- fix 3dlut for multi sensor
- fix stream init pause state
- fix refer to sram info for multi sensor
- add api get isp work mode for rockit
- remove isp_config_hdrshd
- add lock to save tb info
- fix list buf delete err
- fix get tb info
- add iqtool video for isp21
- fix image effect for frame two-run
- fix underperformance for frame two-run
- support unite mode for isp32
- demo: smartIr: fix compile error
- AF: fix SlowStep is too small
- PDAF: support pd offset in otp
- AE: fix IsReconfig bug caused by f99564a

9 **Update tools**

- Update SD tool to V1.76

1) Fix using empty misc size greater than 64k, SD card upgrade tool may have write errors.

- Update RKDevTool to V3.19
- Update window upgrade_tool to V2.23
- Update Rockchip_HdcpKey_Writer to V1.0.5

10 **Update documents**

- Update the SDK application process and instructions for using the Redmine system
- Update DDR related documents and integrate them into one development document
- Add Common/Secutiry document directory
- Add Rockit English documents
- Add RT performance related testing and performance analysis documents
- Add MCU_RGB and MIPI_DSI2  Display Development Document
- Update AVL/USB/PCIE/MMV/USB/NVM/SPI/PERF/WESTON/and other related development documents
- Update the relevant documents required for RK3588 release

11 **Update device/rockchip*

- Add `generate_logs` command is used to package log information.
- Compilation adds prompt SDK version information
- Default empty misc, go to resize partition in OS
- Support for clean module
- Yocto adds default desktop icon layout (synchronized with buildroot)
- Add some dependency checks and prompts for SDK compilation
- Fix AB partition packaging issue
- Fix issue with aarch64 precompiled tool not being able to use
- Yocto supports 3288w
- Ui partition supports automatic resizing
- Support command editing package file
- The yocto SDK supports automatic mounting of USB drives
- Default installation of rktoolkit for all SDKs
- Generate misc firmware from script at compile time
- Using a new wifibt script
- Added support for 'RK3588 EVB7 V11'  boards

## rk3588_linux5.10_release_v1.2.1_20230720.xml Note

1 **Update Debian**

- Filtering Mali DDK does not support GBM_FORMAT_R8 error issue
- Fix the issue of the menu bar sliding and getting stuck on the top left side of the Xfce desktop
- Fix the issue of abnormal rotation function after sretting FlipFB to always
- Add support for Cheese H264 encoding and default to using H264 encoding
- Update rkaiq to release v5.0x1.3
- Update mpp/gstreamer rockchip

2 **Update Buildroot**

- Update lvgl
- Update weston to suppor some issues
- Update rkaiq to release v5.0x1.3
- Support pre-downloaded archives for download

3 **Update rkbin**

- Update bl31 supports to reset vop sub mem pd
- Update ddr.bin to fix init fail issue that max freq between 1066-1600MHz
- Update ddr.bin to fix the issue painc in ddrbin caused by multiple initialization of DDR

4 **Update Kernel**

- Add vicap compatible with rk3588s2
- update vop to support dual connector split mode
- Update of RK3588J and RK3588M frequency Voltmeter

5 **Update documents and tools**

- Upgrade pin_debug_tool to v1.12
- Upgrade programmer_image_tool to v1.26
- Upgrade SDDiskTool to v1.75
- Upgrade FactoryTool to v1.81
- update RKDevTool to v3.18
- Upgrade programming_image_tool to v1.26
- Upgrade Linux_Upgrade_Tool to v2.22
- Update the relevant documents required for RK3588 release

## rk3588_linux_release_v1.2.0_20230620.xml Note

1 **Update device/rockchip**

- Fix Secureboot

2 **Update Debian**

- Update Blueman to resolve abnormal Bluetooth power management issues after sleep wake-up
- Update alsa to address audio issues after sleep wake-up
- Update rkaiq to v5.0x1.2-rc5
- Update mpp/gstreamer rockchip

3 **Update Buildroot**

- Resolve task - c command line exception issues
- Add Weston alpha channel support
- Update rkaiq to v5.0x1.2-rc5
- Add Gstreamer NV16_10LE40 format support
- Increase the use of domestic kgithub image sources for DL packages

5 **Update Kernel**

- Add rk3588-evb7-v11 board to support
- Update RK817/RK809 driver to address sleep wake-up issues
- Fix low-volt-mem-read-margin
- Fixed the rkvenc1 init frequency
- Assign VOP_ACLK to 750MHZ for rk3588-linux.dtsi
- add camera sensor configuration for rk3588s-evb1-lp4x-v10-linux.dts
- Fixed the init frequency

6 **Update documents and tools**

- Update Rockdev to resolve address resolution exceptions
- Update the relevant documents required for RK3588 release

## rk3588_linux_release_v1.1.1_20230520.xml Note

The main update list is as follows:

1 **Update device/rockchip**

- buildroot/yocto installs Chinese fonts by default
- recovery does not install additional overlay
- Fixed hostname exception after dynamically switching rootfs
- Add dependency check and installation prompt
- Add repair owner permission
- Fix the problem that repeated compilation of yocto post-rootfs does not execute

2 **Update recovery**

- Repair press the recovery button to reset to enter the system, nothing is displayed
- U disk upgrade startup support
- Solve the problem that the first upgrade of the SD card starts abnormally
- Fix userdata partition unmount failure

3 **Update Debian**

- Solve the problem of cheese app recording screen freeze
- Support xfce4 power management configuration
- There are hidden problems in updating system permissions
- Update rkwifibt to solve problems related to switch or sleep wake-up
- Update adb to add some feature support
- Update mpp and gstreamer-rockchip
- Update rockchip-test to V2.1
- Solve the abnormal double-click problem of Debian desktop icons

4 **Update Buildroot**

- Optimize rknpu2 compilation configuration
- Add support for setting the location of Gstreamer glimagesink/xvimagesink plugin
- Fixed crash when Weston destroys dmabuf
- Add power/dictionary pen/sweeping machine and other product configurations
- Added support for external toolchains
- Add support for GCC8.X
- Fix the problem that the video source size may overflow after Gstreamer kmssink scaling
- Add Chromium 111.0.5563.147, support video H265 decoding
- Update Frecon, solve zoom and switch VT1 support
- Update rockit to v1.7.4
- Add support for lvgl demo

5 **Update rkbin**

- Adjust the pvtpll configuration of cpu/gpu/npu according to the correlation chip test results
- Increase chip version judgment
- Update RK3588 lp5 mr configuration \ improve the stability of hdmirx related functions \ add ddr spread spectrum mode / optimize boot time.

6 **Update Kernel**

- Solve the problem that the rk3588 hdmiphy lane skew is too large
- Update rknpu driver to V0.8.8
- Solve isp switch abnormal error
- System panic after opening KASAN with Logo buf non-PAGE aligned

7 **Update Uboot**

- fastboot: Burning more than 4G firmware causes the system to fail to start
- System panic after opening KASAN with Logo buf non-PAGE aligned

## rk3588_linux_release_v1.1.0_20230420.xml Note

The main update list is as follows:

### SDK update main core component versions

- Kernel upgrade from 5.10.110 to 5.10.160
- Update Debian to 11.6
- Update Yocto to 4.0.9
- Update Buildroot to November 2021
- Weston updated to 11.0.1
- Gstreamer updated to 1.22

### SDK optimization and adjustment

- Reconstruct SDK configuration compilation mechanism
- Adjusting the compilation mechanism of the wifibt module
- Import a new version of Camera rkaiq to optimize its functionality and performance

### SDK New features

- Added Linux headers support, making it convenient for third-party applications without the need for kernel compilation and debugging
- Added yocto support for x11
- Added gst mpp support for av1
- Added gst mpp support for afbc encoding
- New support for OTA differential function
- New UDL support
- Added adaptation support for libcamera
- New rk3588 venc support for dynamic voltage regulation to improve stability

### SDK main fix issues

- Fix ubi format partition packaging and mounting issues
- Fix recovery mount partition exception
- Fix [webgl](https://webglsamples.org/aquarium/aquarium.html) Flash screen issue
- Fixed the issue of resetting the time to 0 after standby wake-up
- Fix fiq debugger driver, serial port RX interference, resulting in system stuck
- Fixed a low probability of error after starting KASAN: KASAN: use after free in rga_ job_ next
- Support for addressing Weston touch related configurations
- Solve HDMI/MIPI plug and display issues
- Solve the problem of PDM recording channel confusion
- Resolve the issue of playback noise caused by RK809 · RK817-pdm recording
- Solving the unexpected startup of PMU MCU during sleep of rk3588 may cause ddr data to be overwritten
- Improve the stability of RK3588 DDR

## rk3588_linux_release_v1.0.3_20220920.xml Note

- Upgrade bifrost DDK from g12p0-01eac0 to g13p0-01eac0
- Upgrade NPU verison to V1.4.0
- Refactor rkwifibt code
- Update Weston to support to set cursor size and launchers
- Add pm-utils for PowerManager
- Use chromium R88 by default
- Update some packages to buildroot upstream version
- Update Linux_Upgrade_Tool to v2.17
- Update UEFI
- Update audio/crypto/sata/PCIe/usb/rockit/gstreamer/rga... docs

## rk3588_linux_release_v1.0.2_20220820.xml Note

- Remove libglCompositor/avb repositories
- Add rockit/librkcrypto repositories
- Fix a few download/extract errors
- Upgrade Weston version to 10.0.1 and improve its stability
- Add support for buildroot X11 related functions
- Add support for Linux enlightment Wayland desktop
- Upgrade kernel to 5.10.110
- Update the chromium browser version of Debian to R101
- Update Linux_Upgrade_Tool, RKDevTool and SDDiskTool
- Improve HDMI compatibility and HDMI-IN stability
- Upgrade GStreamer of builderroot to 1.20.3 to improve audio and video compatibility
- Add gamma support for xserver and fix the problem of multi touch
- Update loader to improve chip stability
- Update NPU and fix memory leakage
- Update MPP to improve compatibility
- Update docs

## rk3588_linux_release_v1.0.1_20220620.xml Note

- Fixes Secureboot function issue
- Fixes SD boot and upgrade issue
- Update docs include secureboot,pinctrl,display,AVl and so on
- Update kernel to fix some issues
- Add RK3588M Socs to support
- Add RK3588 evb7 to support single pmic hardware design

## rk3588_linux_release_v1.0.0_20220520.xml Note

- Update all the projects with lastest
- Update kernel/uboot/rkbin to improve the chips stability
- Update documents and tools to make the SDK more better
- Fixes some bugs on buildroot weston10
- Fixes the multivideo hang issue
- Fixes the suspend to resume issues
- Fixes the kmssink/rksimageink plugins on gstreamer
- Fixes the bluthooth on/off during the suspend to resume
- Fixes the pcie-ssd performance with write/read
- Fixes the userdata address in parameter.txt
- Fixes the cheese app on debian
- Fixes the permission with pulseaudio
- Improve the video decode performance with mpp fast mode
- Improve the Audio/Video compatibility
- Upgrade RKNN SDK to v1.3.0
- Upgrade RKAIQ from v3.0x8.7 to v3.0x8.8
- Upgrade Debian version from 11.2 to 11.3
- Reduce the debian rootfs size from 5.5G to 3.2G

## rk3588_linux_beta_v0.1.1_20220421.xml Note

- Support midi and fluidsynth format for gstreamer
- Convert github git:// to https:/ on buildroot
- Support mpp fast-mode property

## rk3588_linux_beta_v0.1.0_20220414.xml Note

```
- The first beta version
```

## rk3588_linux_alpha_v0.0.1_20220115.xml Note

```
- The first alpha version
```
