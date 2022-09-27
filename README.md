# std_kotlin
필요 기능: bluetooth 송수신, 2차원 좌표 시각화
안드로이드 개발 기본
> .xml - 안드로이드의 UI 구현을 위한 파일(+ 권한 얻기 관련 코드 포함)
> .kt - kotlin 언어로 된 코드(= .xml을 통해 편집된 버튼을 .kt 코드를 통해 수행)
동작 예시: .xml에 블루투스 사용을 위한 권한 코드 추가 -> .kt에서 동작 편집(스캔 등)

android 12 이상 대상앱에서 블루투스 권한 선언
<manifest>
    <!-- Request legacy Bluetooth permissions on older devices. -->
    <uses-permission android:name="android.permission.BLUETOOTH"
                     android:maxSdkVersion="30" />
    <uses-permission android:name="android.permission.BLUETOOTH_ADMIN"
                     android:maxSdkVersion="30" />

    <!-- Needed only if your app looks for Bluetooth devices.
         If your app doesn't use Bluetooth scan results to derive physical
         location information, you can strongly assert that your app
         doesn't derive physical location. -->
    <uses-permission android:name="android.permission.BLUETOOTH_SCAN" />

    <!-- Needed only if your app makes the device discoverable to Bluetooth
         devices. -->
    <uses-permission android:name="android.permission.BLUETOOTH_ADVERTISE" />

    <!-- Needed only if your app communicates with already-paired Bluetooth
         devices. -->
    <uses-permission android:name="android.permission.BLUETOOTH_CONNECT" />

    <!-- Needed only if your app uses Bluetooth scan results to derive physical location. -->
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />

장치 검색 및 블루투스 설정 권한 선언
    <uses-permission android:name="android.permission.BLUETOOTH_ADMIN" />
android 10, 11 백그라운드 위치 액세스
    <uses-permission android:name="android.permission.ACCESS_BACKGROUND_LOCATION" />
BLE가 중요 기능인 경우(해당 기능이 없는 기기의 경우, 앱스토어에서 사용자에게 앱 숨김)
    <uses-feature android:name="android.hardware.bluetooth_le" android:required="true"/>

경로 탐색 알고리즘: a* 알고리즘
    수식: F = G + H 
    F = 현재까지 이동에 걸린 비용과 예상 비용의 총합
    G = 시작점~현재 위치까지의 경로를 따라이동하는데 소요되는 비용
    H = 현재 위치 ~ 목적지까지의 예상 이동 비용(장애물 무시)
    
