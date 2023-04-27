# 💻 맥북 사용에 관한 편리한 정보들을 제공합니다.
- M1 이상 맥북을 더 편리하게 쓰는 팁
- MacOS 필수 앱

<br>

### ✅ MacOS 필수 앱
- Magnet (AppStore/유료) : macOS  창 정렬 앱, 단축키 누르거나 갖다대면 알아서 정렬됨   
(갖다대면 붙는 것이 아래와 차이점입니다.)   
https://apps.apple.com/us/app/magnet/id441258766?mt=12


- Spectacle (설치형/무료) : macOS 창 정렬 앱, 단축키 누르면 정렬할 수 있음   
https://www.spectacleapp.com


- Keyboard Clean Tool(설치형/무료): 키보드 닦을때 입력 막아주는 앱   
https://folivora.ai/keyboardcleantool


### ✅ MacOS 선택 앱
- CoconutBattert (설치형/무료): 배터리 용량 확인   
https://www.coconut-flavour.com/coconutbattery/

- iMazing (설치형/부분유료):  ipa 추출 등, iPhone의 Deep한 관리   
https://imazing.com/ko?gad=1&gclid=CjwKCAjwuqiiBhBtEiwATgvixGQ7RLOBDLcpcJzV0n-4dw8zzguE7fic12C7YEhvDKdVFPPX0jev2BoC5JsQAvD_BwE


### 📲 개발자 추천 앱   
- DeepWork (AppStore/무료): 집중시간 상단 작업표시줄에 나오고, 기록할 수 있음
https://apps.apple.com/kr/app/%EB%94%A5%EC%9B%8C%ED%81%AC-%EC%A7%81%EA%B4%80%EC%A0%81%EC%9D%B8-%EB%AA%B0%EC%9E%85-%EB%8F%84%EA%B5%AC-deepwork/id1464410783


- jandi (AppStore/무료): Github 커밋잔디를 현황을 볼수 있음   
https://apps.apple.com/kr/app/jandi-%EA%B9%83%ED%97%99-%EC%9E%94%EB%94%94%EB%A5%BC-%EC%83%81%ED%83%9C%EB%B0%94%EC%97%90%EC%84%9C-%EC%86%90%EC%89%BD%EA%B2%8C-%EB%B3%B4%EC%9E%90/id1551460285?mt=12


- iTerm2: 터미널과 동일하지만 터미널 대비 더 세부적인 옵션들이 많음 (보통 oh my zsh와 함께 사용)   
https://iterm2.com


### ✅ 일반 FHD모니터가 맥북 연결시 선명하지 않다면(HIDPI)
---

#### **Better Display**
`일반 FHD모니터에서 1080p HIDPI 지원 / dmg설치 / 부분유료`   
🔗 https://github.com/waydabber/BetterDisplay


<br>

### ✅ macOS Bootable Disk / 부팅 디스크 만들기
---

1. dmg파일을 탑재 후 ₩macOS Ventura 설치.app`파일을 응용프로그램 디렉토리에 넣거나 (경로: `/Applications`)   
앱스토어에서 다운로드 후 USB 또는 외장 SSD에 아래와 같은 파티션을 만들거나 지우기로 만들어 줍니다.   
 (현재 MacOS확장 포맷을 사용하는 경우 파티션만 만들어도되고, MacOS확장이 안나온다면 외장SSD 디스크를 포맷해야합니다)   
2. 디스크 유틸리티를 실행해서 MacOS확장, GUID 포맷, 이름은 MyVolume라는 파티션을 만들어줍니다.

3. 터미널을 열고 `sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume` 을 만들어줍니다.

기타 OS의 경우 애플 공식링크를 참고하세요
https://support.apple.com/en-us/HT201372


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
