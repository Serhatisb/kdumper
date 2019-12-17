# kdumper
Dumps iBoot and is based on kdumper. This might be useful for De Rebus Antiquis for making the nettoyeur. Couldn't get to execute it on an iOS device, if anyone knows how, let me know. Compiled with help from [@xerub](twitter.com/xerub) iOS 6.0-7.1.2 only.

Removed functions that XCode didn't want and was able to compile this. You need to have a /dump file for the dumped iBoot and /start file and time set to Jan 1 1970 00:00-00:15 in Settings to get through the failsafe checks. Don't know if it's supposed to be executed through SSH or by LaunchDaemons.

kloader and ios-kexec-utils by [@winocm](https://github.com/winocm)

kdumper by [@xerub](https://github.com/xerub/ios-kexec-utils/)

# How to compile
`xcrun -sdk iphoneos clang kdumper.c -arch armv7 -framework IOKit -framework CoreFoundation -no-integrated-as -DINLINE_IT_ALL=1 -o kloader -miphoneos-version-min=6.0`

`ldid -Stfp0.plist kdumper`

Compiled using XCode 5.1.1 with iPhoneOS6.1.sdk
