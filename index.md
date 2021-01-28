
# 가이드

> 현재 가이드 문서가 제작 중에 있습니다. LG 폴더의 앱 설치와 같은 커스터마이징 정보는 [블로그](https://garubanana.tistory.com/35)를 참조하여 주시기 바랍니다.

현재 **자주 하는 질문** 에 대한 페이지가 만들어져 있습니다. 자주 발생하는 문제들에 대한 답변들이 올라와 있으니 참고 바랍니다.

[자주 하는 질문 >](http://yvelta1.github.io/qna)

## 시작하기 전에
**이 가이드에서는 LG 폴더 시리즈에 대한 앱 설치, 숨겨진 기능들 사용에 대한 방법을 다루고 있습니다.**

기본적인 안드로이드에 대한 지식과 adb에 대한 사용 방법을 숙지하고 있어야 합니다. 자세한 내용은 구글링하여 참고하세요.

지원하는 기기는 아래와 같습니다.
 - LG 폴더
 - LG 폴더 2
 - LG 폴더 2S

또한, 이 방법들은 시스템 부분을 건드리는 작업이 없기에, 공장 초기화로 이 과정에서 일어나는 대부분의 문제들을 해결할 수 있습니다.

## 준비
LG 폴더를 건드리기 전, PC에서 설치 및 설정해주어야 하는 몇 가지들이 있습니다.

**ADB.zip** : [이곳](adb.zip)에서 다운로드 받은 후, C드라이브 최상단에 adb라는 이름의 폴더로 이동시켜주세요.

**LG USB 드라이버** : [이곳](https://softfamous.com/lg-mobile-driver/)에서 다운로드 받은 후, 설치하세요.

## 기기 설정 및 PC 연결
우선, 잠금을 해제한 후 다이얼에서 5457#*110(폴더 2는 120, 폴더 2S는 120 or 125)를 입력하는 즉시 아래 화면이 불러와집니다.

![사진](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https://blog.kakaocdn.net/dn/cUbwjW/btquR14cFTe/K4KLPXmvuSaIQEGoYouH91/img.png)

그 후, 맨 아래의 **Developer Options**를 선택 후 3번의 **USB 디버깅**으로 진입합니다. USB 디버깅을 켭니다.

> 가끔 재부팅 시, 혹은 일정 시간이 지나면 USB 디버깅이 꺼지는 경우가 있습니다. 컴퓨터와 adb로 연결하여 앱을 설치하거나 다른 명령을 수행하는 경우, 이 기능은 켜져 있어야 합니다.

![사진](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https://blog.kakaocdn.net/dn/GzGqZ/btquTay721L/TpZLK0neInoK8vXjypzIfK/img.png)

이후, **adb를 적절한 위치에 두었으며, LG USB 드라이버가 설치된** PC와 연결하면 아래와 같은 화면이 뜹니다. **확인**을 눌러주세요. 체크표시는 선택사항입니다.

![사진](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https://blog.kakaocdn.net/dn/bFMrlA/btquSpwJldQ/UK39ffhu9kgW1IusIFsbdk/img.png)

그리고, 위에서 언급한 adb 폴더가 C드라이브 최상단에 있다는 가정 하에 아래 명령어를 명령 프롬프트에서 입력합니다.

    cd c:/adb
    adb devices

![사진](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https://blog.kakaocdn.net/dn/bhDYRD/btquQwKy24n/qpvL19HIKUKh0p7vglbCKk/img.png)
Y110(120 or 125)로 시작하는 기기가 뜨고, devices라고 뜨면 정상적으로 인식된 것입니다. 아래 과정을 진행해 주세요.

**Unauthorized 혹은 Offline가 나올 경우, 디버깅 화면에서 확인을 누르지 않은 경우이거나, 단순 오류입니다. 재부팅으로 보통 해결됩니다.(PC 재부팅)**

>이 과정을 수행할때는, PC에 기기가 하나만 연결되어 있는 상태에서 진행하시는 것이 가장 안전합니다.

## 앱 설치

APK 변조를 마친 앱을 설치하는 경우에 한정됩니다.
LG 폴더는 기본적으로 LG 기본 설치 앱 외의 서드파티 어플리케이션 설치를 허용하지 않기 때문에, 이를 속이는 작업이 필요합니다. 자세한 내용과 방법은 [이 게시물](https://garubanana.tistory.com/46)을 참고하세요.

**C드라이브 최상단에 있는 ADB 폴더에, 패키지명을 변경시킨 apk 파일을 이동시킵니다.** 그 후, 아래 명령어를 명령 프롬프트에 입력 해 주세요.

    adb -d install -r (파일 이름.apk)
파일 크기에 따라 시간이 걸릴 수 있으며, Success가 나오면 성공입니다. 다른 에러가 나오며 설치되지 않는 경우에는, [자주 하는 질문](http://yvelta1.github.io/qna) 을 참고하세요.

앱 제거는, 위의 서비스메뉴에서 **Installed Application List** 에 들어가신 후, 제거할 앱을 선택한 후 Uninstall를 누르시면 됩니다. (Uninstall 버튼이 왼쪽에 있는 경우, 기기의 왼쪽 ㅡ 버튼을, 반대인 경우 그 반대로)


## 숨겨진 기능 (예:핫스팟) 사용
