source code for rtl8822bu on rockchip platform

original readme.txt from rk patch (6-6-2018)

----

# config配置

CONFIG_WIFI_LOAD_DRIVER_WHEN_KERNEL_BOOTUP = y

CONFIG_RTL88x2BU = y

dts 配置：wifi_chip_type = "rtl88x2bu";


        wireless-wlan {
                compatible = "wlan-platdata";

                wifi_chip_type = "rtl88x2bu";
                WIFI,poweren_gpio = <&gpio2 GPIO_D2 GPIO_ACTIVE_HIGH>;

                status = "okay";
        };

# 驱动目录 

kernel\drivers\net\wireless\rockchip_wlan\rtl88x2bu


# patch

patch -p1 < add_config_for_rtl88x2bu.patch 添加编译选项，如果pach 不上，按照补丁手动打补丁即可

# Comment

说明，WIFI驱动build in到内核中，开机后自动加载WIFI驱动
