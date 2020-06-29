#For installing zram-config package
sudo apt install zram-config
sudo nano /etc/fstab 
and add a # in front of the swap disk if you have one and then reboot
After booting cat /proc/swaps to check if zram is enabled or not

2. To avoid huge metalava compilation times, compile the api-stubs-docs and other packages manually first then continue with mka bacon etc

For example this is what I'm using now in aosip:
. build/envsetup.sh && lunch aosip_wayne-userdebug && mka api-stubs-docs && mka hiddenapi-lists-docs && mka system-api-stubs-docs && mka test-api-stubs-docs && mka kronic

Each of those api-stubs-docs, hiddenapi-lists-docs etc took around 4-7 mins
Increasing of heap from soong directory or other env exports are not required

Total combined build time in my system (Ryzen 1600 with a 8gb ddr4 stick) is around 2hrs now compared to 5hrs previously

For errors while building metalava check #metalava
