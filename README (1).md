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
- ❌ `binance_logo.png` (X)
- ✅ `binance.png` 또는 `binance.svg` (O)

### 3. 다른 형식 사용 시 HTML 수정

만약 PNG 파일을 사용하고 싶다면, `index.html` 파일에서 확장자를 변경하세요:

**변경 전:**
```html
<img src="logos/binance.svg" alt="Binance" class="exchange-logo">
```

**변경 후:**
```html
<img src="logos/binance.png" alt="Binance" class="exchange-logo">
```

## 📊 거래소 비교 테이블 데이터 수정

`index.html` 파일에서 테이블 데이터를 수정할 수 있습니다 (대략 490-580번째 줄):

```html
<tr>
    <td>
        <div class="exchange-info">
            <img src="logos/binance.svg" alt="Binance" class="exchange-info-logo">
            <span class="exchange-info-name">Binance</span>
        </div>
    </td>
    <td><span class="rate-value">45%</span></td>        <!-- 페이백율 -->
    <td><span class="rate-value">10%</span></td>        <!-- 거래할인율 -->
    <td>0.018%</td>                                       <!-- 지정가 -->
    <td>0.036%</td>                                       <!-- 시장가 -->
    <td><span class="average-value">$156</span></td>    <!-- 1인당 평균페이백 -->
</tr>
```

각 거래소별 수치를 실제 데이터로 변경하세요.

## 🔧 레퍼럴 링크 수정

`index.html` 파일에서 레퍼럴 링크를 수정하세요:

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

`YOUR_REF_CODE`를 실제 레퍼럴 코드로 변경하세요.

## 📧 이메일 주소 수정

`index.html` 파일에서 이메일 주소를 수정하세요:

```javascript
const mailtoLink = `mailto:your-email@example.com?subject=${subject}&body=${body}`;
```

`your-email@example.com`을 실제 이메일 주소로 변경하세요.

## 🚀 GitHub Pages 배포 방법

1. GitHub 계정 생성 및 로그인
2. 새 Repository 생성 (public으로 설정)
3. 모든 파일 업로드 (index.html, logo.svg, logos 폴더 전체)
4. Settings → Pages → Source를 main 브랜치로 설정
5. 완료! URL로 접속 가능

## ⚙️ 네트워크 옵션 수정

`index.html` 파일에서 네트워크 옵션을 수정하세요:

```html
<select id="network" required>
    <option value="">선택해주세요</option>
    <option value="ERC20">ERC20</option>
    <option value="TRON">TRON</option>
    <option value="SOLANA">SOLANA</option>
    <!-- 원하는 네트워크 추가 -->
</select>
```

## 💡 팁

- 거래소 공식 웹사이트에서 로고를 다운로드하세요
- 투명 배경 PNG나 SVG 형식이 가장 깔끔합니다
- 로고 크기는 자동으로 조정됩니다 (카드: 80x80px, 테이블: 40x40px)
- 테이블의 수치는 실제 페이백율로 업데이트하세요
