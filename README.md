Building/Flashing Instructions
------------------------------

Make the directory

    mkdir android
    cd android

To initialize and sync sources

    repo init -u git://github.com/AOSP-Minimal/platform_manifest.git -b master
    repo sync

To lunch a device (example hammerhead/Nexus 5)

    . build/envsetup.sh
    lunch aosp_hammerhead-user

To build the images

    make -j# (Replace # with the number of threads you want to use)

The build images for the device will be present in out/target/product/<device-codename>

Replace the device-codename with codename of device, example hammerhead for Nexus 5

Get system.img, userdata.img and boot.img from there.

To flash the images, connect your device in fastboot mode

    fastboot flash boot boot.img
    fastboot flash userdata userdata.img
    fastboot flash system system.img
