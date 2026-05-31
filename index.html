<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hotel Cordelia - 객실 및 시설 통합 관리 시스템</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flatpickr/dist/flatpickr.min.css">
    <style>
        :root {
            --bg-main: #f8f9fa;
            --card-bg: #ffffff;
            --text-dark: #222222;
            --text-muted: #777777;
            --border-color: #e5e7eb;
            --accent-green: #656d4a; /* 호텔 시그니처 올리브 그린 톤 */
            --accent-green-hover: #4f5539;
            --accent-red: #b91c1c;
            --status-bg-green: #f0fdf4;
            --status-text-green: #16a34a;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
        }

        body {
            background-color: var(--bg-main);
            color: var(--text-dark);
            padding: 24px;
            min-height: 100vh;
        }

        /* [1] 게이트웨이 로그인 스타일 */
        .gateway-container {
            max-width: 400px;
            margin: 100px auto;
            background: var(--card-bg);
            padding: 35px 30px;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.06);
            text-align: center;
        }

        .gateway-header h1 { font-size: 22px; margin-bottom: 6px; letter-spacing: -0.5px; }
        .gateway-header p { font-size: 13px; color: var(--text-muted); margin-bottom: 25px; }

        .mode-btn-group { display: flex; gap: 10px; margin-bottom: 20px; }
        .mode-btn {
            flex: 1; padding: 12px; border: 1px solid var(--border-color);
            background: #f9fafb; border-radius: 8px; cursor: pointer;
            font-weight: bold; font-size: 14px; transition: all 0.2s;
        }
        .mode-btn.active-op { background: var(--accent-green); color: white; border-color: var(--accent-green); }
        .mode-btn.active-admin { background: var(--accent-red); color: white; border-color: var(--accent-red); }

        .pin-box input {
            width: 100%; padding: 14px; border: 1px solid var(--border-color);
            border-radius: 8px; text-align: center; font-size: 18px;
            letter-spacing: 4px; margin-bottom: 15px;
        }
        .error-msg { color: var(--accent-red); font-size: 12px; margin-bottom: 15px; display: none; }
        
        .bypass-btn {
            background: none; border: none; color: #9ca3af; font-size: 11px;
            text-decoration: underline; cursor: pointer; margin-top: 12px;
        }

        /* [2] 메인 레이아웃 및 최상단 탑 네비게이션 */
        .app-container { display: none; max-width: 1400px; margin: 0 auto; }
        
        .app-top-bar {
            display: flex; justify-content: space-between; align-items: center;
            background: var(--card-bg); padding: 18px 24px; border-radius: 12px;
            margin-bottom: 20px; box-shadow: 0 1px 3px rgba(0,0,0,0.02);
        }
        .brand-title h2 { font-size: 20px; font-weight: 700; color: #111; }
        .brand-title p { font-size: 12px; color: var(--text-muted); margin-top: 2px; }
        .top-bar-actions { display: flex; align-items: center; gap: 10px; }
        
        .top-btn {
            padding: 8px 14px; border: 1px solid var(--border-color);
            background: #ffffff; border-radius: 6px; font-size: 13px; font-weight: 500;
            cursor: pointer; display: flex; align-items: center; gap: 4px;
        }
        .top-btn:hover { background: #f9fafb; }
        .top-btn.btn-danger { background: #fef2f2; color: var(--accent-red); border-color: #fee2e2; }

        .badge { padding: 4px 12px; border-radius: 20px; font-size: 12px; font-weight: bold; color: white; }
        .badge-op { background-color: var(--accent-green); }
        .badge-admin { background-color: var(--accent-red); }

        /* 대시보드 상단 4종 요약 카드 */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 16px; margin-bottom: 20px;
        }
        @media (max-width: 900px) { .stats-grid { grid-template-columns: repeat(2, 1fr); } }
        
        .stats-card {
            background: var(--card-bg); padding: 20px; border-radius: 12px;
            border: 1px solid var(--border-color); box-shadow: 0 1px 3px rgba(0,0,0,0.01);
        }
        .stats-card .stats-label { font-size: 12px; color: var(--text-muted); font-weight: 600; }
        .stats-card .stats-value { font-size: 28px; font-weight: 800; margin: 8px 0 4px 0; }
        .stats-card .stats-desc { font-size: 11px; color: #888; }

        /* 메인 분할 레이아웃 */
        .dashboard-body-layout {
            display: grid; grid-template-columns: 1fr 380px; gap: 20px;
        }
        @media (max-width: 1100px) { .dashboard-body-layout { grid-template-columns: 1fr; } }

        .left-main-stream { display: flex; flex-direction: column; gap: 20px; }

        /* 객실 현황 메인 그리드 바 */
        .panel-container {
            background: var(--card-bg); padding: 24px; border-radius: 12px;
            border: 1px solid var(--border-color);
        }
        .panel-header-title {
            font-size: 16px; font-weight: 700; margin-bottom: 20px;
            display: flex; justify-content: space-between; align-items: center;
        }

        .room-grid {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 16px;
        }
        
        .room-card {
            border: 1px solid var(--border-color); border-radius: 12px;
            padding: 20px; background: #ffffff; cursor: pointer;
            transition: all 0.2s; position: relative;
        }
        .room-card:hover, .room-card.selected {
            border-color: var(--accent-green); box-shadow: 0 4px 14px rgba(0,0,0,0.04);
        }
        .admin-view .room-card:hover, .admin-view .room-card.selected { border-color: var(--accent-red); }

        .room-card .room-title-num { font-size: 22px; font-weight: 800; }
        .room-card .status-tag {
            position: absolute; top: 20px; right: 20px; font-size: 11px;
            padding: 3px 8px; border-radius: 6px; background: #f3f4f6; color: #555; font-weight: 600;
        }
        .room-card.in-use { background: #fafbfa; }
        .room-card.in-use .status-tag { background: var(--accent-green); color: white; }
        
        .room-info-list { font-size: 13px; margin-top: 15px; display: flex; flex-direction: column; gap: 4px; }
        .room-info-list div { display: flex; justify-content: space-between; border-bottom: 1px dashed #f3f4f6; padding-bottom: 2px; }
        .room-info-list div span:first-child { color: var(--text-muted); }
        .room-info-list div span:last-child { font-weight: 600; }

        .card-inner-actions { display: flex; gap: 6px; margin-top: 15px; }
        .inner-btn {
            flex: 1; padding: 6px; font-size: 12px; font-weight: 500;
            border: 1px solid var(--border-color); background: white; border-radius: 6px; cursor: pointer;
        }
        .inner-btn:hover { background: #f9fafb; }

        /* 데이터 리스트 테이블 공통 스타일 */
        .data-table-wrapper { width: 100%; overflow-x: auto; margin-top: 10px; }
        .base-data-table { width: 100%; border-collapse: collapse; text-align: left; font-size: 13px; }
        .base-data-table th { background: #f9fafb; padding: 12px; font-weight: 600; border-bottom: 2px solid #edf2f7; color: #444; }
        .base-data-table td { padding: 14px 12px; border-bottom: 1px solid #edf2f7; color: #333; }
        .table-btn-end { padding: 4px 10px; border: 1px solid #fee2e2; background: #fef2f2; color: var(--accent-red); border-radius: 4px; font-weight: bold; cursor: pointer; }

        /* 우측 정밀 제어 및 결제 정산 사이드바 */
        .right-control-sidebar {
            background: var(--card-bg); padding: 24px; border-radius: 12px;
            border: 1px solid var(--border-color); display: flex; flex-direction: column; gap: 22px;
            align-self: start;
        }
        
        .section-block-title { font-size: 15px; font-weight: 700; padding-bottom: 8px; border-bottom: 2px solid #f3f4f6; }
        .focus-room-title { font-size: 26px; font-weight: 800; color: var(--accent-green); }
        .admin-view .focus-room-title { color: var(--accent-red); }

        .form-row { margin-bottom: 12px; }
        .form-row label { display: block; font-size: 12px; font-weight: 600; color: var(--text-muted); margin-bottom: 6px; }
        .form-row input, .form-row select { width: 100%; padding: 10px; border: 1px solid var(--border-color); border-radius: 6px; font-size: 14px; }
        
        /* 결제 방식 선택 그리드 버튼 */
        .pay-method-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 6px; margin-top: 6px; }
        .method-btn {
            padding: 8px; font-size: 12px; font-weight: bold; border: 1px solid var(--border-color);
            background: #fff; border-radius: 6px; cursor: pointer; text-align: center;
        }
        .method-btn.selected { background: #f5f6f2; border-color: var(--accent-green); color: var(--accent-green); }
        .admin-view .method-btn.selected { background: #fef2f2; border-color: var(--accent-red); color: var(--accent-red); }

        /* 달력 배치 하우징 */
        .embed-calendar-box { background: #fff; border: 1px solid var(--border-color); border-radius: 8px; padding: 8px; }

        /* 최종 요금 노출 박스 */
        .total-amount-display-card {
            background: #fbfbfa; border: 1px solid #e9ebe4; padding: 15px;
            border-radius: 8px; text-align: center; margin-top: 5px;
        }
        .total-amount-display-card .amt-label { font-size: 12px; color: var(--text-muted); }
        .total-amount-display-card .amt-val { font-size: 22px; font-weight: 800; color: #111; margin-top: 4px; }

        .submit-large-btn {
            width: 100%; padding: 15px; background: var(--accent-green); color: white;
            border: none; border-radius: 8px; font-size: 15px; font-weight: bold; cursor: pointer;
        }
        .submit-large-btn:hover { background: var(--accent-green-hover); }
        .admin-view .submit-large-btn { background: var(--accent-red); }

        .term-info-desc { font-size: 11px; color: #999; text-align: center; line-height: 1.5; }
    </style>
</head>
<body>

    <div id="gateway-root" class="gateway-container">
        <div class="gateway-header">
            <h1>HOTEL CORDELIA</h1>
            <p>객실 및 시설 통합 관리 시스템</p>
        </div>
        
        <div class="mode-btn-group">
            <button id="gate-op-btn" class="mode-btn active-op" onclick="toggleGateTab('op')">운영 화면</button>
            <button id="gate-admin-btn" class="mode-btn" onclick="toggleGateTab('admin')">관리자 대시보드</button>
        </div>

        <div class="pin-box">
            <input type="password" id="sys-pincode" placeholder="PIN 번호 입력" maxlength="4" autocomplete="off">
            <div id="sys-auth-error" class="error-msg">비밀번호 권한 불일치 (운영:0220 / 관리자:0880)</div>
        </div>

        <button class="submit-large-btn" style="padding:12px;" onclick="executeLogin()">시스템 안전 접속</button>
        <button class="bypass-btn" onclick="bypassDirectAuth()">[보안 우회하여 대시보드 즉시 확인]</button>
    </div>


    <div id="dashboard-app-root" class="app-container">
        
        <div class="app-top-bar">
            <div class="brand-title">
                <h2>객실 및 투숙 관리 시스템</h2>
                <p>투숙객 입실 처리, 실시간 예약 현황 관리, 이용 종료 및 객실 정산을 관리합니다.</p>
            </div>
            <div class="top-bar-actions">
                <button class="top-btn" onclick="alert('사용자 투숙 현황 보드와 동기화되었습니다.')">사용자 화면</button>
                <button class="top-btn" onclick="location.reload();">🔄 새로고침</button>
                <button class="top-btn" style="color:var(--accent-red);" onclick="location.reload();">🔄 전체 초기화</button>
                <span id="authority-badge" class="badge badge-op">운영 모드</span>
                <button class="top-btn btn-danger" onclick="location.reload();">로그아웃</button>
            </div>
        </div>

        <div class="stats-grid">
            <div class="stats-card">
                <div class="stats-label">재실/운영중</div>
                <div class="stats-value" style="color: var(--accent-green);">1 실</div>
                <div class="stats-desc">현재 투숙객이 이용 중인 객실</div>
            </div>
            <div class="stats-card">
                <div class="stats-label">예약가능 (공실)</div>
                <div class="stats-value" id="avail-rooms-counter" style="color: #4b5563;">7 실</div>
                <div class="stats-desc">즉시 체크인 및 당일 배정 가능한 객실</div>
            </div>
            <div class="stats-card">
                <div class="stats-label">정비/점검 필요</div>
                <div class="stats-value" style="color: #d97706;">0 실</div>
                <div class="stats-desc">퇴실 후 청소 점검 또는 대기 중인 상태</div>
            </div>
            <div class="stats-card">
                <div class="stats-label">오늘 정산 매출</div>
                <div class="stats-value" id="today-revenue-display">0 원</div>
                <div class="stats-desc">금일 정산 완료된 숙박/이용 총 누적 금액</div>
            </div>
        </div>

        <div class="dashboard-body-layout" id="style-visual-root">
            
            <div class="left-main-stream">
                
                <div class="panel-container">
                    <div class="panel-header-title">
                        <span>객실 투숙 현황</span>
                        <span style="font-size:13px; font-weight:normal; color:var(--text-muted);" id="total-rooms-lbl">총 8개 객실</span>
                    </div>
                    
                    <div class="room-grid">
                        <div class="room-card selected" id="room-101" onclick="focusActiveRoom('101')">
                            <div class="room-title-num">101호</div>
                            <span class="status-tag">예약가능</span>
                            <div class="room-info-list">
                                <div><span>투숙 기간</span><span>-</span></div>
                                <div><span>연락처</span><span>-</span></div>
                                <div><span>숙박 요금</span><span>0원</span></div>
                            </div>
                            <div class="card-inner-actions admin-only-block">
                                <button class="inner-btn">공실 전환</button>
                                <button class="inner-btn">정비중 지정</button>
                            </div>
                        </div>

                        <div class="room-card" id="room-102" onclick="focusActiveRoom('102')">
                            <div class="room-title-num">102호</div>
                            <span class="status-tag">예약가능</span>
                            <div class="room-info-list">
                                <div><span>투숙 기간</span><span>-</span></div>
                                <div><span>연락처</span><span>-</span></div>
                                <div><span>숙박 요금</span><span>0원</span></div>
                            </div>
                            <div class="card-inner-actions admin-only-block">
                                <button class="inner-btn">공실 전환</button>
                                <button class="inner-btn">정비중 지정</button>
                            </div>
                        </div>

                        <div class="room-card in-use" id="room-103" onclick="focusActiveRoom('103')">
                            <div class="room-title-num">103호</div>
                            <span class="status-tag">이용중</span>
                            <div class="room-info-list">
                                <div><span>투숙 기간</span><span>일 단위 정산 대기</span></div>
                                <div><span>연락처</span><span>010-****-0220</span></div>
                                <div><span>숙박 요금</span><span>0원</span></div>
                            </div>
                            <div class="card-inner-actions admin-only-block">
                                <button class="inner-btn" style="color:var(--accent-red); font-weight:bold;">퇴실 처리</button>
                                <button class="inner-btn">정비중 지정</button>
                            </div>
                        </div>

                        <div class="room-card" id="room-104" onclick="focusActiveRoom('104')">
                            <div class="room-title-num">104호</div>
                            <span class="status-tag">예약가능</span>
                            <div class="room-info-list">
                                <div><span>투숙 기간</span><span>-</span></div>
                                <div><span>연락처</span><span>-</span></div>
                                <div><span>숙박 요금</span><span>0원</span></div>
                            </div>
                            <div class="card-inner-actions admin-only-block">
                                <button class="inner-btn">공실 전환</button>
                                <button class="inner-btn">정비중 지정</button>
                            </div>
                        </div>

                        <div class="room-card" id="room-105" onclick="focusActiveRoom('105')">
                            <div class="room-title-num">105호</div>
                            <span class="status-tag">예약가능</span>
                            <div class="room-info-list">
                                <div><span>투숙 기간</span><span>-</span></div>
                                <div><span>연락처</span><span>-</span></div>
                                <div><span>숙박 요금</span><span>0원</span></div>
                            </div>
                            <div class="card-inner-actions admin-only-block">
