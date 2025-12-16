# HomeBug 🐛

AI 기반 해충 인식 및 방제 정보 제공 Android 앱

![Android](https://img.shields.io/badge/Android-26+-green.svg)
![Kotlin](https://img.shields.io/badge/Kotlin-1.9.22-blue.svg)
![Gradle](https://img.shields.io/badge/Gradle-8.7-blue.svg)
![License](https://img.shields.io/badge/License-Educational-yellow.svg)

## 📱 주요 기능

### 🤖 AI 해충 인식
- **TensorFlow Lite** 기반 실시간 해충 분류
- **50종 해충** 자동 인식
- **CameraX** 활용 고품질 카메라 촬영
- 신뢰도 표시 및 결과 분석

### 📚 해충 백과사전
- 50종 해충의 상세 정보
- 크기, 서식지, 위험도 정보
- 카테고리별 분류 및 검색
- 실제 해충 사진 제공

### 🛡️ 검열 모드
- 혐오스러운 이미지 보호 기능
- 흑백 + 흐림 + 밝기 효과
- 원클릭 토글 기능

### 📍 방제업체 찾기
- 위치 기반 업체 검색
- Google Maps 연동
- 업체 정보 및 연락처 제공

### 📊 최근 검색 기록
- 최근 조회한 해충 3개 저장
- SharedPreferences 활용
- 메인 화면 빠른 접근

## 🛠️ 기술 스택

### Core
- **언어**: Kotlin 1.9.22
- **최소 SDK**: 26 (Android 8.0)
- **타겟 SDK**: 33 (Android 13)
- **컴파일 SDK**: 33
- **Gradle**: 8.7
- **AGP**: 8.3.2

### 주요 라이브러리

#### UI/UX
```gradle
// Material Design
com.google.android.material:material:1.9.0

// RecyclerView & CardView
androidx.recyclerview:recyclerview:1.3.1
androidx.cardview:cardview:1.0.0

// ConstraintLayout
androidx.constraintlayout:constraintlayout:2.1.4
```

#### Camera & AI
```gradle
// CameraX
androidx.camera:camera-camera2:1.2.3
androidx.camera:camera-lifecycle:1.2.3
androidx.camera:camera-view:1.2.3

// TensorFlow Lite
org.tensorflow:tensorflow-lite:2.14.0
org.tensorflow:tensorflow-lite-support:0.4.4
org.tensorflow:tensorflow-lite-gpu:2.14.0
```

#### Location & Maps
```gradle
// Google Maps & Location
com.google.android.gms:play-services-maps:18.2.0
com.google.android.gms:play-services-location:21.0.1
```

#### Image Loading
```gradle
// Glide
com.github.bumptech.glide:glide:4.15.1
```

#### Async & Lifecycle
```gradle
// Coroutines
org.jetbrains.kotlinx:kotlinx-coroutines-android:1.7.3

// Lifecycle
androidx.lifecycle:lifecycle-runtime-ktx:2.6.1
```

## 📁 프로젝트 구조

```
HomeBug/
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── java/com/homebug/app/
│   │       │   ├── MainActivity.kt                 (메인 화면)
│   │       │   ├── CameraActivity.kt               (AI 카메라)
│   │       │   ├── PestDetailActivity.kt           (상세 정보)
│   │       │   ├── PestEncyclopediaActivity.kt     (백과사전)
│   │       │   ├── FindServiceActivity.kt          (업체 찾기)
│   │       │   ├── PestControlGuideActivity.kt     (방제 가이드)
│   │       │   ├── SettingsActivity.kt             (설정)
│   │       │   ├── Pest.kt                         (데이터 모델)
│   │       │   ├── PestAdapter.kt                  (어댑터)
│   │       │   └── PestControlCompany.kt           (업체 정보)
│   │       ├── res/
│   │       │   ├── layout/          (8개 레이아웃 XML)
│   │       │   ├── drawable/        (50+ 해충 이미지)
│   │       │   ├── values/          (colors, strings, themes)
│   │       │   └── mipmap-*/        (앱 아이콘)
│   │       ├── assets/
│   │       │   ├── pest_50_mobilenet.tflite  (AI 모델)
│   │       │   └── labels.txt                 (라벨 파일)
│   │       └── AndroidManifest.xml
│   ├── build.gradle                 (앱 모듈 빌드 설정)
│   └── proguard-rules.pro          (ProGuard 규칙)
├── gradle/
│   └── wrapper/
│       └── gradle-wrapper.properties
├── build.gradle                     (프로젝트 빌드 설정)
├── settings.gradle                  (프로젝트 설정)
├── gradle.properties                (Gradle 속성)
├── local.properties.template        (SDK 경로 템플릿)
├── .gitignore
└── README.md
```

## 🚀 빌드 및 실행

### 1. 요구사항
- **Android Studio**: Hedgehog (2023.1.1) 이상 권장
- **JDK**: Java 17
- **Android SDK**: API 33
- **Gradle**: 8.7 (자동 다운로드)

### 2. 프로젝트 설정

#### Step 1: 압축 해제
```bash
unzip HomeBug_Complete.zip
cd HomeBug_Project
```

#### Step 2: SDK 경로 설정
```bash
# local.properties 파일 생성 (자동 또는 수동)
# Android Studio가 자동으로 생성하거나,
# local.properties.template를 참고하여 수동 생성

# Windows 예시
sdk.dir=C:\\Users\\YOUR_USERNAME\\AppData\\Local\\Android\\Sdk

# Mac 예시
sdk.dir=/Users/YOUR_USERNAME/Library/Android/sdk

# Linux 예시
sdk.dir=/home/YOUR_USERNAME/Android/Sdk
```

#### Step 3: Android Studio에서 열기
```
1. Android Studio 실행
2. File > Open
3. HomeBug_Project 폴더 선택
4. Gradle Sync 자동 실행 대기 (2-3분)
```

### 3. 빌드 & 실행

#### 에뮬레이터 실행
```
1. AVD Manager에서 에뮬레이터 생성/선택
2. 권장 사양: Pixel 5, API 33
3. Run 버튼 클릭 (▶️)
```

#### 실제 디바이스 연결
```
1. USB 디버깅 활성화
2. 디바이스 연결
3. Run 버튼 클릭
```

#### APK 빌드
```
Build > Build Bundle(s) / APK(s) > Build APK(s)
```

#### Release APK 생성
```bash
./gradlew assembleRelease
# 출력 위치: app/build/outputs/apk/release/
```

## 🔑 필요 권한

```xml
<!-- AndroidManifest.xml -->
<uses-permission android:name="android.permission.CAMERA" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.INTERNET" />
```

## 🤖 AI 모델 정보

### TensorFlow Lite 모델
- **모델 이름**: pest_50_mobilenet.tflite
- **기반 아키텍처**: MobileNet
- **입력 크기**: 224×224 RGB
- **출력**: 50개 클래스 확률 (Softmax)
- **모델 크기**: ~4MB
- **최적화**: 
  - 모든 ABI 지원 (armeabi-v7a, arm64-v8a, x86, x86_64)
  - tflite 파일 압축 방지 설정
  - GPU 가속 지원

### 라벨 파일
- **파일**: labels.txt
- **형식**: 한 줄에 하나의 해충 이름
- **개수**: 50종

### 지원 해충 카테고리
1. 파리목 (8종)
2. 모기목 (4종)
3. 바퀴목 (6종)
4. 개미목 (7종)
5. 거미목 (3종)
6. 딱정벌레목 (5종)
7. 기타 (17종)

## 📱 화면 구성

### 1. 메인 화면 (MainActivity)
- 최근 검색한 해충 3개 표시
- AI 인식 시작 버튼
- 해충 백과사전 이동
- 방제업체 찾기 이동
- 설정 메뉴

### 2. 카메라 화면 (CameraActivity)
- 실시간 카메라 프리뷰
- 사진 촬영 버튼
- AI 분석 중 표시
- 결과 화면 (해충명, 신뢰도)
- 상세 정보 보기 버튼

### 3. 해충 백과사전 (PestEncyclopediaActivity)
- RecyclerView 리스트
- 해충 아이콘 + 이름 표시
- 스크롤 가능한 목록
- 아이템 클릭 → 상세 정보

### 4. 상세 정보 (PestDetailActivity)
- 해충 이미지 (검열 모드)
- 기본 정보 (크기, 서식지, 위험도)
- 특징 및 출몰 장소
- 퇴치 방법
- 검열 모드 토글 버튼
- 방제 가이드 이동
- 업체 찾기 이동

### 5. 업체 찾기 (FindServiceActivity)
- Google Maps 표시
- 현재 위치 기반 검색
- 업체 마커 표시
- 업체 정보 하단 시트
- 전화 연결 기능

### 6. 설정 (SettingsActivity)
- 다크 모드 토글
- 앱 정보
- 버전 정보
- 개발자 정보

## 💾 데이터 저장

### SharedPreferences
```kotlin
// 최근 검색 기록
val prefs = getSharedPreferences("HomeBugPrefs", Context.MODE_PRIVATE)
prefs.edit().putString("recent_pests", "13,10,27").apply()

// 다크 모드 설정
prefs.edit().putBoolean("dark_mode", true).apply()
```

### Assets (정적 리소스)
- AI 모델 파일 (pest_50_mobilenet.tflite)
- 라벨 파일 (labels.txt)

### Drawable (이미지)
- 50개 해충 PNG 이미지
- 아이콘 및 UI 리소스

## 🎨 디자인 시스템

### Material Design 3
- **컬러 팔레트**:
  - Primary: `#4CAF50` (녹색)
  - Danger: `#F44336` (빨간색)
  - Warning: `#FFC107` (노란색)
  - Safe: `#8BC34A` (연두색)

### 다크 모드
- 자동 시스템 테마 감지
- 수동 토글 기능
- 모든 화면 다크 모드 지원

### Typography
- Material Typography 사용
- 한글 폰트 최적화

## 🔧 트러블슈팅

### Gradle Sync 실패
```bash
# 캐시 초기화
File > Invalidate Caches / Restart

# Clean & Rebuild
Build > Clean Project
Build > Rebuild Project
```

### TensorFlow Lite 모델 로드 실패
```kotlin
// assets 폴더 확인
assets/
├── pest_50_mobilenet.tflite  ✓
└── labels.txt                 ✓

// aaptOptions 설정 확인 (build.gradle)
aaptOptions {
    noCompress "tflite"
}
```

### CameraX 초기화 오류
```xml
<!-- AndroidManifest.xml 권한 확인 -->
<uses-permission android:name="android.permission.CAMERA" />
```

### Google Maps 표시 안됨
```
1. API 키 필요 (별도 발급)
2. google-services.json 추가
3. Maps SDK 활성화
```

### 빌드 느림 문제
```properties
# gradle.properties 최적화 설정 확인
org.gradle.caching=true
org.gradle.parallel=true
org.gradle.configureondemand=true
```

## 📊 성능 최적화

### Gradle 빌드 최적화
- 병렬 빌드 활성화
- 빌드 캐시 사용
- On-demand 설정

### TensorFlow Lite 최적화
- GPU 가속 지원
- 멀티 스레드 처리 (4 threads)
- 모든 ABI 지원

### 이미지 로딩 최적화
- Glide 라이브러리 사용
- 이미지 캐싱
- 메모리 관리

## 🐛 알려진 이슈

1. **AI 모델 크기**: ~4MB로 APK 크기 증가
2. **Google Maps API 키**: 별도 발급 필요
3. **위치 권한**: 실제 디바이스에서 테스트 필요
4. **방제업체 데이터**: 샘플 데이터 사용

## 🔮 향후 계획

- [ ] 온라인 해충 데이터베이스 연동
- [ ] 사용자 리뷰 및 평가 시스템
- [ ] 해충 출몰 지도 (커뮤니티)
- [ ] 푸시 알림 (해충 주의보)
- [ ] 다국어 지원 (영어, 일본어)
- [ ] 태블릿 최적화
- [ ] Wear OS 지원

## 📄 라이선스

이 프로젝트는 교육 목적으로 제작되었습니다.

## 👨‍💻 개발자

**신민용** (Android Developer)
- GitHub: [@your-github](https://github.com/your-github)
- Email: your-email@example.com

## 🙏 감사의 말

- **TensorFlow** - AI 모델 프레임워크
- **Google** - CameraX, Maps API
- **Material Design** - UI 디자인 시스템
- **Android Community** - 오픈소스 기여

## 📝 변경 로그

### v1.0.0 (2025-12-16)
- 🎉 초기 릴리즈
- ✅ AI 해충 인식 기능
- ✅ 50종 해충 백과사전
- ✅ 검열 모드
- ✅ 방제업체 찾기
- ✅ 최근 검색 기록
- ✅ 다크 모드

### 동영상
![--ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/a04fc03c-3d30-4884-beb6-6095147851c1)

