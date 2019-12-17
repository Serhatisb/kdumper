# kdumper
Dumps iBoot and is based on kdumper. This might be useful for De Rebus Antiquis with making the nettoyeur. Got it to execute on iPhone3,1/11D257 (iPhone 4 7.1.2) Compiled with help from [@xerub](twitter.com/xerub) iOS 6.0-7.1.2 only.

kloader and ios-kexec-utils by [@winocm](https://github.com/winocm)

kdumper by [@xerub](https://github.com/xerub/ios-kexec-utils/)

# How to execute

A jailbroken device with tfp0 is required to execute this. 

You need to have an empty /dump file for the dumped iBoot and an empty /start file both on root and time set to Jan 1 1970 00:00-00:15 in Settings to get through the failsafe checks. The failsafe checks are there to prevent bootlooping.

You need to execute kdumper as soon as you can SSH when the device boots up.

Then you need to type `kdumper /dump` (if kdumper is in /usr/bin with 777)

It may not dump the iBoot first time with Segmentation fault: 11 so try executing again.

The dump of iPhone3,1/11D257 is on the source code.

# How to compile
`xcrun -sdk iphoneos clang kdumper.c -arch armv7 -framework IOKit -framework CoreFoundation -no-integrated-as -DINLINE_IT_ALL=1 -o kloader -miphoneos-version-min=6.0`

`ldid -Stfp0.plist kdumper`

Compiled using XCode 5.1.1 on OS X 10.7 with iPhoneOS6.1.sdk
