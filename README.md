# kdumper
Dumps iBoot and is based on kdumper. This might be useful for De Rebus Antiquis for making the nettoyeur. Couldn't get to execute it on an iOS device, if anyone knows how, let me know. iOS 6.0-7.1.2 only.

Removed functions that XCode didn't want and was able to compile this. You need to have a /dump file for the dumped iBoot and /start file and time set to Jan 1 1970 00:00-00:15 in Settings to get through the failsafe checks. Don't know if it's supposed to be executed through SSH or by LaunchDaemons.

kloader and ios-kexec-utils by [@winocm](https://github.com/winocm)

kdumper by [@xerub](https://github.com/xerub/ios-kexec-utils/)

# How to compile
