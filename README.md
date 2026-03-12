# KoEngClub
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>윤하 패밀리 마스터플랜</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;700;900&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #080f1e;
    --bg2: #0d1829;
    --card: #111f35;
    --border: #1a3050;
    --accent: #f0a500;
    --accent2: #fcd34d;
    --teal: #14b8a6;
    --red: #ef4444;
    --blue: #3b82f6;
    --green: #22c55e;
    --purple: #a855f7;
    --text: #e2e8f0;
    --muted: #64748b;
    --muted2: #94a3b8;
  }
  * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
  html, body { background: var(--bg); color: var(--text); font-family: 'Noto Sans KR', sans-serif; min-height: 100vh; overflow-x: hidden; font-size: 15px; }
  .top-header { background: linear-gradient(135deg, #0d1829 0%, #0a1628 100%); border-bottom: 1px solid var(--border); padding: 20px 16px 16px; position: sticky; top: 0; z-index: 100; }
  .top-header h1 { font-size: 1.25rem; font-weight: 900; letter-spacing: -0.5px; color: #fff; }
  .top-header h1 span { color: var(--accent); }
  .goal-pill { display: inline-block; margin-top: 6px; background: linear-gradient(90deg, rgba(240,165,0,0.2), rgba(252,211,77,0.1)); border: 1px solid rgba(240,165,0,0.35); border-radius: 20px; padding: 4px 12px; font-size: 0.72rem; font-weight: 700; color: var(--accent2); letter-spacing: 0.3px; }
  .tab-nav { display: flex; overflow-x: auto; background: var(--bg2); border-bottom: 1px solid var(--border); padding: 0 8px; scrollbar-width: none; -ms-overflow-style: none; position: sticky; top: 76px; z-index: 99; }
  .tab-nav::-webkit-scrollbar { display: none; }
  .tab-btn { flex-shrink: 0; padding: 12px 14px; font-size: 0.75rem; font-weight: 600; font-family: 'Noto Sans KR', sans-serif; color: var(--muted2); background: none; border: none; border-bottom: 2px solid transparent; cursor: pointer; white-space: nowrap; transition: all 0.2s; }
  .tab-btn.active { color: var(--accent); border-bottom-color: var(--accent); }
  .tab-content { display: none; padding: 16px; }
  .tab-content.active { display: block; }
  .card { background: var(--card); border: 1px solid var(--border); border-radius: 12px; padding: 16px; margin-bottom: 12px; position: relative; overflow: hidden; }
  .card-accent-line { position: absolute; top: 0; left: 0; right: 0; height: 2px; }
  .section-label { font-size: 0.62rem; font-weight: 700; letter-spacing: 2.5px; text-transform: uppercase; color: var(--accent); margin-bottom: 12px; }
  .kpi-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 12px; }
  .kpi-card { background: var(--card); border: 1px solid var(--border); border-radius: 10px; padding: 14px 12px; position: relative; overflow: hidden; }
  .kpi-label { font-size: 0.62rem; color: var(--muted2); font-weight: 500; letter-spacing: 0.5px; margin-bottom: 4px; }
  .kpi-value { font-family: 'JetBrains Mono', monospace; font-size: 1.3rem; font-weight: 700; line-height: 1; }
  .kpi-sub { font-size: 0.68rem; color: var(--muted2); margin-top: 4px; font-weight: 300; }
  .phase-strip { display: flex; gap: 6px; overflow-x: auto; padding-bottom: 4px; scrollbar-width: none; margin-bottom: 12px; }
  .phase-strip::-webkit-scrollbar { display: none; }
  .phase-chip { flex-shrink: 0; padding: 8px 12px; border-radius: 8px; font-size: 0.72rem; font-weight: 700; text-align: center; white-space: nowrap; }
  .phase-chip.now { background: rgba(240,165,0,0.18); border: 1px solid rgba(240,165,0,0.4); color: var(--accent2); }
  .phase-chip.future { background: rgba(255,255,255,0.04); border: 1px solid var(--border); color: var(--muted2); }
  .phase-chip .phase-sub { display: block; font-size: 0.62rem; font-weight: 400; opacity: 0.75; margin-top: 2px; }
  .timeline { position: relative; padding-left: 20px; }
  .timeline::before { content: ''; position: absolute; left: 6px; top: 6px; bottom: 6px; width: 1px; background: linear-gradient(to bottom, var(--accent), var(--teal), var(--border)); }
  .tl-item { position: relative; padding-bottom: 20px; display: flex; flex-direction: column; gap: 2px; }
  .tl-item:last-child { padding-bottom: 0; }
  .tl-item::before { content: ''; position: absolute; left: -16px; top: 5px; width: 7px; height: 7px; border-radius: 50%; background: var(--accent); border: 1.5px solid var(--bg); box-shadow: 0 0 6px var(--accent); }
  .tl-item.key::before { width: 10px; height: 10px; left: -18px; top: 4px; background: var(--accent2); box-shadow: 0 0 10px var(--accent2); }
  .tl-item.done::before { background: var(--teal); box-shadow: 0 0 6px var(--teal); }
  .tl-date { font-family: 'JetBrains Mono', monospace; font-size: 0.68rem; color: var(--accent); font-weight: 700; }
  .tl-item.done .tl-date { color: var(--teal); }
  .tl-title { font-size: 0.88rem; font-weight: 600; color: #fff; line-height: 1.3; }
  .tl-desc { font-size: 0.75rem; color: var(--muted2); font-weight: 300; line-height: 1.4; }
  .badge { display: inline-block; padding: 1px 7px; border-radius: 3px; font-size: 0.6rem; font-weight: 700; margin-left: 6px; vertical-align: middle; }
  .badge.now { background: rgba(240,165,0,0.2); color: var(--accent); border: 1px solid rgba(240,165,0,0.3); }
  .badge.key { background: rgba(252,211,77,0.2); color: var(--accent2); border: 1px solid rgba(252,211,77,0.3); }
  .family-item { display: flex; align-items: center; gap: 12px; padding: 12px 0; border-bottom: 1px solid var(--border); }
  .family-item:last-child { border-bottom: none; padding-bottom: 0; }
  .family-item:first-child { padding-top: 0; }
  .avatar { width: 40px; height: 40px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.1rem; flex-shrink: 0; }
  .family-info h4 { font-size: 0.88rem; font-weight: 700; }
  .family-info p { font-size: 0.75rem; color: var(--muted2); margin-top: 2px; font-weight: 300; line-height: 1.4; }
  .asset-item { margin-bottom: 16px; }
  .asset-item:last-child { margin-bottom: 0; }
  .asset-header { display: flex; justify-content: space-between; align-items: baseline; margin-bottom: 6px; }
  .asset-name { font-size: 0.85rem; }
  .asset-amount { font-family: 'JetBrains Mono', monospace; font-weight: 700; font-size: 0.9rem; color: var(--accent); }
  .bar-bg { height: 6px; background: rgba(255,255,255,0.08); border-radius: 3px; overflow: hidden; }
  .bar-fill { height: 100%; border-radius: 3px; }
  .asset-note { font-size: 0.7rem; color: var(--muted2); margin-top: 4px; }
  .invest-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: 14px; }
  .invest-item { border-radius: 8px; padding: 12px; }
  .invest-label { font-size: 0.68rem; color: var(--muted2); margin-bottom: 4px; }
  .invest-amount { font-family: 'JetBrains Mono', monospace; font-weight: 700; font-size: 1rem; }
  .cf-row { display: flex; justify-content: space-between; align-items: center; padding: 10px 0; border-bottom: 1px solid var(--border); font-size: 0.85rem; }
  .cf-row:last-child { border-bottom: none; }
  .cf-row.total { font-weight: 700; font-size: 0.95rem; color: #fff; }
  .cf-row .cf-note { font-size: 0.7rem; color: var(--muted2); font-weight: 300; }
  .plus { color: var(--green); font-family: 'JetBrains Mono', monospace; font-weight: 700; }
  .minus { color: var(--red); font-family: 'JetBrains Mono', monospace; font-weight: 700; }
  .biz-item { border-radius: 10px; padding: 14px; margin-bottom: 10px; }
  .biz-item:last-child { margin-bottom: 0; }
  .biz-title { font-size: 0.9rem; font-weight: 700; margin-bottom: 6px; }
  .biz-desc { font-size: 0.78rem; color: var(--muted2); line-height: 1.6; font-weight: 300; }
  .biz-highlight { color: var(--accent2); font-weight: 600; }
  .risk-item { display: flex; gap: 10px; align-items: flex-start; padding: 12px 0; border-bottom: 1px solid var(--border); }
  .risk-item:last-child { border-bottom: none; padding-bottom: 0; }
  .risk-item:first-child { padding-top: 0; }
  .risk-badge { flex-shrink: 0; padding: 3px 8px; border-radius: 4px; font-size: 0.6rem; font-weight: 700; letter-spacing: 0.5px; margin-top: 1px; }
  .risk-badge.high { background: rgba(239,68,68,0.2); color: #fca5a5; border: 1px solid rgba(239,68,68,0.3); }
  .risk-badge.mid { background: rgba(234,179,8,0.2); color: #fde047; border: 1px solid rgba(234,179,8,0.3); }
  .risk-badge.low { background: rgba(34,197,94,0.2); color: #86efac; border: 1px solid rgba(34,197,94,0.3); }
  .risk-title { font-size: 0.85rem; font-weight: 600; margin-bottom: 3px; }
  .risk-desc { font-size: 0.75rem; color: var(--muted2); font-weight: 300; line-height: 1.4; }
  .action-item { display: flex; gap: 14px; align-items: flex-start; padding: 14px 0; border-bottom: 1px solid var(--border); }
  .action-item:first-child { padding-top: 0; }
  .action-item:last-child { border-bottom: none; padding-bottom: 0; }
  .action-num { width: 30px; height: 30px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-weight: 900; font-size: 0.85rem; flex-shrink: 0; }
  .action-num.p1 { background: var(--accent); color: var(--bg); }
  .action-num.p2 { background: var(--red); color: #fff; }
  .action-num.p3 { background: var(--blue); color: #fff; }
  .action-num.p4 { background: var(--purple); color: #fff; }
  .action-title { font-size: 0.9rem; font-weight: 700; line-height: 1.3; margin-bottom: 4px; }
  .action-desc { font-size: 0.75rem; color: var(--muted2); font-weight: 300; line-height: 1.4; }
  .planb-box { background: rgba(239,68,68,0.07); border: 1px solid rgba(239,68,68,0.2); border-radius: 10px; padding: 14px; margin-top: 12px; }
  .planb-box .section-label { color: #f87171; }
  .callout { border-radius: 8px; padding: 12px 14px; font-size: 0.8rem; line-height: 1.5; margin-bottom: 10px; font-weight: 400; }
  .callout.yellow { background: rgba(252,211,77,0.1); border: 1px solid rgba(252,211,77,0.25); color: var(--accent2); }
  .callout.red { background: rgba(239,68,68,0.1); border: 1px solid rgba(239,68,68,0.25); color: #fca5a5; }
  .callout.teal { background: rgba(20,184,166,0.1); border: 1px solid rgba(20,184,166,0.25); color: #5eead4; }
  .footer-note { text-align: center; padding: 20px 16px; font-size: 0.72rem; color: var(--muted); border-top: 1px solid var(--border); margin-top: 4px; }
  .divider { height: 1px; background: var(--border); margin: 14px 0; }
  .two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-bottom: 10px; }
  .mini-card { background: rgba(255,255,255,0.03); border: 1px solid var(--border); border-radius: 8px; padding: 10px 12px; }
  .mini-label { font-size: 0.62rem; color: var(--muted2); margin-bottom: 4px; }
  .mini-value { font-size: 0.82rem; font-weight: 700; }
</style>
</head>
<body>

<div class="top-header">
  <h1>윤하 패밀리 <span>마스터플랜</span></h1>
  <div class="goal-pill">🎯 2029년 아영이 마닐라 국제학교 입학</div>
</div>

<div class="tab-nav">
  <button class="tab-btn active" onclick="switchTab('overview', this)">📊 전체현황</button>
  <button class="tab-btn" onclick="switchTab('timeline', this)">⏱ 타임라인</button>
  <button class="tab-btn" onclick="switchTab('assets', this)">💰 자산</button>
  <button class="tab-btn" onclick="switchTab('biz', this)">🏫 사업</button>
  <button class="tab-btn" onclick="switchTab('edu', this)">📚 교육센터</button>
  <button class="tab-btn" onclick="switchTab('risk', this)">⚠️ 리스크</button>
  <button class="tab-btn" onclick="switchTab('action', this)">🔥 할일</button>
</div>

<!-- ===== TAB 1: 전체현황 ===== -->
<div id="tab-overview" class="tab-content active">
  <div class="phase-strip">
    <div class="phase-chip now">🔥 지금<span class="phase-sub">준비·셋업</span></div>
    <div class="phase-chip future">📦 이사<span class="phase-sub">26년 상반기</span></div>
    <div class="phase-chip future">🏗️ 계약<span class="phase-sub">26년 5~6월</span></div>
    <div class="phase-chip future">🏫 오픈<span class="phase-sub">26년 10월</span></div>
    <div class="phase-chip future">📈 안착<span class="phase-sub">27~28년</span></div>
    <div class="phase-chip future">✈️ 이주준비<span class="phase-sub">28년 하반기</span></div>
    <div class="phase-chip future">🌏 체류시작<span class="phase-sub">29년 ★특례</span></div>
  </div>

  <div class="kpi-grid">
    <div class="kpi-card" style="border-top: 2px solid var(--accent);">
      <div class="kpi-label">총 순자산</div>
      <div class="kpi-value" style="color:var(--accent);">26억</div>
      <div class="kpi-sub">아파트·주식·빌라</div>
    </div>
    <div class="kpi-card" style="border-top: 2px solid var(--teal);">
      <div class="kpi-label">체류 시작까지</div>
      <div class="kpi-value" style="color:var(--teal);">약 36개월</div>
      <div class="kpi-sub">29년 초 12년 특례 개시</div>
    </div>
    <div class="kpi-card" style="border-top: 2px solid var(--green);">
      <div class="kpi-label">목표 현금흐름</div>
      <div class="kpi-value" style="color:var(--green);">월 1천</div>
      <div class="kpi-sub">이주 전 달성 필수</div>
    </div>
    <div class="kpi-card" style="border-top: 2px solid var(--blue);">
      <div class="kpi-label">현재 월 순흐름</div>
      <div class="kpi-value" style="color:var(--blue);">+490만</div>
      <div class="kpi-sub">아내 육휴 시 -210만</div>
    </div>
  </div>

  <div class="card">
    <div class="card-accent-line" style="background: linear-gradient(90deg,var(--teal),transparent)"></div>
    <div class="section-label">가족 현황</div>
    <div class="family-item">
      <div class="avatar" style="background:rgba(240,165,0,0.15)">👨</div>
      <div class="family-info">
        <h4>본인 — 쿠팡 연봉 1억 (육휴 중)</h4>
        <p>잔여 ~30개월 / 플랜B 복직 가능<br>한국어 교육 담당 (교육센터)</p>
      </div>
    </div>
    <div class="family-item">
      <div class="avatar" style="background:rgba(59,130,246,0.15)">👩</div>
      <div class="family-info">
        <h4>아내 — 카카오페이 (연봉 1억)</h4>
        <p>곧 육휴 예정 / 이주 전 퇴직<br>영어 교육 담당 (유펜 졸업)</p>
      </div>
    </div>
    <div class="family-item">
      <div class="avatar" style="background:rgba(20,184,166,0.15)">👧</div>
      <div class="family-info">
        <h4>아영이 (23.02생)</h4>
        <p>26.03 판교 어린이집 → 29년 마닐라 체류 시작 (12년 특례)</p>
      </div>
    </div>
    <div class="family-item">
      <div class="avatar" style="background:rgba(168,85,247,0.15)">👶</div>
      <div class="family-info">
        <h4>토토 (26.05 출생예정)</h4>
        <p>아들</p>
      </div>
    </div>
  </div>

  <div class="planb-box">
    <div class="section-label">플랜 B</div>
    <div style="font-size:0.85rem; line-height:1.7;">
      창업+이주 실패 시 <strong style="color:#f87171;">쿠팡 복직</strong><br>
      <span style="color:var(--muted2); font-size:0.75rem;">언제든 복직 가능한 안전망 보유</span>
    </div>
  </div>
</div>

<!-- ===== TAB 2: 타임라인 ===== -->
<div id="tab-timeline" class="tab-content">
  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--accent),var(--teal))"></div>
    <div class="section-label">전체 타임라인</div>
    <div class="timeline">
      <div class="tl-item done">
        <div class="tl-date">25.10</div>
        <div class="tl-title">본인 육아휴직 시작</div>
        <div class="tl-desc">사업 셋업 기간 확보 — 최대 30개월</div>
      </div>
      <div class="tl-item key">
        <div class="tl-date">26.03</div>
        <div class="tl-title">아영이 판교 어린이집 등원 <span class="badge now">NOW</span></div>
        <div class="tl-desc">타깃 상권과 생활 동선 일치</div>
      </div>
      <div class="tl-item">
        <div class="tl-date">26.05</div>
        <div class="tl-title">토토 출생 예정 🍼</div>
        <div class="tl-desc">아내 육아휴직 시작</div>
      </div>
      <div class="tl-item">
        <div class="tl-date">26.상반기</div>
        <div class="tl-title">판교 전세 이사</div>
        <div class="tl-desc">10억 전세 — 차액 2.4억 필요</div>
      </div>
      <div class="tl-item key">
        <div class="tl-date">26.03~04</div>
        <div class="tl-title">호두잉글리시 멘토링 + 상권 답사 <span class="badge key">핵심</span></div>
        <div class="tl-desc">김민우 대표님 — 지금 당장 일정 잡기. 10월 오픈까지 시간 없음</div>
      </div>
      <div class="tl-item key">
        <div class="tl-date">26.03~</div>
        <div class="tl-title">경쟁 교육센터 현장 답사 <span class="badge key">핵심</span></div>
        <div class="tl-desc">학부모로 위장 — 커리큘럼·운영 시스템·수강료·정원 파악. 최소 4~5곳 방문 목표</div>
      </div>
      <div class="tl-item">
        <div class="tl-date">26.03~</div>
        <div class="tl-title">테크 창업가 친구 회사 방문</div>
        <div class="tl-desc">교육 시스템·학부모 소통 솔루션 벤치마킹. 상호 협업 제안 준비 (스타트업+이커머스 경험 제공)</div>
      </div>
      <div class="tl-item">
        <div class="tl-date">26.05~06</div>
        <div class="tl-title">상가 계약 ⚠️</div>
        <div class="tl-desc">토토 출생과 겹치는 구간 — 아내 출산 직후, 본인 단독 진행 각오 필요</div>
      </div>
      <div class="tl-item">
        <div class="tl-date">26.07~09</div>
        <div class="tl-title">인테리어 + 커리큘럼·브랜딩 준비</div>
        <div class="tl-desc">유펜·초등교장·대원외고 교사 등 전문가 협업 콘텐츠 설계</div>
      </div>
      <div class="tl-item key">
        <div class="tl-date">26.10</div>
        <div class="tl-title">이중언어 교육센터 오픈 🏫</div>
        <div class="tl-desc">한국어(본인) + 영어(아내) 이중언어 교육. 6~13세 대상. 전문가 신뢰 기반 포지셔닝</div>
      </div>
      <div class="tl-item">
        <div class="tl-date">26.10~28.상반기</div>
        <div class="tl-title">사업 안착 + 매니저 육성</div>
        <div class="tl-desc">이주 6~12개월 전부터 이양 훈련 시작</div>
      </div>
      <div class="tl-item">
        <div class="tl-date">28.초~중반</div>
        <div class="tl-title">아내 복직 — 황금 저축 구간</div>
        <div class="tl-desc">월 +1,040만원 저축 가능 (본인 700 + 아내 700 + 빌라 140 - 지출 500)</div>
      </div>
      <div class="tl-item key">
        <div class="tl-date">28.하반기</div>
        <div class="tl-title">마닐라 전원이주 준비 완료 ✈️</div>
        <div class="tl-desc">아내 퇴직 — 매니저에게 사업 위임 / 이주 직전 최종 점검</div>
      </div>
      <div class="tl-item key">
        <div class="tl-date">29년 초</div>
        <div class="tl-title">마닐라 체류 시작 🌏 <span class="badge key">12년 특례 D-DAY</span></div>
        <div class="tl-desc">아영이 해외 체류 공식 시작 — 12년 특례 카운트 개시</div>
      </div>
      <div class="tl-item key">
        <div class="tl-date">29년~</div>
        <div class="tl-title">아영이 국제학교 입학 🎓</div>
        <div class="tl-desc">마닐라 영어학원 창업 / 41년까지 12년 특례 완성</div>
      </div>
    </div>
  </div>
</div>

<!-- ===== TAB 3: 자산 ===== -->
<div id="tab-assets" class="tab-content">
  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--accent),transparent)"></div>
    <div class="section-label">자산 구성 — 총 26억</div>
    <div class="asset-item">
      <div class="asset-header">
        <span class="asset-name">🏠 아파트 (위례 25평)</span>
        <span class="asset-amount">15억</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" style="width:57.7%; background:linear-gradient(90deg,#3b82f6,#1d4ed8)"></div></div>
      <div class="asset-note">전세 6.7억 수령 중</div>
    </div>
    <div class="asset-item">
      <div class="asset-header">
        <span class="asset-name">📈 현금/주식</span>
        <span class="asset-amount">8억</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" style="width:30.8%; background:linear-gradient(90deg,var(--accent),var(--accent2))"></div></div>
      <div class="asset-note">전액 주식 투자 중 (수익률 ~0%)</div>
    </div>
    <div class="asset-item">
      <div class="asset-header">
        <span class="asset-name">🏘️ 빌라</span>
        <span class="asset-amount">3억</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" style="width:11.5%; background:linear-gradient(90deg,var(--teal),#0f766e)"></div></div>
      <div class="asset-note">월세 140만원 — 이주 후에도 유지</div>
    </div>
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--blue),transparent)"></div>
    <div class="section-label">초기 투자금 배분안 (8억)</div>
    <div class="invest-grid">
      <div class="invest-item" style="background:rgba(240,165,0,0.1);border:1px solid rgba(240,165,0,0.2);">
        <div class="invest-label">판교 전세 증액</div>
        <div class="invest-amount" style="color:var(--accent);">2.4억</div>
      </div>
      <div class="invest-item" style="background:rgba(59,130,246,0.1);border:1px solid rgba(59,130,246,0.2);">
        <div class="invest-label">교육센터 창업</div>
        <div class="invest-amount" style="color:#60a5fa;">1.5억</div>
      </div>
      <div class="invest-item" style="background:rgba(20,184,166,0.1);border:1px solid rgba(20,184,166,0.2);">
        <div class="invest-label">비상예비금</div>
        <div class="invest-amount" style="color:var(--teal);">2억</div>
      </div>
      <div class="invest-item" style="background:rgba(168,85,247,0.1);border:1px solid rgba(168,85,247,0.2);">
        <div class="invest-label">주식 유지</div>
        <div class="invest-amount" style="color:#c084fc;">2.1억</div>
      </div>
    </div>
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--green),transparent)"></div>
    <div class="section-label">현재 월 현금흐름</div>
    <div class="cf-row"><span>빌라 월세</span><span class="plus">+140만</span></div>
    <div class="cf-row"><span>본인 육휴급여</span><span class="plus">+150만</span></div>
    <div class="cf-row"><span>아내 급여</span><span class="plus">+700만</span></div>
    <div class="cf-row"><span>고정지출</span><span class="minus">-500만</span></div>
    <div class="divider"></div>
    <div class="cf-row total"><span>순 현금흐름</span><span class="plus">+490만</span></div>
    <div style="font-size:0.72rem; color:var(--muted2); margin-top:8px;">* 아내 육휴 시 -210만원으로 감소</div>
    <div class="divider"></div>
    <div class="section-label" style="margin-bottom:8px;">저축 시뮬레이션</div>
    <div class="cf-row">
      <div><div style="font-size:0.82rem;">현재~26년 중반</div><div class="cf-note">아내 육휴 전</div></div>
      <span class="plus">+500만/월</span>
    </div>
    <div class="cf-row">
      <div><div style="font-size:0.82rem;">육휴 겹치는 구간</div><div class="cf-note">두 분 동시 육휴</div></div>
      <span class="minus">-100만/월</span>
    </div>
    <div class="cf-row" style="border-bottom:none;">
      <div><div style="font-size:0.82rem;">28년~이주 전</div><div class="cf-note">두 분 복직 시</div></div>
      <span class="plus">+500만/월</span>
    </div>
    <div style="margin-top:10px; padding:10px 12px; background:rgba(34,197,94,0.08); border:1px solid rgba(34,197,94,0.2); border-radius:8px; font-size:0.78rem; color:#86efac;">
      📊 이주 전 추가 저축 예상 약 <strong>2~3억</strong> (사업 수익 제외)
    </div>
  </div>
</div>

<!-- ===== TAB 4: 사업 ===== -->
<div id="tab-biz" class="tab-content">
  <div class="callout yellow">
    💡 지금 당장 해야 할 것: <strong>호두잉글리시 김민우 대표님 방문 일정 잡기</strong> — 현재 가장 ROI 높은 행동
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,#3b82f6,transparent)"></div>
    <div class="section-label">국내 사업 — 이중언어 교육센터</div>
    <div class="biz-item" style="background:rgba(59,130,246,0.08);border:1px solid rgba(59,130,246,0.2);">
      <div class="biz-title">🏫 판교 이중언어 교육센터</div>
      <div class="biz-desc">
        판교 1순위 / 위례 2순위<br>
        독립창업 / 초기 투자 <strong style="color:#fff;">1.5억</strong><br>
        대상: 6~13세 (프리스쿨 ~ 초등 전 학년)<br>
        <span class="biz-highlight">✦ 본인: 한국어 읽기·쓰기·말하기<br>✦ 아내: 영어 읽기·쓰기·말하기 (유펜 졸업)</span><br>
        목표 수익: 월 1,000만원<br>
        이주 후: 매니저 고용 → 원격 운영
      </div>
    </div>
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--purple),transparent)"></div>
    <div class="section-label">장기 비전 — 스케일러블 모델</div>
    <div class="biz-item" style="background:rgba(168,85,247,0.08);border:1px solid rgba(168,85,247,0.2);">
      <div class="biz-title">📱 앱·소프트웨어 확장</div>
      <div class="biz-desc">
        단순 학원이 아닌 <strong style="color:#fff;">교육 플랫폼 비즈니스</strong><br>
        학부모 소통 시스템 → 자체 서비스화<br>
        커리큘럼 관리 앱 → 프랜차이즈 확장 기반<br>
        테크 창업가 친구와 시스템 공동 개발 모색
      </div>
    </div>
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--teal),transparent)"></div>
    <div class="section-label">해외 사업 — 마닐라 영어학원</div>
    <div class="biz-item" style="background:rgba(20,184,166,0.08);border:1px solid rgba(20,184,166,0.2);">
      <div class="biz-title">🌏 마닐라 영어학원</div>
      <div class="biz-desc">
        이주 후 현지 창업<br>
        12년 특례 체류 조건 충족<br>
        국내 교육센터와 브랜드·커리큘럼 시너지
      </div>
    </div>
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--accent),transparent)"></div>
    <div class="section-label">멘토링 기회</div>
    <div class="biz-item" style="background:rgba(240,165,0,0.08);border:1px solid rgba(240,165,0,0.2);">
      <div class="biz-title">💡 호두잉글리시 김민우 대표</div>
      <div class="biz-desc">
        "언제든 놀러와서 일 배워도 된다"<br>
        업계 구조, 운영 노하우, 네트워크 무료 습득<br>
        <span style="color:var(--accent);">→ 판교 이사 후 바로 방문 일정 잡기</span>
      </div>
    </div>
  </div>

  <div class="card" style="background:rgba(239,68,68,0.05); border-color:rgba(239,68,68,0.15);">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--red),transparent)"></div>
    <div class="section-label" style="color:#f87171;">버려야 할 것</div>
    <div style="font-size:0.85rem; line-height:1.6; color:var(--muted2);">
      <strong style="color:#fca5a5;">❌ 무인편의점</strong><br>
      월 140~200만원 수준 대비 관리 리소스 소모<br>
      핵심 사업과 시너지 없음 — 지금 단계 에너지 분산
    </div>
  </div>
</div>

<!-- ===== TAB 5: 교육센터 상세 ===== -->
<div id="tab-edu" class="tab-content">
  <div class="callout teal">
    📚 핵심 전략: 단순 영어학원이 아닌 <strong>한국어+영어 이중언어 전문 교육센터</strong>로 포지셔닝
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--blue),transparent)"></div>
    <div class="section-label">교육 구조</div>
    <div class="two-col">
      <div class="mini-card" style="border-color:rgba(240,165,0,0.3);">
        <div class="mini-label" style="color:var(--accent);">🇰🇷 한국어 파트</div>
        <div class="mini-value" style="font-size:0.78rem; color:var(--muted2); font-weight:400; margin-top:4px;">담당: 본인<br>읽기·쓰기·말하기<br>체계적 국어 교육</div>
      </div>
      <div class="mini-card" style="border-color:rgba(59,130,246,0.3);">
        <div class="mini-label" style="color:#60a5fa;">🇺🇸 영어 파트</div>
        <div class="mini-value" style="font-size:0.78rem; color:var(--muted2); font-weight:400; margin-top:4px;">담당: 아내 (유펜 졸업)<br>읽기·쓰기·말하기<br>원어민 수준 지도</div>
      </div>
    </div>
    <div style="padding:12px; background:rgba(255,255,255,0.03); border-radius:8px; margin-top:4px;">
      <div style="font-size:0.72rem; color:var(--muted2); margin-bottom:6px;">대상 연령</div>
      <div style="font-size:0.85rem; font-weight:600;">6세 ~ 13세 (프리스쿨 ~ 초등 전 학년)</div>
    </div>
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--accent),transparent)"></div>
    <div class="section-label">브랜딩 포지셔닝</div>
    <div style="font-size:0.82rem; line-height:1.7; color:var(--muted2);">
      <strong style="color:#fff;">✦ 유펜 졸업</strong> — 영어 교육 신뢰도<br>
      <strong style="color:#fff;">✦ 전직 초등학교 교장</strong> — 교육 전문성<br>
      <strong style="color:#fff;">✦ 대원외고 교사</strong> — 명문 트랙 연결<br>
      <strong style="color:#fff;">✦ 이중언어 전문</strong> — 국내 희소성<br><br>
      <span style="color:var(--accent2);">"검증된 전문가들이 함께 만든 교육"</span>이 핵심 메시지
    </div>
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--teal),transparent)"></div>
    <div class="section-label">시장 리서치 전략 — 경쟁사 답사</div>
    <div style="font-size:0.82rem; line-height:1.7; color:var(--muted2); margin-bottom:12px;">
      <strong style="color:#fff;">방법:</strong> 학부모로 위장 ("아이 등록 고려 중인 부모")<br>
      <strong style="color:#fff;">목표:</strong> 4~5곳 이상 방문<br>
      <strong style="color:#fff;">이미 방문:</strong> 2곳 완료
    </div>
    <div style="font-size:0.72rem; color:var(--accent); font-weight:700; letter-spacing:1px; margin-bottom:8px;">방문 시 확인할 것</div>
    <div style="font-size:0.8rem; line-height:1.8; color:var(--muted2);">
      ▸ 한국어·영어 수업을 어떻게 구분해서 가르치나요?<br>
      ▸ 하루 수업 구성이 어떻게 되나요?<br>
      ▸ 학급 정원이 몇 명인가요?<br>
      ▸ 수업료와 포함 내역이 어떻게 되나요?<br>
      ▸ 아이 실력 향상을 부모님께 어떻게 공유하나요?<br>
      ▸ 우리 아이가 말하기를 많이 어려워하는데 어떻게 도와주나요?<br>
      ▸ 이 교육 방식을 선택하신 이유가 뭔가요?
    </div>
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--purple),transparent)"></div>
    <div class="section-label">테크 창업가 친구 협업 전략</div>
    <div style="font-size:0.82rem; line-height:1.7; color:var(--muted2); margin-bottom:10px;">
      친구 회사 방문 목적: 교육 시스템 + 학부모 소통 관리 시스템 벤치마킹
    </div>
    <div style="font-size:0.72rem; color:var(--accent); font-weight:700; letter-spacing:1px; margin-bottom:8px;">방문 시 확인할 것</div>
    <div style="font-size:0.8rem; line-height:1.8; color:var(--muted2);">
      ▸ 학부모 소통을 어떤 플랫폼으로 관리하나요?<br>
      ▸ 학생 진도와 성취도를 어떻게 트래킹하나요?<br>
      ▸ 처음 시작했을 때 어떤 시스템부터 구축했나요?<br>
      ▸ 확장할 때 가장 병목이 된 게 뭐였나요?<br>
      ▸ 지금 돌아보면 처음부터 다르게 만들었을 것이 있나요?
    </div>
    <div class="divider"></div>
    <div style="font-size:0.72rem; color:var(--purple); font-weight:700; letter-spacing:1px; margin-bottom:8px;">협업 제안 프레임</div>
    <div style="font-size:0.8rem; line-height:1.7; color:var(--muted2);">
      <strong style="color:#fff;">내가 줄 수 있는 것:</strong><br>
      스타트업 경험, 이커머스·라이브커머스 노하우, 사업 확장 경험<br><br>
      <strong style="color:#fff;">내가 받고 싶은 것:</strong><br>
      교육 시스템 설계 지원, 학부모 소통 플랫폼 공동 개발<br><br>
      <span style="color:var(--accent2);">→ "나는 네 사업 확장을 돕고, 너는 내 플랫폼 구축을 돕는다"</span>
    </div>
  </div>
</div>

<!-- ===== TAB 6: 리스크 ===== -->
<div id="tab-risk" class="tab-content">
  <div class="callout yellow">
    ✅ 29년 초 체류 시작으로 <strong>12년 특례 일정 확정</strong> — 이제 사업 안착이 핵심 과제입니다
  </div>

  <div class="card">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--red),transparent)"></div>
    <div class="section-label">리스크 관리</div>
    <div class="risk-item">
      <div><div class="risk-badge low">확정</div></div>
      <div>
        <div class="risk-title">12년 특례 — 29년 체류 시작 확정</div>
        <div class="risk-desc">29년 초 체류 시작 → 특례 카운트 개시 확정. 입시 컨설턴트 통해 학교 입학 시점·서류 요건 최종 확인 권장</div>
      </div>
    </div>
    <div class="risk-item">
      <div><div class="risk-badge high">HIGH</div></div>
      <div>
        <div class="risk-title">이주 후 수입 공백</div>
        <div class="risk-desc">아내+본인 동시 수입 0 → 사업 월 1,000만원 달성이 이주의 전제조건</div>
      </div>
    </div>
    <div class="risk-item">
      <div><div class="risk-badge mid">MID</div></div>
      <div>
        <div class="risk-title">아내 영어 파트 의존도</div>
        <div class="risk-desc">아내 이주 후 퇴직 → 영어 파트 대체 교사 채용 필요. 아내 육휴 기간 중 미리 백업 강사 발굴</div>
      </div>
    </div>
    <div class="risk-item">
      <div><div class="risk-badge mid">MID</div></div>
      <div>
        <div class="risk-title">매니저 의존 리스크</div>
        <div class="risk-desc">이주 6~12개월 전부터 채용 + 운영 이양 훈련 필요 / 창업 초기부터 구조 설계</div>
      </div>
    </div>
    <div class="risk-item">
      <div><div class="risk-badge mid">MID</div></div>
      <div>
        <div class="risk-title">사업 미안착</div>
        <div class="risk-desc">26년 10월 오픈 후 수익화 실패 시 → 플랜B 쿠팡 복직 / 멘토링으로 리스크 최소화</div>
      </div>
    </div>
    <div class="risk-item">
      <div><div class="risk-badge low">LOW</div></div>
      <div>
        <div class="risk-title">주식 매도 타이밍</div>
        <div class="risk-desc">수익률 ~0% → 분할 매도 유연하게 진행 가능</div>
      </div>
    </div>
  </div>
</div>

<!-- ===== TAB 7: 할일 ===== -->
<div id="tab-action" class="tab-content">
  <div class="card" style="border-color:rgba(240,165,0,0.4);">
    <div class="card-accent-line" style="background:linear-gradient(90deg,var(--accent),var(--accent2))"></div>
    <div class="section-label">지금 당장 해야 할 것</div>
    <div class="action-item">
      <div class="action-num p1">1</div>
      <div>
        <div class="action-title">호두잉글리시 김민우 대표님 방문 일정 잡기</div>
        <div class="action-desc">영어 교육 업계 구조·운영 노하우·네트워크 무료 습득<br>지금 할 수 있는 가장 ROI 높은 행동</div>
      </div>
    </div>
    <div class="action-item">
      <div class="action-num p2">2</div>
      <div>
        <div class="action-title">경쟁 교육센터 3~4곳 추가 방문</div>
        <div class="action-desc">학부모로 위장 — 커리큘럼·수강료·정원·학부모 소통 방식 파악<br>이미 2곳 완료. 3~4곳 추가 목표</div>
      </div>
    </div>
    <div class="action-item">
      <div class="action-num p3">3</div>
      <div>
        <div class="action-title">테크 창업가 친구 회사 방문</div>
        <div class="action-desc">교육 시스템·학부모 소통 솔루션 벤치마킹<br>상호 협업 제안 준비 (교육센터 + 스케일러블 플랫폼)</div>
      </div>
    </div>
    <div class="action-item">
      <div class="action-num p4">4</div>
      <div>
        <div class="action-title">12년 특례 세부 서류·절차 확인</div>
        <div class="action-desc">체류 시작 시점(29년 초) 확정 — 입시 컨설턴트 통해 학교 선정·입학 서류·비자 요건 사전 점검</div>
      </div>
    </div>
  </div>

  <div style="margin-top:4px; padding:14px 16px; background:var(--card); border:1px solid var(--border); border-radius:12px;">
    <div class="section-label">단순화한 집중 원칙</div>
    <div style="font-size:0.82rem; line-height:1.8; color:var(--muted2);">
      지금 가장 큰 문제는 뭘 먼저 할지가 아니라<br>
      <strong style="color:#fff;">뭘 하지 말아야 하는지</strong>입니다.<br><br>
      무인편의점·마닐라 준비·교육센터를 동시에 하면<br>
      전부 어설프게 됩니다. 2029년 이주까지 30개월.<br><br>
      <strong style="color:var(--accent2);">지금은 이중언어 교육센터 하나에만 집중하세요.</strong>
    </div>
  </div>
</div>

<div class="footer-note">윤하 패밀리 마스터플랜 · 2026년 3월 업데이트</div>

<script>
function switchTab(id, btn) {
  document.querySelectorAll('.tab-content').forEach(el => el.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(el => el.classList.remove('active'));
  document.getElementById('tab-' + id).classList.add('active');
  btn.classList.add('active');
}
</script>
</body>
</html>
