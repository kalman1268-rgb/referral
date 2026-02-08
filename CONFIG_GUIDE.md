# ⚙️ 설정 관리 가이드 (Configuration Guide)

## 📍 설정 파일 위치

모든 주요 설정은 `index.html` 파일 상단의 **JavaScript 설정 섹션**에 집중되어 있습니다.

파일을 열면 맨 아래쪽에 다음과 같은 섹션이 있습니다:

```javascript
// ========================================
// 📝 설정 관리 섹션 (Configuration Management)
// 이 섹션에서 모든 주요 설정을 관리할 수 있습니다
// ========================================
```

---

## 🔗 1. 거래소 레퍼럴 링크 수정

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

**수정 방법:**
- `YOUR_REF_CODE`를 각 거래소의 실제 레퍼럴 코드로 변경
- 전체 URL을 교체 가능

**예시:**
```javascript
binance: 'https://www.binance.com/en/register?ref=ABC123',
```

---

## 📊 2. 거래소 데이터 수정 (페이백율, 수수료 등)

```javascript
const exchangeData = {
    binance: {
        name: 'Binance',
        logo: 'logos/binance.svg',
        description: {
            en: "World's largest cryptocurrency exchange",
            ko: '세계 최대 암호화폐 거래소'
        },
        paybackRate: '45%',      // 페이백율
        discount: '10%',          // 거래할인율
        makerFee: '0.018%',      // 지정가 수수료
        takerFee: '0.036%',      // 시장가 수수료
        avgPayback: '$156'       // 평균 페이백
    },
    // ... 다른 거래소들
};
```

### 수정 가능한 항목:

| 항목 | 설명 | 예시 |
|------|------|------|
| `name` | 거래소 이름 | `'Binance'` |
| `logo` | 로고 파일 경로 | `'logos/binance.svg'` 또는 `'logos/binance.png'` |
| `description.en` | 영문 설명 | `"World's largest exchange"` |
| `description.ko` | 한글 설명 | `'세계 최대 거래소'` |
| `paybackRate` | 페이백율 | `'45%'` → `'50%'` |
| `discount` | 거래할인율 | `'10%'` → `'15%'` |
| `makerFee` | 지정가 수수료 | `'0.018%'` → `'0.020%'` |
| `takerFee` | 시장가 수수료 | `'0.036%'` → `'0.040%'` |
| `avgPayback` | 평균 페이백 금액 | `'$156'` → `'$200'` |

### 📝 수정 예시:

Binance의 페이백율을 50%로, 평균 페이백을 $200으로 변경:

```javascript
binance: {
    name: 'Binance',
    logo: 'logos/binance.svg',
    description: {
        en: "World's largest cryptocurrency exchange",
        ko: '세계 최대 암호화폐 거래소'
    },
    paybackRate: '50%',      // 45% → 50%로 변경
    discount: '10%',
    makerFee: '0.018%',
    takerFee: '0.036%',
    avgPayback: '$200'       // $156 → $200으로 변경
},
```

---

## 🖼️ 3. 거래소 로고 이미지 변경

### 방법 1: 파일 교체 (권장)
1. `logos/` 폴더에서 해당 거래소 로고 파일 교체
2. **파일명을 동일하게 유지** (예: `binance.svg`)
3. 코드 수정 불필요

### 방법 2: 새 파일명 사용
1. 새 로고 파일을 `logos/` 폴더에 추가
2. `exchangeData`에서 경로 수정:

```javascript
binance: {
    logo: 'logos/binance-new.png',  // 새 파일명으로 변경
    // ...
}
```

### 지원 이미지 형식:
- SVG (권장)
- PNG (투명 배경 권장)
- JPG

---

## 🎬 4. 배너 링크 수정

```javascript
const bannerLinks = [
    'https://your-event-page.com/event1',  // 첫 번째 배너
    'https://your-event-page.com/event2',  // 두 번째 배너
    'https://your-event-page.com/event3'   // 세 번째 배너
];
```

**수정 방법:**
각 배너를 클릭했을 때 이동할 URL을 변경

**예시:**
```javascript
const bannerLinks = [
    'https://mysite.com/promotion',
    'https://mysite.com/bonus',
    'https://mysite.com/vip'
];
```

---

## 📧 5. 기타 설정

```javascript
const CONFIG = {
    emailRecipient: 'your-email@example.com',  // 페이백 신청 정보를 받을 이메일
    telegramLink: 'https://t.me/your_telegram', // 텔레그램 링크
    sliderInterval: 5000  // 슬라이더 자동 전환 시간 (밀리초)
};
```

### 수정 항목:

| 항목 | 설명 | 예시 |
|------|------|------|
| `emailRecipient` | 신청 정보 수신 이메일 | `'support@mysite.com'` |
| `telegramLink` | 텔레그램 채널/그룹 주소 | `'https://t.me/cryptomax_support'` |
| `sliderInterval` | 배너 전환 속도 (밀리초) | `5000` (5초), `3000` (3초) |

---

## ➕ 6. 새 거래소 추가하기

### 단계별 가이드:

**1단계: 로고 준비**
- `logos/` 폴더에 로고 파일 추가 (예: `kucoin.svg`)

**2단계: `exchangeData`에 추가**
```javascript
const exchangeData = {
    binance: { /* ... */ },
    bybit: { /* ... */ },
    // ... 기존 거래소들
    
    kucoin: {  // 새 거래소 추가
        name: 'KuCoin',
        logo: 'logos/kucoin.svg',
        description: {
            en: 'People\'s Exchange',
            ko: '사용자 중심 거래소'
        },
        paybackRate: '40%',
        discount: '10%',
        makerFee: '0.020%',
        takerFee: '0.040%',
        avgPayback: '$130'
    }
};
```

**3단계: 레퍼럴 링크 추가**
```javascript
const referralLinks = {
    binance: 'https://...',
    bybit: 'https://...',
    // ... 기존 링크들
    
    kucoin: 'https://www.kucoin.com/r/YOUR_REF'  // 새 링크 추가
};
```

**완료!** 페이지를 새로고침하면 자동으로 표시됩니다.

---

## ❌ 7. 거래소 제거하기

### 방법 1: 완전 제거
`exchangeData`와 `referralLinks`에서 해당 거래소 전체 블록 삭제

### 방법 2: 임시 숨김 (주석 처리)
```javascript
const exchangeData = {
    binance: { /* ... */ },
    // huobi: {  // 임시로 숨김
    //     name: 'Huobi',
    //     ...
    // },
    mexc: { /* ... */ }
};
```

---

## 🎯 빠른 수정 체크리스트

### 🔥 필수 수정 항목:
- [ ] 거래소 레퍼럴 링크 (YOUR_REF_CODE 변경)
- [ ] 이메일 주소 (your-email@example.com 변경)
- [ ] 텔레그램 링크 (your_telegram 변경)

### ✨ 선택 수정 항목:
- [ ] 거래소 페이백율 업데이트
- [ ] 수수료 정보 업데이트
- [ ] 평균 페이백 금액 업데이트
- [ ] 거래소 로고 교체
- [ ] 배너 링크 설정
- [ ] 거래소 추가/제거

---

## 💡 팁

1. **테스트 방법**: 수정 후 브라우저에서 페이지를 새로고침하여 확인
2. **백업**: 수정 전 원본 파일 백업 권장
3. **로고 크기**: 정사각형 이미지 권장 (200x200px 이상)
4. **일괄 수정**: 여러 거래소 동시 수정 시 실수 방지를 위해 한 번에 하나씩 수정 권장

---

## ⚠️ 주의사항

- JavaScript 문법을 정확히 지켜주세요 (따옴표, 콤마, 중괄호 등)
- 각 거래소 블록 끝에 콤마(`,`) 필수 (마지막 항목 제외)
- URL은 반드시 따옴표(`'` 또는 `"`)로 감싸야 함
- 퍼센트(%), 달러($) 기호는 문자열로 포함

---

## 🆘 문제 해결

**문제: 페이지가 비어있거나 오류 발생**
- 브라우저 개발자 도구(F12) → Console 탭에서 오류 확인
- 대부분 문법 오류 (따옴표, 콤마 누락)

**문제: 로고가 표시되지 않음**
- 파일 경로 확인 (`logos/binance.svg`)
- 파일명 대소문자 확인
- 이미지 파일이 실제로 존재하는지 확인

**문제: 변경사항이 반영되지 않음**
- 브라우저 캐시 삭제 (Ctrl+Shift+R 또는 Cmd+Shift+R)
- 파일 저장 확인

---

이 가이드를 따라하시면 쉽게 모든 설정을 관리하실 수 있습니다! 🚀
