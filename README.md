# Apple Music ALAC Downloader
Original script by Sorrow. Modified by me to include some fixes and improvements.

## How to use
1. Create a virtual device on Android Studio with a image that doesn't have Google APIs.
2. Install this version of Apple Music: https://www.apkmirror.com/apk/apple/apple-music/apple-music-3-6-0-beta-release/apple-music-3-6-0-beta-4-android-apk-download/. You will also need SAI to install it: https://f-droid.org/pt_BR/packages/com.aefyr.sai.fdroid/.
3. Launch Apple Music and sign in to your account. Subscription required.
4. Port forward 10020 TCP: `adb forward tcp:10020 tcp:10020`.
5. Start frida server. `adb push frida-server /data/local/tmp/` and `adb shell` and `su` and `chmod 755 frida-server` and `/data/local/tmp/frida-server &`
6. Start the frida agent: `frida -U -l agent.js -f com.apple.android.music`.
7. Start downloading some albums: `go run main.go https://music.apple.com/us/album/whenever-you-need-somebody-2022-remaster/1624945511`.
8. For dolby atmos: `go run main_atmos.go "https://music.apple.com/hk/album/%E5%91%A8%E6%9D%B0%E5%80%AB%E5%9C%B0%E8%A1%A8%E6%9C%80%E5%BC%B7%E4%B8%96%E7%95%8C%E5%B7%A1%E8%BF%B4%E6%BC%94%E5%94%B1%E6%9C%83/1721464851"`.
