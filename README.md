# 크립토 거래소 레퍼럴 웹사이트

## 📁 파일 구조

```
/
├── index.html          # 메인 웹페이지
├── logo.svg           # 사이트 로고
└── logos/             # 거래소 로고 폴더
    ├── binance.svg
    ├── bybit.svg
    ├── bitget.svg
    ├── okx.svg
    ├── huobi.svg
    └── mexc.svg
```

## ✨ 주요 기능

### 1. 상단 네비게이션 메뉴
- **로고 클릭**: 홈으로 이동
- **서비스 소개**: 서비스 안내
- **페이백 신청**: 신청 페이지로 이동
- **고객상담센터**: 텔레그램 연결

### 2. 슬라이딩 배너 (3개)
- 자동 슬라이드 (5초마다)
- 클릭 시 설정된 링크로 이동
- 하단 점(dot) 클릭으로 수동 전환

### 3. 거래소 카드
- 로고 + 거래소명 + 설명
- 클릭 시 레퍼럴 링크로 이동

### 4. 비교 테이블
- 거래소별 페이백율 비교
- 모바일 반응형 (가로 스크롤)

### 5. 페이백 신청 폼
- 돌아가기 / 제출하기 2개 버튼
- 이메일로 정보 전송

## 🎨 거래소 로고 변경 방법

### 1. 이미지 파일 준비
- PNG, SVG, JPG 등 원하는 이미지 형식 사용 가능
- 권장 크기: 정사각형 (예: 200x200px, 500x500px)
- 배경이 투명한 PNG나 SVG 권장

### 2. 파일 교체
기존 로고 파일을 원하는 이미지로 교체하세요:

```
logos/binance.svg  → 실제 Binance 로고로 교체
logos/bybit.svg    → 실제 Bybit 로고로 교체
logos/bitget.svg   → 실제 Bitget 로고로 교체
logos/okx.svg      → 실제 OKX 로고로 교체
logos/huobi.svg    → 실제 Huobi 로고로 교체
logos/mexc.svg     → 실제 MEXC 로고로 교체
```

**중요:** 파일 이름은 그대로 유지해야 합니다!

## 🎬 슬라이딩 배너 설정

### 배너 링크 변경
`index.html` 파일 상단 JavaScript 부분에서:

```javascript
const bannerLinks = [
    'https://your-event-page.com/event1',  // 첫 번째 배너 클릭 시 이동할 URL
    'https://your-event-page.com/event2',  // 두 번째 배너 클릭 시 이동할 URL
    'https://your-event-page.com/event3'   // 세 번째 배너 클릭 시 이동할 URL
];
```

### 배너 내용 변경
HTML에서 배너 텍스트 수정:

```html
<div class="slider-slide active" onclick="openBannerLink(0)">
    <div class="slider-content">
        <h2>🎉 최대 50% 페이백 이벤트</h2>
        <p>지금 가입하고 특별 혜택을 받으세요!</p>
    </div>
</div>
```

### 배너 이미지 배경 사용하기
배너에 실제 이미지를 사용하려면:

```html
<div class="slider-slide active" onclick="openBannerLink(0)">
    <img src="banners/banner1.jpg" alt="배너1">
    <div class="slider-content">
        <h2>🎉 최대 50% 페이백 이벤트</h2>
        <p>지금 가입하고 특별 혜택을 받으세요!</p>
    </div>
</div>
```

그리고 `banners/` 폴더를 만들어 이미지 파일을 넣으세요.

## 📊 거래소 비교 테이블 데이터 수정

각 거래소 행의 수치 변경:

```html
<tr>
    <td>
        <div class="exchange-info">
            <img src="logos/binance.svg" alt="Binance">
            <span class="exchange-info-name">Binance</span>
        </div>
    </td>
    <td><span class="rate-value">45%</span></td>        ← 페이백율
    <td><span class="rate-value">10%</span></td>        ← 거래할인율
    <td>0.018%</td>                                      ← 지정가
    <td>0.036%</td>                                      ← 시장가
    <td><span class="average-value">$156</span></td>    ← 평균페이백
</tr>
```

## 🔗 텔레그램 링크 설정

헤더 네비게이션에서 텔레그램 링크 수정:

```html
<a class="nav-link" href="https://t.me/your_telegram" target="_blank">고객상담센터</a>
```

`your_telegram`을 실제 텔레그램 주소로 변경하세요.
- 예: `https://t.me/cryptomax_support`

## 🔧 레퍼럴 링크 수정

```javascript
const referralLinks = {
    binance: 'https://www.binance.com/en/register?ref=YOUR_REF_CODE',
    bybit: 'https://www.bybit.com/register?ref=YOUR_REF_CODE',
    bitget: 'https://www.bitget.com/expressly?channelCode=YOUR_REF_CODE',
    okx: 'https://www.okx.com/join/YOUR_REF_CODE',
    huobi: 'https://www.huobi.com/en-us/v/register/double-invite/?inviter_id=YOUR_REF_CODE',
    mexc: 'https://www.mexc.com/register?inviteCode=YOUR_REF_CODE'
};
```

## 📧 이메일 주소 수정

```javascript
const mailtoLink = `mailto:your-email@example.com?subject=${subject}&body=${body}`;
```

## 🚀 GitHub Pages 배포 방법

1. GitHub 계정 생성 및 로그인
2. 새 Repository 생성 (public으로 설정)
3. 모든 파일 업로드
   - index.html
   - logo.svg
   - logos/ 폴더 (모든 거래소 로고 포함)
4. Settings → Pages → Source를 main 브랜치로 설정
5. 완료! `https://[username].github.io/[repository]`로 접속

## ⚙️ 네트워크 옵션 수정

```html
<select id="network" required>
    <option value="">선택해주세요</option>
    <option value="ERC20">ERC20</option>
    <option value="TRON">TRON</option>
    <option value="SOLANA">SOLANA</option>
    <option value="BEP20">BEP20</option>  <!-- 추가 예시 -->
</select>
```

## 💡 팁

- 거래소 공식 웹사이트에서 로고를 다운로드하세요
- 투명 배경 PNG나 SVG가 가장 깔끔합니다
- 슬라이딩 배너는 5초마다 자동 전환됩니다
- 모바일에서는 햄버거 메뉴(☰)로 표시됩니다
- 배너 이미지는 16:9 비율 권장 (예: 1920x1080px)

## 📱 모바일 최적화

- 모든 요소가 자동으로 모바일에 최적화됩니다
- 테이블은 가로 스크롤 지원
- 네비게이션은 햄버거 메뉴로 변경
- 터치 제스처 지원 (슬라이더)

## 🎯 커스터마이징 포인트

1. **색상 변경**: CSS에서 `#4F46E5`, `#7C3AED` 변경
2. **폰트 변경**: CSS의 `font-family` 수정
3. **배너 속도**: JavaScript의 `5000` (5초) 수정
4. **서비스 소개**: `showServiceInfo()` 함수 내용 수정

## 🔒 보안 주의사항

- 이메일 주소는 스팸봇에 노출될 수 있습니다
- 실제 운영 시 백엔드 서버 사용 권장
- 민감한 정보는 암호화하여 전송하세요
