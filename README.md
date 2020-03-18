# kdumper
Dumps iBoot and is based on kdumper. This might be useful for De Rebus Antiquis with making the nettoyeur. Got it to execute on iPhone3,2/11D257 (iPhone 4 (2012) 7.1.2) Compiled with help from [@xerub](twitter.com/xerub) and [@dora2_yururi](twitter.com/dora2_yururi) iOS 6.0-7.1.2 only.

kloader and ios-kexec-utils by [@winocm](https://github.com/winocm)

kdumper by [@xerub](https://github.com/xerub/ios-kexec-utils/)

# How to execute

A jailbroken device with tfp0 is required to execute this. 

You need to have an empty /dump file for the dumped iBoot and an empty /start file both on root and time set to Jan 1 1970 00:00-00:15 in Settings to get through the failsafe checks. You also need to put kdumper in /etc/rc.d from the root of your device with chmod 755. kdumper was put on this folder because the untether is executed in the same folder and the failsafe checks are there to prevent bootlooping.

The dump of iPhone3,2/11D257 is on the source code.

kdumper will dump the iBoot from 6.x and 7.x but because iloader isn't compatible with iOS 6.x, De Rebus Antiquis cannot be exploited in that version.

# How to compile
`xcrun -sdk iphoneos clang kdumper.c -arch armv7 -framework IOKit -framework CoreFoundation -no-integrated-as -DINLINE_IT_ALL=1 -o kdumper -miphoneos-version-min=6.0`

`ldid -Stfp0.plist kdumper`

Compiled using XCode 5.1.1 on OS X 10.7 with iPhoneOS6.1.sdk
