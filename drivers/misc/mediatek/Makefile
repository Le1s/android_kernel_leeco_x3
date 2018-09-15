
MTK_PLATFORM := $(subst ",,$(CONFIG_MTK_PLATFORM))
ARCH_MTK_PROJECT := $(subst ",,$(CONFIG_ARCH_MTK_PROJECT))

MTK_CUSTOM_PATH  := $(srctree)/drivers/misc/mediatek

# For arm64, no mach-xxx folder
MTK_PLATFORM_PATH_ROOT := $(srctree)/drivers/misc/mediatek/mach/$(MTK_PLATFORM)
MTK_PROJECT_PATH_ROOT := $(srctree)/drivers/misc/mediatek/mach/$(MTK_PLATFORM)/$(ARCH_MTK_PROJECT)

ccflags-y += -I$(MTK_PLATFORM_PATH_ROOT)/include \
			 -I$(MTK_PLATFORM_PATH_ROOT)/include/mach \
			 -I$(MTK_PROJECT_PATH_ROOT)/accdet \
			 -I$(MTK_PROJECT_PATH_ROOT)/core \
			 -I$(MTK_PROJECT_PATH_ROOT)/camera/camera \
			 -I$(MTK_PROJECT_PATH_ROOT)/common \
			 -I$(MTK_PROJECT_PATH_ROOT)/dct/dct \
			 -I$(MTK_PROJECT_PATH_ROOT)/hdmi \
			 -I$(MTK_PROJECT_PATH_ROOT)/imgsensor/inc \
			 -I$(MTK_PROJECT_PATH_ROOT)/keypad \
			 -I$(MTK_PROJECT_PATH_ROOT)/leds/mt65xx \
			 -I$(MTK_PROJECT_PATH_ROOT)/power \
			 -I$(MTK_PROJECT_PATH_ROOT)/rtc \
			 -I$(MTK_PROJECT_PATH_ROOT)/sound/inc \
			 -I$(MTK_PROJECT_PATH_ROOT)/touchpanel/ft5406_82 \
			 -I$(MTK_PROJECT_PATH_ROOT)/vibrator \
			 -I$(MTK_PROJECT_PATH_ROOT)/nand \
			 -I$(DRVGEN_OUT)/inc

ccflags-y += -I$(MTK_CUSTOM_PATH)/accdet/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/accelerometer/inc \
			 -I$(MTK_CUSTOM_PATH)/alsps/inc \
			 -I$(MTK_CUSTOM_PATH)/hdmi/inc \
			 -I$(MTK_CUSTOM_PATH)/barometer/inc \
			 -I$(MTK_CUSTOM_PATH)/auxadc/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/cam_cal/inc \
			 -I$(MTK_CUSTOM_PATH)/camera/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/m4u/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/devinfo/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/dual_ccci/$(MTK_PLATFORM)/include \
			 -I$(MTK_CUSTOM_PATH)/dual_ccci/include \
			 -I$(MTK_CUSTOM_PATH)/flashlight/inc \
			 -I$(MTK_CUSTOM_PATH)/gyroscope/inc \
			 -I$(MTK_CUSTOM_PATH)/step_counter \
			 -I$(MTK_CUSTOM_PATH)/pedometer \
			 -I$(MTK_CUSTOM_PATH)/activity_sensor \
			 -I$(MTK_CUSTOM_PATH)/in_pocket_sensor \
			 -I$(MTK_CUSTOM_PATH)/face_down_sensor \
			 -I$(MTK_CUSTOM_PATH)/pick_up_sensor \
			 -I$(MTK_CUSTOM_PATH)/shake_sensor \
			 -I$(MTK_CUSTOM_PATH)/heart_rate_sensor \
			 -I$(MTK_CUSTOM_PATH)/gravity \
			 -I$(MTK_CUSTOM_PATH)/rotationvector \
			 -I$(MTK_CUSTOM_PATH)/linearacceleration \
			 -I$(MTK_CUSTOM_PATH)/gamerotationvector \
			 -I$(MTK_CUSTOM_PATH)/geomagneticrotationvector \
			 -I$(MTK_CUSTOM_PATH)/tilt_detector_sensor \
			 -I$(MTK_CUSTOM_PATH)/wake_gesture_sensor \
			 -I$(MTK_CUSTOM_PATH)/glance_gesture_sensor \
			 -I$(MTK_CUSTOM_PATH)/bringtosee \
			 -I$(MTK_CUSTOM_PATH)/i2c/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/imgsensor/inc \
			 -I$(MTK_CUSTOM_PATH)/eeprom/inc \
			 -I$(MTK_CUSTOM_PATH)/leds/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/lens/inc \
			 -I$(MTK_CUSTOM_PATH)/magnetometer/inc \
			 -I$(MTK_CUSTOM_PATH)/met/platform/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/met/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/sensorHub/inc \
			 -I$(MTK_CUSTOM_PATH)/smi/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/ssw/inc \
			 -I$(MTK_CUSTOM_PATH)/sync \
			 -I$(MTK_CUSTOM_PATH)/uart/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/vibrator/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/video/include \
			 -I$(MTK_CUSTOM_PATH)/video/common \
			 -I$(MTK_CUSTOM_PATH)/video/$(MTK_PLATFORM)/dispsys \
			 -I$(MTK_CUSTOM_PATH)/video/$(MTK_PLATFORM)/videox \
			 -I$(MTK_CUSTOM_PATH)/wdk \
			 -I$(MTK_CUSTOM_PATH)/mjc/v1.0 \
			 -I$(MTK_CUSTOM_PATH)/lcm \
			 -I$(MTK_CUSTOM_PATH)/lcm/inc \
			 -I$(MTK_CUSTOM_PATH)/rrc/v1.0 \
			 -I$(MTK_CUSTOM_PATH)/multibridge/$(MTK_PLATFORM)/mt8193/inc \
			 -I$(MTK_CUSTOM_PATH)/dum-char/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/freqhopping \
			 -I$(MTK_CUSTOM_PATH)/freqhopping/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/btcvsd/inc/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/cmdq/v2 \
			 -I$(MTK_CUSTOM_PATH)/cmdq/v2/$(MTK_PLATFORM) \
			 -I$(MTK_CUSTOM_PATH)/lens/mt6795/inc

CUSTOM_KERNEL_FLAGS := $(addprefix -D, $(shell echo \
			 $(CONFIG_CUSTOM_KERNEL_FLASHLIGHT) \
			 $(CONFIG_CUSTOM_KERNEL_LCM) \
			 $(CONFIG_CUSTOM_KERNEL_IMGSENSOR) | tr a-z A-Z))
ccflags-y += $(CUSTOM_KERNEL_FLAGS)

# Add for ptgen
ccflags-y += -I$(objtree)/PTGEN/inc

ccflags-y += -I$(srctree)/drivers/misc/mediatek/ptgen/$(MTK_PLATFORM)

# Add for Sensor Hub
ccflags-$(CONFIG_MTK_SCP_SENSORHUB) += -DCUSTOM_KERNEL_SENSORHUB

obj-y	+= hallsensor/

obj-$(CONFIG_MTK_FINGERPRINT)	+= fingerprint/

# For MT6795 FPGA bring-up
ifeq ($(CONFIG_ARM64), y)
# For arm64
ifneq ($(CONFIG_MTK_GIC),y)
obj-y	+= irq/
endif

obj-$(CONFIG_MTK_SYSTRACKER)	+= systracker/

obj-$(CONFIG_MTK_LASTPC)		+= lastpc/
#obj-$(CONFIG_MTK_NFC) += nfc/
obj-$(CONFIG_ZRAM)	+= mlog/
obj-$(CONFIG_MTK_ETM)	+= etm/

obj-y	+= lcm/
obj-y	+= mach/

obj-y	+= aee/
obj-y	+= ram_console/
obj-$(CONFIG_MEDIATEK_SOLUTION)	+= sched/
obj-y	+= videocodec/

obj-$(CONFIG_MTK_BOOT)	+= boot/
obj-$(CONFIG_MTK_BOOT_REASON)	+= boot_reason/
obj-$(CONFIG_MTK_CHIP)	+= chip/
obj-y	+= devinfo/
obj-y	+= devapc/
obj-y	+= eint/
obj-y	+= gpio/
obj-y	+= pmic_wrap/
obj-$(CONFIG_SECURITY_SELINUX)	+= selinux_warning/
obj-$(CONFIG_MTK_AEE_MRDUMP)	+= mrdump/
obj-$(CONFIG_MTK_MEM)	+= mem/
obj-y	+= kernel/

obj-y	+= xlog/
obj-y	+= atf_log/
obj-y	+= mmp/
obj-y	+= m4u/
obj-y	+= flashlight/src/
obj-$(CONFIG_MTK_LENS)	+= lens/

obj-y	+= jpeg/
obj-y	+= rrc/


obj-y	+= imgsensor/src/
ifeq ($(wildcard $(srctree)/drivers/misc/mediatek/mach/$(MTK_PLATFORM)/$(ARCH_MTK_PROJECT)/cam_cal),)
obj-$(CONFIG_MTK_CAM_CAL)	+= cam_cal/src/
endif

obj-y += mtprof/
obj-$(CONFIG_MTK_SPM)	+= spm/

obj-y	+= cmdq/
obj-$(CONFIG_MTK_CIRQ) += cirq/
obj-y	+= watchpoint/

obj-y	+= fmradio/
obj-y	+= gps/
subdir-ccflags-y += -I$(srctree)/drivers/misc/mediatek/mach/$(MTK_PLATFORM)/include
obj-$(CONFIG_MTK_COMBO)	+= connectivity/
obj-$(CONFIG_MTK_CONN_MD)	+= conn_md/
obj-y	+= mach/

obj-y	+=  ccci_util/
obj-$(CONFIG_MTK_ECCCI_DRIVER) +=  eccci/

obj-y	+= aee/
obj-y	+= sched/

obj-$(CONFIG_MTK_BOOT)	+= boot/
obj-$(CONFIG_MTK_BOOT_REASON)	+= boot_reason/
obj-$(CONFIG_MTK_CHIP)	+= chip/
obj-y	+= devinfo/

obj-y	+= cqdma/
#obj-y	+= eint/
obj-$(CONFIG_TRUSTONIC_TEE_SUPPORT) += gud/
obj-$(CONFIG_TRUSTONIC_TEE_SUPPORT) += secmem/
obj-$(CONFIG_MTK_MJC_DRIVER)	+= mjc/


obj-$(CONFIG_MTK_SERIAL)	+= uart/
obj-$(CONFIG_MTK_MMC)	+= mmc-host/

obj-y	+= m4u/

obj-y	+= mmp/
obj-y	+= cmdq/
ifeq ($(CONFIG_MTK_SENSOR_SUPPORT),y)
obj-$(CONFIG_MTK_HWMON) += hwmon/
obj-$(CONFIG_MTK_NXP_TFA9897)	+= smartpa/
obj-$(CONFIG_CUSTOM_KERNEL_ALSPS) += alsps/
obj-$(CONFIG_CUSTOM_KERNEL_ACCELEROMETER) += accelerometer/
obj-$(CONFIG_CUSTOM_KERNEL_MAGNETOMETER) += magnetometer/
endif

obj-$(CONFIG_MTK_XHCI)	+=  xhci/

obj-$(CONFIG_MTK_SYNC)	+= sync/
obj-$(CONFIG_MTK_FB) += video/
obj-y	+= mtprof/
obj-y	+= rtc/
obj-y	+= keypad/
obj-y	+= wdk/
obj-y	+= wdt/
#backlight
obj-y	+= leds/
obj-y	+= vibrator/
obj-y	+= power/
obj-$(CONFIG_MTK_POWER_GS)	+= power_gs/

obj-y	+= accdet/

ifeq ($(CONFIG_MTK_HDMI_SUPPORT),y)
obj-y	+= hdmi/
obj-y	+= ext_disp/
endif

obj-$(CONFIG_MTK_HIBERNATION) += hibcore/

obj-y	+= i2c/
obj-$(CONFIG_MTK_PWM)	+= pwm/
obj-$(CONFIG_MTK_AUXADC)	+= auxadc/
obj-y	+= spi/
obj-$(CONFIG_THERMAL)	+= thermal/

obj-$(CONFIG_MTK_MMC)	+= partition/

obj-$(CONFIG_MTK_SYSENV) += sysenv/

obj-y	+= smi/
# USB need to after gpio
obj-$(CONFIG_USB_MTK_HDRC)	  += usb20/
obj-$(CONFIG_USB_MU3D_DRV)	  += mu3d/
obj-$(CONFIG_USB_MU3D_DRV)	  += mu3phy/

obj-$(CONFIG_MTK_TEST_XHCI)	+=  xhci_test/

obj-$(CONFIG_MTK_USBFSH)  += usb11/

obj-$(CONFIG_MTK_VCOREFS)	+= vcorefs/
obj-y	+= freqhopping/

# MT_STOREAGE_LOGGER
obj-$(CONFIG_MTK_MT_LOGGER) += mt_logger/

obj-y	+= gpu/
obj-y	+= emi_mpu/
obj-y	+= emi_bwl/
obj-$(CONFIG_MD32_SUPPORT)	+= md32/

obj-$(CONFIG_MTK_SECURITY_SW_SUPPORT) +=masp/
obj-$(CONFIG_MTK_USB2JTAG_SUPPORT) += usb2jtag/

endif		# end of CONFIG_ARM64

obj-$(CONFIG_MTK_MULTIBRIDGE_SUPPORT) += multibridge/

#widevine drm
#Classic DRM
#$(info "CONFIG_TRUSTONIC_TEE_SUPPORT = $(CONFIG_TRUSTONIC_TEE_SUPPORT)")
obj-$(CONFIG_TRUSTONIC_TEE_SUPPORT) += gcpu/
obj-$(CONFIG_TRUSTONIC_TEE_SUPPORT) += secwidevine/
