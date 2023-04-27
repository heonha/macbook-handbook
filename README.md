# 💻 맥북 사용에 관한 편리한 정보들을 제공합니다.
- M1 이상 맥북을 더 편리하게 쓰는 팁
- MacOS 필수 앱

<br>

---

### 일반 FHD모니터가 맥북 연결시 선명하지 않다면(HIDPI)
---

<br>

#### **Better Display**
`일반 FHD모니터에서 1080p HIDPI 지원 / dmg설치 / 부분유료`   
🔗 https://github.com/waydabber/BetterDisplay


### macOS Bootable Disk / 부팅 디스크 만들기
---

1. dmg파일을 탑재 후 ₩macOS Ventura 설치.app`파일을 응용프로그램 디렉토리에 넣거나 (경로: `/Applications`)   
앱스토어에서 다운로드 후 USB 또는 외장 SSD에 아래와 같은 파티션을 만들거나 지우기로 만들어 줍니다.   
 (현재 MacOS확장 포맷을 사용하는 경우 파티션만 만들어도되고, MacOS확장이 안나온다면 외장SSD 디스크를 포맷해야합니다)   
2. 디스크 유틸리티를 실행해서 MacOS확장, GUID 포맷, 이름은 MyVolume라는 파티션을 만들어줍니다.

3. 터미널을 열고 `sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume` 을 만들어줍니다.


정상적인 경우
```
~ ❯ sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

Ready to start.
To continue we need to erase the volume at /Volumes/MyVolume.
If you wish to continue type (Y) then press return: Y
Erasing disk: 0%... 10%... 20%... 30%... 100%
Copying essential files...
Copying the macOS RecoveryOS...
Making disk bootable...
Copying to disk: 0%... 10%... 20%... 30%... 40%... 50%... 60%... 70%... 80%... 90%...

``` 

MacOS 저널링 포맷이 아닌경우 아래와 같이 뜹니다.
APFS포맷은 만들수 없으니 macOS확장으로 포맷하면 해결됩니다.
```
~ ❯ sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

Password:
Ready to start.
To continue we need to erase the volume at /Volumes/MyVolume.
If you wish to continue type (Y) then press return: Y
APFS disks may not be used as bootable install media.
An error occurred erasing the disk.
```
설치방법은 제작한 외장 SSD를 꼽고, 디스크 선택화면이 나올때까지 전원버튼을 누르고 있고,
Ventura 설치 디스크를 선택해주시면 됩니다.
