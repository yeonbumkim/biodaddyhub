# BioDaddy Hub - Page Skills & Patterns

각 계산기/도구 페이지에 공통으로 적용하는 재사용 가능한 컴포넌트 패턴.

---

## 1. BioDaddy Hub Header (Sticky Nav)

모든 하위 페이지 상단에 `← BioDaddy Hub` 링크를 sticky nav로 배치.

### Dark Theme (kbank 등 다크 배경 페이지)

```html
<nav style="background:rgba(10,14,26,0.9);border-bottom:1px solid #1e293b;padding:0.6rem 1.5rem;position:sticky;top:0;z-index:100;backdrop-filter:blur(20px);">
  <div style="max-width:1060px;margin:0 auto;display:flex;align-items:center;gap:1rem;">
    <a href="https://farmingdollar.com" style="font-size:0.95rem;font-weight:700;text-decoration:none;color:#e2e8f0;transition:color 0.2s;" onmouseover="this.style.color='#3b82f6'" onmouseout="this.style.color='#e2e8f0'">&#x2190; BioDaddy Hub</a>
  </div>
</nav>
```

### Light Theme (medianincome 등 라이트 카드 페이지)

```css
.bd-nav {
    background: rgba(26, 26, 46, 0.95);
    border-bottom: 1px solid rgba(255,255,255,0.1);
    padding: 0.6rem 1.5rem;
    position: sticky;
    top: 0;
    z-index: 100;
    backdrop-filter: blur(20px);
}
.bd-nav-inner {
    max-width: 800px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    gap: 1rem;
}
.bd-nav a {
    font-size: 0.95rem;
    font-weight: 700;
    text-decoration: none;
    color: #e2e8f0;
    transition: color 0.2s;
}
.bd-nav a:hover { color: #e94560; }
```

```html
<nav class="bd-nav">
  <div class="bd-nav-inner">
    <a href="https://farmingdollar.com">&#x2190; BioDaddy Hub</a>
  </div>
</nav>
```

**규칙**: hover 색상은 해당 페이지의 accent 색상과 맞출 것 (kbank → `#3b82f6`, medianincome → `#e94560`)

---

## 2. Disclaimer (면책 조항)

모든 계산기 페이지 하단에 면책 조항을 포함. 내용은 도메인에 맞게 커스터마이즈.

### 투자/IPO 계산기용 (kbank 등)

```html
<div class="disclaimer">
  <div class="container">
    <p><strong>면책 조항 (Disclaimer)</strong></p>
    <ul class="disclaimer-list">
      <li>본 계산기는 <strong>단순 참고용</strong>이며, 투자 권유·추천·자문이 아닙니다.</li>
      <li>계산 결과에는 <strong>오류가 포함될 수 있으며</strong>, 실제 배정 주식수·공모가·수수료·세금 등은 반드시 해당 증권사 및 공식 공시자료를 통해 직접 확인하시기 바랍니다.</li>
      <li>본 페이지에 기재된 수치·비율·시나리오는 과거 데이터 및 가정에 기반한 <strong>추정치</strong>로, 실제 시장 상황과 상이할 수 있습니다.</li>
      <li>본 계산기 이용으로 발생하는 <strong>직·간접적 손실에 대해 운영자는 일체의 법적 책임을 지지 않습니다.</strong></li>
      <li>모든 투자 판단과 그에 따른 결과의 책임은 <strong>전적으로 투자자 본인</strong>에게 있습니다.</li>
      <li>투자 전 반드시 금융투자협회 전자공시시스템(DART), 증권사 HTS/MTS 등 <strong>공식 채널의 정보를 직접 확인</strong>하시기 바랍니다.</li>
    </ul>
  </div>
</div>
```

### 복지/소득 계산기용 (medianincome 등)

```html
<div class="bd-disclaimer">
  <p><strong>면책 조항 (Disclaimer)</strong></p>
  <ul class="bd-disclaimer-list">
    <li>본 계산기는 <strong>단순 참고용</strong>이며, 공식적인 수급 자격 판정이 아닙니다.</li>
    <li>실제 수급 자격은 소득·재산·부양의무자 등 <strong>추가 기준이 적용</strong>되며, 본 계산기의 결과와 상이할 수 있습니다.</li>
    <li>본 페이지에 기재된 수치·비율은 2026년 보건복지부 고시 기준 <strong>추정치</strong>로, 향후 변경될 수 있습니다.</li>
    <li>정책별 기준은 매년 변경될 수 있으며, 최신 정보는 <strong>보건복지부 및 해당 기관의 공식 공시</strong>를 확인하시기 바랍니다.</li>
    <li>본 계산기 이용으로 발생하는 <strong>직·간접적 불이익에 대해 운영자는 일체의 법적 책임을 지지 않습니다.</strong></li>
    <li>정확한 자격 확인은 <strong>주민센터 또는 해당 기관</strong>에 직접 문의하시기 바랍니다.</li>
  </ul>
</div>
```

### 공통 스타일 패턴

- 제목: `<p><strong>면책 조항 (Disclaimer)</strong></p>`
- 리스트: `·` prefix, 작은 폰트 (12~13px), muted 색상
- 핵심 항목은 `<strong>` 태그로 강조
- 반드시 포함할 항목:
  1. 단순 참고용임을 명시
  2. 오류 가능성 안내
  3. 추정치 기반임을 명시
  4. 법적 책임 면책
  5. 본인 책임 명시
  6. 공식 채널 확인 안내

---

## 3. BioDaddy Hub Footer

### Dark Theme (kbank 등)

```html
<footer class="footer">
  <div class="container">
    <div class="footer-links">
      <a href="https://blog.naver.com/biodad" target="_blank" rel="noopener">블로그</a>
      <span class="footer-dot">·</span>
      <a href="https://farmingdollar.com" target="_blank" rel="noopener">farmingdollar.com</a>
    </div>
    <p class="copyright">&copy; 2026 바이오대디. All rights reserved.</p>
  </div>
</footer>
```

### Light Theme (medianincome 등 - 카드 바깥)

```html
<footer class="bd-footer">
  <div class="bd-footer-links">
    <a href="https://blog.naver.com/biodad" target="_blank" rel="noopener">블로그</a>
    <span class="bd-footer-dot">·</span>
    <a href="https://farmingdollar.com" target="_blank" rel="noopener">farmingdollar.com</a>
  </div>
  <p class="bd-copyright">&copy; 2026 바이오대디. All rights reserved.</p>
</footer>
```

### 필수 링크

| 항목 | URL |
|------|-----|
| 블로그 | https://blog.naver.com/biodad |
| 메인 사이트 | https://farmingdollar.com |
| Copyright | &copy; 2026 바이오대디. All rights reserved. |

---

## 4. SEO / Open Graph 패턴 (kbank 참고)

새 계산기 페이지 생성 시 OG 태그 포함:

```html
<!-- Open Graph -->
<meta property="og:title" content="[페이지 제목]">
<meta property="og:description" content="[한 줄 설명]">
<meta property="og:image" content="https://[subdomain].farmingdollar.com/og-image.png">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
<meta property="og:type" content="website">
<meta property="og:url" content="https://[subdomain].farmingdollar.com">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="[페이지 제목]">
<meta name="twitter:description" content="[한 줄 설명]">
<meta name="twitter:image" content="https://[subdomain].farmingdollar.com/og-image.png">
```

### OG Image (SVG → PNG)

- 크기: 1200x630
- 배경: `#0a0e1a` → `#111827` 그라데이션
- 상단 4px accent 라인
- 좌측: 제목 + 핵심 수치 카드
- 우측: 시나리오/데이터 프리뷰
- 하단: `farmingdollar.com` + `© 바이오대디`

---

## 5. 페이지 제목 패턴

```
[페이지명] | 바이오대디
```

예시:
- `케이뱅크 IPO 수익 계산기 | 바이오대디`
- `2026년 중위소득 계산기 | 바이오대디`

---

## 6. 공통 Design Tokens

### Dark Theme (kbank 계열)

```css
--bg: #0a0e1a;
--bg-card: #111827;
--border: #1e293b;
--text: #e2e8f0;
--text-dim: #94a3b8;
--text-muted: #64748b;
--accent: #3b82f6;
--green: #22c55e;
--red: #ef4444;
--yellow: #eab308;
```

### Light Theme (medianincome 계열)

```css
background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
accent: #e94560;
card-bg: white;
```

---

## 7. 블로그 배너 (외부 링크 연결)

계산기/도구 페이지 내에서 관련 블로그 글이나 외부 콘텐츠를 자연스럽게 노출하는 카드형 배너.

### 배치 위치

- 결과 섹션과 정보/안내 섹션 사이 (콘텐츠 하단부)
- 여러 개일 경우 순서대로 나열 (관련도 높은 글을 먼저)

### CSS

```css
/* Blog Banner */
.blog-banner {
    display: block;
    background: var(--card-background);
    border-radius: 16px;
    padding: 20px;
    box-shadow: 0 2px 12px rgba(0, 0, 0, 0.08);
    margin-bottom: 20px;
    text-decoration: none;
    color: var(--text-primary);
    border: 1px solid var(--border-color);
    transition: all 0.25s ease;
    position: relative;
    overflow: hidden;
}

.blog-banner:hover {
    border-color: var(--secondary-color);
    box-shadow: 0 4px 20px rgba(52, 152, 219, 0.15);
    transform: translateY(-2px);
}

.blog-banner::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 4px;
    height: 100%;
    background: linear-gradient(180deg, var(--secondary-color), var(--primary-light));
}

.blog-banner-badge {
    display: inline-block;
    background: linear-gradient(135deg, var(--secondary-color), var(--primary-light));
    color: white;
    font-size: 0.7rem;
    font-weight: 700;
    padding: 3px 10px;
    border-radius: 20px;
    margin-bottom: 10px;
    letter-spacing: 0.5px;
}

.blog-banner-title {
    font-size: 1rem;
    font-weight: 700;
    color: var(--text-primary);
    margin-bottom: 6px;
    line-height: 1.4;
}

.blog-banner-desc {
    font-size: 0.82rem;
    color: var(--text-secondary);
    line-height: 1.5;
    margin-bottom: 10px;
}

.blog-banner-cta {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    font-size: 0.82rem;
    font-weight: 600;
    color: var(--secondary-color);
}

.blog-banner-cta svg {
    transition: transform 0.2s;
}

.blog-banner:hover .blog-banner-cta svg {
    transform: translateX(3px);
}

@media (min-width: 600px) {
    .blog-banner {
        padding: 24px;
        margin-bottom: 24px;
    }
    .blog-banner-title {
        font-size: 1.1rem;
    }
}
```

### HTML 템플릿

```html
<a href="[링크 URL]" target="_blank" rel="noopener" class="blog-banner">
    <span class="blog-banner-badge">[뱃지 텍스트]</span>
    <div class="blog-banner-title">[배너 제목]</div>
    <div class="blog-banner-desc">[한 줄 설명]</div>
    <span class="blog-banner-cta">
        자세히 보기
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>
    </span>
</a>
```

### 뱃지 텍스트 가이드

| 콘텐츠 유형 | 뱃지 | 예시 |
|-------------|------|------|
| 네이버 블로그 | `BLOG` | 계산기 활용법, 후기 |
| 경제/재테크 | `ECONOMY` | 부의 추월차선, 투자 전략 |
| 가이드/팁 | `GUIDE` | 신청 방법, 절차 안내 |
| farmingdollar 콘텐츠 | `ARTICLE` | 자체 사이트 글 |

### 작성 규칙

- **제목**: 블로그 원문 제목을 그대로 사용하거나, 계산기 맥락에 맞게 살짝 변형
- **설명**: 1줄, 해당 글이 사용자에게 주는 실질적 가치를 명시
- **CTA**: "자세히 보기" 고정, 화살표 아이콘 포함
- **왼쪽 액센트 바**: `::before`로 자동 적용 (페이지 accent 색상 연동)
- **호버 효과**: 위로 2px 이동 + 테두리 색 변경 + 화살표 3px 슬라이드

### 적용 예시 (mortgage 계산기)

```html
<!-- 네이버 블로그 글 -->
<a href="https://blog.naver.com/biodad/224193705560" target="_blank" rel="noopener" class="blog-banner">
    <span class="blog-banner-badge">BLOG</span>
    <div class="blog-banner-title">3월 이사 시즌, 주택담보대출 '월 납부액'만 보면 큰일납니다</div>
    <div class="blog-banner-desc">유예·상환방식별 총 이자 차이, 이 계산기 활용법까지 한 번에 정리했습니다.</div>
    <span class="blog-banner-cta">
        자세히 보기
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>
    </span>
</a>

<!-- farmingdollar 경제 콘텐츠 -->
<a href="https://www.farmingdollar.com/economy/TheMillionaireFastlane.html" target="_blank" rel="noopener" class="blog-banner">
    <span class="blog-banner-badge">ECONOMY</span>
    <div class="blog-banner-title">부의 추월차선 핵심 요약 — 대출 갚는 동안, 돈이 일하게 만드는 법</div>
    <div class="blog-banner-desc">MJ 드마코의 경제적 자유 전략과 NEED 공식, 시스템으로 수동 소득을 만드는 핵심을 정리했습니다.</div>
    <span class="blog-banner-cta">
        자세히 보기
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>
    </span>
</a>
```

---

## 체크리스트 (새 페이지 추가 시)

- [ ] `<title>` 에 `| 바이오대디` 포함
- [ ] Sticky nav header (`← BioDaddy Hub` → farmingdollar.com)
- [ ] 면책 조항 (Disclaimer) - 도메인에 맞게 커스터마이즈
- [ ] Footer (블로그 · farmingdollar.com · copyright)
- [ ] Open Graph + Twitter Card 메타 태그
- [ ] 블로그 배너 (관련 글 있을 경우 추가)
- [ ] Google AdSense 스크립트 (필요 시)
- [ ] 모바일 반응형 확인
