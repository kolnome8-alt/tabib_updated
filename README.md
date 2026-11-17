<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0" />
  <title>نَبْض برو | حجز طبيبي وإدارة العيادات والمختبرات في العراق</title>
  <style>
    /* ================= DESIGN TOKENS & RESET ================= */
    :root {
      --bg-page: #f1f5f9;
      --bg-card: #ffffff;
      --bg-subtle: #f8fafc;
      --navy-dark: #0f172a;
      --navy-mid: #1e293b;
      --teal-primary: #0d9488;
      --teal-dark: #0f766e;
      --teal-light: #ccfbf1;
      --teal-soft: #f0fdfa;
      --emerald: #059669;
      --emerald-soft: #ecfdf5;
      --amber: #d97706;
      --amber-soft: #fffbeb;
      --rose: #e11d48;
      --rose-soft: #fff1f2;
      --indigo: #4f46e5;
      --indigo-soft: #eef2ff;
      --text-main: #0f172a;
      --text-muted: #64748b;
      --border-color: #e2e8f0;
      --shadow-sm: 0 2px 8px rgba(15, 23, 42, 0.05);
      --shadow-md: 0 8px 24px rgba(15, 23, 42, 0.08);
      --shadow-lg: 0 18px 40px rgba(15, 23, 42, 0.16);
      --radius-md: 12px;
      --radius-lg: 18px;
      --radius-xl: 24px;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      -webkit-tap-highlight-color: transparent;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Tahoma, Arial, sans-serif;
      background-color: var(--bg-page);
      color: var(--text-main);
      line-height: 1.6;
      direction: rtl;
      overflow-x: hidden;
      padding-bottom: 44px;
    }

    button, input, select, textarea {
      font-family: inherit;
    }

    .hidden {
      display: none !important;
    }

    /* ================= TOP HEADER ================= */
    .app-header {
      position: sticky;
      top: 0;
      z-index: 40;
      background: linear-gradient(135deg, var(--navy-dark) 0%, #134e4a 100%);
      color: #ffffff;
      padding: 12px 16px;
      box-shadow: var(--shadow-md);
    }

    .header-inner {
      max-width: 1280px;
      margin: 0 auto;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
    }

    .brand-box {
      display: flex;
      align-items: center;
      gap: 10px;
      cursor: pointer;
      user-select: none;
    }

    .brand-logo {
      width: 42px;
      height: 42px;
      border-radius: 13px;
      background: linear-gradient(135deg, #14b8a6, #059669);
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 4px 12px rgba(20, 184, 166, 0.35);
      flex-shrink: 0;
    }

    .brand-title {
      font-size: 18px;
      font-weight: 800;
      letter-spacing: -0.3px;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .brand-badge {
      font-size: 10px;
      font-weight: 700;
      background: rgba(255, 255, 255, 0.16);
      color: #99f6e4;
      padding: 2px 8px;
      border-radius: 99px;
      border: 1px solid rgba(153, 246, 228, 0.3);
    }

    .brand-sub {
      font-size: 11px;
      color: #cbd5e1;
      display: block;
    }

    .header-actions {
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .btn-header-pill {
      background: rgba(255, 255, 255, 0.12);
      color: #ffffff;
      border: 1px solid rgba(255, 255, 255, 0.2);
      padding: 8px 12px;
      border-radius: 12px;
      font-size: 12px;
      font-weight: 700;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      transition: 0.2s;
    }

    .btn-header-pill:hover {
      background: rgba(255, 255, 255, 0.22);
    }

    .btn-secret-shield {
      width: 34px;
      height: 34px;
      border-radius: 10px;
      background: rgba(255, 255, 255, 0.06);
      border: 1px solid rgba(255, 255, 255, 0.1);
      color: rgba(255, 255, 255, 0.45);
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      transition: 0.2s;
    }

    .btn-secret-shield:hover {
      color: #5eead4;
      background: rgba(255, 255, 255, 0.14);
    }

    /* ================= MAIN CONTAINER & NAV TABS ================= */
    .main-container {
      max-width: 1280px;
      margin: 0 auto;
      padding: 16px;
    }

    .nav-tabs-bar {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-lg);
      padding: 6px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 6px;
      box-shadow: var(--shadow-sm);
      margin-bottom: 16px;
    }

    .tab-btn {
      border: none;
      background: transparent;
      color: var(--text-muted);
      padding: 11px 8px;
      border-radius: 13px;
      font-size: 12.5px;
      font-weight: 800;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      transition: all 0.2s ease;
      text-align: center;
      position: relative;
    }

    .tab-btn.active {
      background: linear-gradient(135deg, var(--teal-primary), var(--teal-dark));
      color: #ffffff;
      box-shadow: 0 4px 12px rgba(13, 148, 136, 0.28);
    }

    .nav-counter-dot {
      background: var(--rose);
      color: #fff;
      font-size: 10px;
      font-weight: 900;
      padding: 1px 6px;
      border-radius: 99px;
    }

    /* ================= AD BANNER CAROUSEL ================= */
    .ad-carousel-wrap {
      position: relative;
      border-radius: var(--radius-xl);
      overflow: hidden;
      margin-bottom: 16px;
      box-shadow: var(--shadow-md);
      background: linear-gradient(135deg, #1e1b4b 0%, #0f766e 100%);
      color: #ffffff;
      border: 1px solid rgba(255, 255, 255, 0.14);
    }

    .ad-slide {
      padding: 18px 20px;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 14px;
      min-height: 118px;
      transition: opacity 0.35s ease;
    }

    .ad-tag {
      display: inline-flex;
      align-items: center;
      gap: 5px;
      background: rgba(251, 191, 36, 0.22);
      color: #fde68a;
      border: 1px solid rgba(251, 191, 36, 0.45);
      font-size: 11px;
      font-weight: 800;
      padding: 3px 10px;
      border-radius: 99px;
      margin-bottom: 6px;
    }

    .ad-controls {
      display: flex;
      align-items: center;
      justify-content: space-between;
      background: rgba(15, 23, 42, 0.32);
      padding: 6px 14px;
    }

    .ad-dots {
      display: flex;
      gap: 6px;
    }

    .ad-dot {
      width: 8px;
      height: 8px;
      border-radius: 99px;
      background: rgba(255, 255, 255, 0.35);
      cursor: pointer;
      transition: 0.25s;
    }

    .ad-dot.active {
      width: 22px;
      background: #5eead4;
    }

    .ad-nav-btn {
      background: rgba(255, 255, 255, 0.15);
      border: none;
      color: #fff;
      width: 26px;
      height: 26px;
      border-radius: 8px;
      cursor: pointer;
      font-weight: 900;
    }

    /* ================= CATEGORY SEGMENT BAR ================= */
    .category-bar {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 8px;
      margin-bottom: 14px;
    }

    .cat-btn {
      background: #ffffff;
      border: 1.5px solid var(--border-color);
      border-radius: 14px;
      padding: 10px 6px;
      font-size: 12px;
      font-weight: 800;
      color: var(--navy-mid);
      cursor: pointer;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 4px;
      transition: 0.2s;
      box-shadow: var(--shadow-sm);
    }

    .cat-btn.active {
      border-color: var(--teal-primary);
      background: var(--teal-soft);
      color: var(--teal-dark);
    }

    /* ================= HERO & SEARCH FILTER ================= */
    .hero-banner {
      background: linear-gradient(135deg, #0f172a 0%, #0f766e 100%);
      color: #ffffff;
      border-radius: var(--radius-xl);
      padding: 20px 18px;
      margin-bottom: 16px;
      box-shadow: var(--shadow-md);
    }

    .hero-banner h2 {
      font-size: 19px;
      font-weight: 800;
      margin-bottom: 4px;
    }

    .hero-banner p {
      font-size: 12.5px;
      color: #cbd5e1;
      margin-bottom: 14px;
    }

    .search-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 9px;
      background: rgba(255, 255, 255, 0.1);
      padding: 11px;
      border-radius: var(--radius-lg);
      border: 1px solid rgba(255, 255, 255, 0.15);
    }

    @media (min-width: 768px) {
      .search-grid {
        grid-template-columns: 1fr 1fr 1fr 1.2fr auto;
      }
      .hero-banner h2 {
        font-size: 23px;
      }
    }

    .form-control {
      width: 100%;
      padding: 10px 13px;
      border-radius: 12px;
      border: 1px solid var(--border-color);
      background: #ffffff;
      color: var(--text-main);
      font-size: 13px;
      font-weight: 600;
      outline: none;
      transition: border-color 0.2s;
    }

    .form-control:focus {
      border-color: var(--teal-primary);
      box-shadow: 0 0 0 3px rgba(13, 148, 136, 0.15);
    }

    /* Specialty Quick Pills */
    .pills-row {
      display: flex;
      gap: 8px;
      overflow-x: auto;
      padding-bottom: 8px;
      margin-bottom: 14px;
      scrollbar-width: none;
    }

    .pills-row::-webkit-scrollbar {
      display: none;
    }

    .spec-pill {
      white-space: nowrap;
      padding: 7px 14px;
      border-radius: 99px;
      border: 1px solid var(--border-color);
      background: #ffffff;
      color: var(--navy-mid);
      font-size: 12px;
      font-weight: 700;
      cursor: pointer;
      transition: 0.2s;
    }

    .spec-pill.active, .spec-pill:hover {
      background: var(--teal-primary);
      color: #ffffff;
      border-color: var(--teal-primary);
    }

    /* ================= DOCTORS / LABS / SONAR CARDS GRID ================= */
    .section-header {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 8px;
      margin-bottom: 14px;
    }

    .section-title {
      font-size: 16px;
      font-weight: 800;
      color: var(--navy-dark);
    }

    .doctors-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 14px;
    }

    @media (min-width: 768px) {
      .doctors-grid {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    @media (min-width: 1080px) {
      .doctors-grid {
        grid-template-columns: repeat(3, 1fr);
      }
    }

    .doc-card {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-lg);
      padding: 16px;
      box-shadow: var(--shadow-sm);
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      transition: transform 0.2s, box-shadow 0.2s;
      position: relative;
    }

    .doc-card:hover {
      transform: translateY(-2px);
      box-shadow: var(--shadow-md);
      border-color: #99f6e4;
    }

    .discount-ribbon {
      position: absolute;
      top: 12px;
      left: 12px;
      background: linear-gradient(135deg, #e11d48, #be123c);
      color: #ffffff;
      font-size: 11px;
      font-weight: 900;
      padding: 3px 9px;
      border-radius: 99px;
      box-shadow: 0 3px 10px rgba(225, 29, 72, 0.3);
    }

    .doc-top {
      display: flex;
      gap: 12px;
      align-items: flex-start;
    }

    .doc-avatar {
      width: 54px;
      height: 54px;
      border-radius: 16px;
      background: linear-gradient(135deg, var(--teal-soft), #ccfbf1);
      color: var(--teal-dark);
      border: 1.5px solid #99f6e4;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      font-weight: 800;
      flex-shrink: 0;
    }

    .doc-meta-top {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 6px;
      margin-bottom: 4px;
    }

    .badge-spec {
      background: var(--teal-soft);
      color: var(--teal-dark);
      border: 1px solid #99f6e4;
      font-size: 11px;
      font-weight: 800;
      padding: 2px 8px;
      border-radius: 8px;
    }

    .badge-cat {
      background: var(--indigo-soft);
      color: #3730a3;
      border: 1px solid #c7d2fe;
      font-size: 10.5px;
      font-weight: 800;
      padding: 2px 7px;
      border-radius: 8px;
    }

    .badge-rating {
      color: #d97706;
      font-size: 12px;
      font-weight: 800;
    }

    .doc-name {
      font-size: 16px;
      font-weight: 800;
      color: var(--navy-dark);
    }

    .doc-title {
      font-size: 12px;
      color: var(--text-muted);
      margin-top: 2px;
    }

    .doc-details {
      margin: 12px 0;
      padding: 10px 0;
      border-top: 1px dashed var(--border-color);
      border-bottom: 1px dashed var(--border-color);
      display: flex;
      flex-direction: column;
      gap: 6px;
      font-size: 12px;
    }

    .doc-detail-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 8px;
      color: #334155;
    }

    .work-days-badges {
      display: flex;
      flex-wrap: wrap;
      gap: 4px;
      margin-top: 2px;
    }

    .day-chip {
      font-size: 10px;
      font-weight: 700;
      padding: 2px 7px;
      border-radius: 6px;
      background: #f1f5f9;
      color: #334155;
      border: 1px solid #e2e8f0;
    }

    .doc-bottom {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
    }

    .next-slot-box {
      background: var(--emerald-soft);
      border: 1px solid #a7f3d0;
      padding: 6px 10px;
      border-radius: 10px;
    }

    .next-slot-box span {
      display: block;
      font-size: 10px;
      color: var(--emerald);
      font-weight: 700;
    }

    .next-slot-box strong {
      font-size: 11.5px;
      color: #064e3b;
      font-weight: 800;
    }

    /* ================= BUTTONS ================= */
    .btn {
      border: none;
      border-radius: 12px;
      padding: 10px 16px;
      font-size: 13px;
      font-weight: 800;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      transition: 0.2s;
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--teal-primary), var(--teal-dark));
      color: #ffffff;
      box-shadow: 0 4px 12px rgba(13, 148, 136, 0.25);
    }

    .btn-primary:hover {
      filter: brightness(1.06);
    }

    .btn-dark {
      background: var(--navy-dark);
      color: #ffffff;
    }

    .btn-dark:hover {
      background: var(--teal-dark);
    }

    .btn-emerald {
      background: var(--emerald);
      color: #ffffff;
    }

    .btn-rose {
      background: var(--rose);
      color: #ffffff;
    }

    .btn-amber {
      background: var(--amber-soft);
      color: #92400e;
      border: 1px solid #fde68a;
    }

    .btn-indigo {
      background: var(--indigo);
      color: #ffffff;
    }

    .btn-outline {
      background: #ffffff;
      color: var(--navy-dark);
      border: 1px solid var(--border-color);
    }

    .btn-sm {
      padding: 7px 11px;
      font-size: 11.5px;
      border-radius: 10px;
    }

    .btn-block {
      width: 100%;
    }

    /* ================= STATS STRIP ================= */
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 10px;
      margin-bottom: 16px;
    }

    @media (min-width: 768px) {
      .stats-grid {
        grid-template-columns: repeat(4, 1fr);
      }
    }

    .stat-card {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-lg);
      padding: 14px;
      box-shadow: var(--shadow-sm);
    }

    .stat-card span {
      display: block;
      font-size: 11.5px;
      color: var(--text-muted);
      font-weight: 700;
    }

    .stat-card strong {
      display: block;
      font-size: 19px;
      font-weight: 800;
      color: var(--navy-dark);
      margin-top: 4px;
    }

    /* ================= CARDS & TABLES ================= */
    .panel-card {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-lg);
      padding: 16px;
      box-shadow: var(--shadow-sm);
      margin-bottom: 16px;
    }

    .table-wrap {
      overflow-x: auto;
      border-radius: 12px;
      border: 1px solid var(--border-color);
    }

    table {
      width: 100%;
      border-collapse: collapse;
      min-width: 760px;
      font-size: 12.5px;
    }

    th {
      background: var(--bg-subtle);
      color: var(--text-muted);
      font-weight: 800;
      text-align: right;
      padding: 12px;
      border-bottom: 1px solid var(--border-color);
    }

    td {
      padding: 12px;
      border-bottom: 1px solid var(--border-color);
      vertical-align: middle;
    }

    tr:last-child td {
      border-bottom: none;
    }

    .badge-pill {
      display: inline-flex;
      align-items: center;
      gap: 4px;
      padding: 4px 10px;
      border-radius: 99px;
      font-size: 11px;
      font-weight: 800;
    }

    .badge-green { background: var(--emerald-soft); color: #065f46; border: 1px solid #a7f3d0; }
    .badge-amber { background: var(--amber-soft); color: #92400e; border: 1px solid #fde68a; }
    .badge-indigo { background: var(--indigo-soft); color: #3730a3; border: 1px solid #c7d2fe; }
    .badge-rose { background: var(--rose-soft); color: #9f1239; border: 1px solid #fecdd3; }
    .badge-gray { background: #f1f5f9; color: #475569; }

    /* ================= DOCTOR WORKSPACE (EMR) ================= */
    .emr-layout {
      display: grid;
      grid-template-columns: 1fr;
      gap: 16px;
    }

    @media (min-width: 960px) {
      .emr-layout {
        grid-template-columns: 340px 1fr;
      }
    }

    .queue-item {
      padding: 12px;
      border-radius: 14px;
      border: 1.5px solid var(--border-color);
      background: #ffffff;
      margin-bottom: 10px;
      cursor: pointer;
      transition: 0.2s;
    }

    .queue-item.active {
      border-color: var(--teal-primary);
      background: var(--teal-soft);
    }

    .allergy-alert {
      background: var(--rose-soft);
      border: 1.5px solid #fda4af;
      color: #881337;
      padding: 12px 14px;
      border-radius: 14px;
      font-size: 13px;
      font-weight: 800;
      margin-bottom: 14px;
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .vitals-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 10px;
      margin-bottom: 14px;
    }

    @media (min-width: 600px) {
      .vitals-grid {
        grid-template-columns: repeat(4, 1fr);
      }
    }

    .vital-box {
      background: var(--bg-subtle);
      border: 1px solid var(--border-color);
      border-radius: 12px;
      padding: 10px;
      text-align: center;
    }

    .vital-box span {
      font-size: 11px;
      color: var(--text-muted);
      display: block;
    }

    .vital-box strong {
      font-size: 15px;
      color: var(--navy-dark);
      font-weight: 800;
    }

    .rx-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      background: var(--bg-subtle);
      border: 1px solid var(--border-color);
      padding: 10px 12px;
      border-radius: 12px;
      margin-bottom: 8px;
    }

    /* ================= MODALS & DIGITAL TICKET ================= */
    .modal-backdrop {
      position: fixed;
      inset: 0;
      z-index: 60;
      background: rgba(15, 23, 42, 0.8);
      backdrop-filter: blur(5px);
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 14px;
      overflow-y: auto;
    }

    .modal-box {
      background: #ffffff;
      width: 100%;
      max-width: 500px;
      border-radius: var(--radius-xl);
      overflow: hidden;
      box-shadow: var(--shadow-lg);
      animation: popIn 0.2s ease-out;
      max-height: 92vh;
      overflow-y: auto;
    }

    @keyframes popIn {
      from { transform: scale(0.95); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    .modal-header {
      background: linear-gradient(135deg, var(--navy-dark), #134e4a);
      color: #ffffff;
      padding: 15px 18px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .modal-body {
      padding: 18px;
    }

    .form-group {
      margin-bottom: 12px;
    }

    .form-label {
      display: block;
      font-size: 12px;
      font-weight: 800;
      color: #334155;
      margin-bottom: 5px;
    }

    .days-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 8px;
    }

    .slots-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 8px;
    }

    .slot-btn {
      padding: 9px 6px;
      border-radius: 10px;
      border: 1.5px solid var(--border-color);
      background: #ffffff;
      font-size: 11.5px;
      font-weight: 800;
      cursor: pointer;
      text-align: center;
    }

    .slot-btn.selected {
      background: var(--teal-primary);
      color: #ffffff;
      border-color: var(--teal-primary);
    }

    .slot-btn:disabled {
      background: #f1f5f9;
      color: #94a3b8;
      text-decoration: line-through;
      cursor: not-allowed;
    }

    .pay-methods-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 8px;
    }

    .pay-option {
      border: 2px solid var(--border-color);
      border-radius: 12px;
      padding: 10px;
      text-align: center;
      cursor: pointer;
      font-size: 12px;
      font-weight: 800;
      background: #ffffff;
    }

    .pay-option.selected {
      border-color: var(--teal-primary);
      background: var(--teal-soft);
      color: var(--teal-dark);
    }

    /* Digital Ticket Styling */
    .ticket-card {
      background: linear-gradient(180deg, #ffffff 0%, #f8fafc 100%);
      border: 2px dashed #0d9488;
      border-radius: 20px;
      padding: 16px;
      position: relative;
    }

    .ticket-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px dashed #cbd5e1;
      padding-bottom: 12px;
      margin-bottom: 12px;
    }

    .ticket-row {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      gap: 10px;
      font-size: 12.5px;
      padding: 5px 0;
    }

    .ticket-row span {
      color: var(--text-muted);
      white-space: nowrap;
    }

    .ticket-row strong {
      color: var(--navy-dark);
      text-align: left;
    }

    .qr-box {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background: #ffffff;
      border: 1px solid var(--border-color);
      border-radius: 14px;
      padding: 10px;
      margin-top: 10px;
    }

    /* ================= ADMIN PANEL ================= */
    .admin-banner {
      background: linear-gradient(135deg, #0f172a, #1e293b);
      color: #ffffff;
      border-radius: var(--radius-lg);
      padding: 16px;
      margin-bottom: 16px;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      border: 1px solid #334155;
    }

    .admin-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 16px;
    }

    @media (min-width: 960px) {
      .admin-grid {
        grid-template-columns: 440px 1fr;
      }
    }

    .admin-doc-row {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      padding: 12px;
      border: 1px solid var(--border-color);
      border-radius: 14px;
      background: var(--bg-subtle);
      margin-bottom: 10px;
    }

    .admin-doc-row.suspended {
      opacity: 0.72;
      background: #fff1f2;
      border-color: #fecdd3;
    }

    .label-with-edit {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 6px;
      margin-bottom: 5px;
    }

    .label-with-edit .form-label {
      margin-bottom: 0;
    }

    .btn-pencil-edit {
      background: var(--amber-soft);
      color: #92400e;
      border: 1px solid #fde68a;
      border-radius: 8px;
      padding: 2px 7px;
      font-size: 11px;
      font-weight: 800;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 3px;
      transition: 0.2s;
    }

    .btn-pencil-edit:hover {
      background: #fde68a;
    }

    .days-picker-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 6px;
    }

    .day-toggle-btn {
      padding: 7px 4px;
      border-radius: 9px;
      border: 1px solid var(--border-color);
      background: #ffffff;
      font-size: 11px;
      font-weight: 800;
      cursor: pointer;
      text-align: center;
      color: var(--text-muted);
    }

    .day-toggle-btn.selected {
      background: var(--teal-primary);
      color: #ffffff;
      border-color: var(--teal-primary);
    }

    .taxonomy-item-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 8px;
      padding: 9px 10px;
      background: var(--bg-subtle);
      border: 1px solid var(--border-color);
      border-radius: 12px;
      margin-bottom: 8px;
    }

    .taxonomy-item-row input {
      flex: 1;
      padding: 6px 10px;
      border-radius: 8px;
      border: 1px solid var(--teal-primary);
      font-size: 12.5px;
      font-weight: 700;
    }

    /* ================= TOAST NOTIFICATION ================= */
    .toast-box {
      position: fixed;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 99;
      background: var(--navy-dark);
      color: #ffffff;
      padding: 12px 18px;
      border-radius: 14px;
      font-size: 13px;
      font-weight: 700;
      box-shadow: var(--shadow-lg);
      border: 1px solid rgba(255, 255, 255, 0.15);
      max-width: 92vw;
      text-align: center;
    }

    /* ================= FOOTER ================= */
    .app-footer {
      max-width: 1280px;
      margin: 24px auto 0;
      padding: 16px;
      border-top: 1px solid var(--border-color);
      display: flex;
      align-items: center;
      justify-content: space-between;
      font-size: 11.5px;
      color: var(--text-muted);
    }

    @media print {
      body * { visibility: hidden; }
      #printable-ticket-zone, #printable-ticket-zone * { visibility: visible; }
      #printable-ticket-zone {
        position: fixed;
        inset: 0;
        background: #ffffff;
        padding: 20px;
        z-index: 9999;
      }
      .no-print { display: none !important; }
    }
  </style>
</head>
<body>

  <!-- ================= HEADER ================= -->
  <header class="app-header">
    <div class="header-inner">
      <!-- Triple-Tap Secret Logo Trigger -->
      <div class="brand-box" onclick="handleLogoSecretTap()" title="نَبْض برو">
        <div class="brand-logo">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#ffffff" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round">
            <path d="M22 12h-4l-3 9L9 3l-3 9H2"/>
          </svg>
        </div>
        <div>
          <div class="brand-title">
            <span>نَبْض برو</span>
            <span class="brand-badge">كل العراق</span>
          </div>
          <span class="brand-sub">حجز الأطباء والمختبرات والسونار وإرسال فوري للسكرتير</span>
        </div>
      </div>

      <div class="header-actions">
        <button class="btn-header-pill" onclick="switchTab('booking')">
          <span>📅</span>
          <span>احجز الآن</span>
        </button>

        <!-- Discreet Shield Icon for Admin Passcode (808011) -->
        <button class="btn-secret-shield" onclick="openAdminAuthModal()" title="بوابة الإدارة">
          <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2">
            <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
          </svg>
        </button>
      </div>
    </div>
  </header>

  <!-- ================= MAIN CONTENT ================= -->
  <main class="main-container">

    <!-- Top Navigation Tabs (Admin Tab Completely Hidden until Unlocked) -->
    <nav class="nav-tabs-bar">
      <button id="nav-booking" class="tab-btn active" onclick="switchTab('booking')">
        <span>🏥</span>
        <span>بوابة الحجز</span>
      </button>
      <button id="nav-reception" class="tab-btn" onclick="switchTab('reception')">
        <span>🛎️</span>
        <span>لوحة السكرتير</span>
        <span id="nav-sec-badge" class="nav-counter-dot">0</span>
      </button>
      <button id="nav-doctor" class="tab-btn" onclick="switchTab('doctor')">
        <span>🩺</span>
        <span>غرفة الطبيب</span>
      </button>
    </nav>

    <!-- =================================================================== -->
    <!-- VIEW 1: PATIENT BOOKING PORTAL                                      -->
    <!-- =================================================================== -->
    <section id="view-booking">

      <!-- Dynamic Hospital & Doctors Ad Carousel -->
      <div id="ad-carousel" class="ad-carousel-wrap">
        <div id="ad-slide-content" class="ad-slide"></div>
        <div class="ad-controls">
          <button class="ad-nav-btn" onclick="prevAd()">›</button>
          <div id="ad-dots" class="ad-dots"></div>
          <button class="ad-nav-btn" onclick="nextAd()">‹</button>
        </div>
      </div>

      <!-- Category Tabs: All / Doctors / Labs / Sonar -->
      <div class="category-bar">
        <button class="cat-btn active" data-cat="all" onclick="selectCategory(this, 'all')">
          <span>✨</span>
          <span>الكل</span>
        </button>
        <button class="cat-btn" data-cat="أطباء" onclick="selectCategory(this, 'أطباء')">
          <span>👨‍⚕️</span>
          <span>الأطباء</span>
        </button>
        <button class="cat-btn" data-cat="مختبرات" onclick="selectCategory(this, 'مختبرات')">
          <span>🔬</span>
          <span>المختبرات</span>
        </button>
        <button class="cat-btn" data-cat="سونار وأشعة" onclick="selectCategory(this, 'سونار وأشعة')">
          <span>📡</span>
          <span>السونار والأشعة</span>
        </button>
      </div>

      <div class="hero-banner">
        <h2>احجز موعدك الطبي في كل محافظات العراق ويصل فوراً للسكرتير</h2>
        <p>اختر المحافظة والمنطقة والتخصص، واستلم تذكرتك برمز QR مع إرسال تلقائي لواتساب سكرتير العيادة</p>

        <div class="search-grid">
          <select id="filter-gov" class="form-control" onchange="onPublicGovChange()"></select>
          <select id="filter-area" class="form-control" onchange="filterDoctors()"></select>
          <select id="filter-specialty" class="form-control" onchange="filterDoctors()"></select>
          <input id="filter-query" type="text" class="form-control" placeholder="ابحث باسم الطبيب، المختبر أو السونار..." oninput="filterDoctors()" />
          <button class="btn btn-primary" onclick="filterDoctors()">بحث</button>
        </div>
      </div>

      <!-- Quick Specialty Filter Pills -->
      <div class="pills-row" id="specialty-pills"></div>

      <div class="section-header">
        <h3 class="section-title">الجهات الطبية المتاحة للحجز (<span id="visible-docs-count">0</span>)</h3>
        <span style="font-size:12px; color:var(--teal-dark); font-weight:700;">رسم الخدمة: <strong id="public-fee-hint">2,000 د.ع</strong></span>
      </div>

      <div id="doctors-grid" class="doctors-grid"></div>
    </section>

    <!-- =================================================================== -->
    <!-- VIEW 2: RECEPTION & SECRETARY DESK (RECEIVES BOOKINGS INSTANTLY)    -->
    <!-- =================================================================== -->
    <section id="view-reception" class="hidden">
      <div class="stats-grid">
        <div class="stat-card">
          <span>إجمالي الحجوزات الواصلة</span>
          <strong id="rec-total">0</strong>
        </div>
        <div class="stat-card">
          <span>بانتظار الدخول للعيادة</span>
          <strong id="rec-waiting" style="color:var(--amber);">0</strong>
        </div>
        <div class="stat-card">
          <span>تم تأكيد الدفع</span>
          <strong id="rec-paid" style="color:var(--emerald);">0</strong>
        </div>
        <div class="stat-card">
          <span>صندوق السكرتير المحصّل</span>
          <strong id="rec-revenue" style="color:var(--teal-dark);">0 د.ع</strong>
        </div>
      </div>

      <div class="panel-card">
        <div class="section-header">
          <div>
            <h3 class="section-title">🛎️ شاشة السكرتير المباشرة (كل حجز ينزل هنا فوراً)</h3>
            <span style="font-size:11.5px; color:var(--text-muted);">فلتر حسب الطبيب أو شاهد جميع الحجوزات الواردة من التطبيق</span>
          </div>
          <div style="display:flex; flex-wrap:wrap; gap:8px; align-items:center;">
            <select id="rec-doc-filter" class="form-control" style="width:auto; min-width:190px;" onchange="renderReception()">
              <option value="all">جميع الأطباء والمختبرات</option>
            </select>
            <button class="btn btn-primary btn-sm" onclick="openWalkInModal()">+ إضافة مراجع حضوري</button>
          </div>
        </div>

        <div class="table-wrap">
          <table>
            <thead>
              <tr>
                <th>التذكرة والتسلسل</th>
                <th>المريض ورقم هاتفه</th>
                <th>الطبيب / المختبر</th>
                <th>اليوم والتاريخ والساعة</th>
                <th>المبلغ وطريقة الدفع</th>
                <th>حالة الدفع</th>
                <th>إجراءات السكرتير</th>
              </tr>
            </thead>
            <tbody id="reception-tbody"></tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- =================================================================== -->
    <!-- VIEW 3: DOCTOR EXAMINATION & SMART EMR WORKSPACE                    -->
    <!-- =================================================================== -->
    <section id="view-doctor" class="hidden">
      <div class="emr-layout">
        <!-- Live Queue Column -->
        <div class="panel-card" style="height:fit-content;">
          <div class="section-header">
            <h3 class="section-title">طابور الانتظار المباشر</h3>
            <button class="btn btn-primary btn-sm" onclick="callNextPatient()">استدعاء التالي ⏭️</button>
          </div>
          <div id="doctor-queue-list"></div>
        </div>

        <!-- Active Patient Medical Record & Smart E-Prescription -->
        <div class="panel-card">
          <div style="display:flex; flex-wrap:wrap; justify-content:space-between; align-items:center; gap:10px; border-bottom:1px solid var(--border-color); padding-bottom:12px; margin-bottom:14px;">
            <div>
              <span class="badge-pill badge-green" style="margin-bottom:4px;">داخل غرفة الفحص الآن</span>
              <h3 id="emr-p-name" style="font-size:19px; font-weight:800;">علي محمود الكبيسي</h3>
              <p id="emr-p-meta" style="font-size:12.5px; color:var(--text-muted);">العمر: 46 سنة • ذكر • فصيلة الدم: O+ • تذكرة #NB-4081</p>
            </div>
            <button class="btn btn-dark btn-sm" onclick="previewPrescription()">🖨️ معاينة وطباعة الوصفة (QR)</button>
          </div>

          <!-- Allergy Alert Box -->
          <div id="emr-allergy-box" class="allergy-alert">
            <span>⚠️</span>
            <div>
              <div>تنبيه حساسية دوائية مسجلة: <span id="emr-allergy-text">حساسية البنسلين (Penicillin)</span></div>
              <small style="font-weight:600; opacity:0.85;">يقوم النظام بفحص التعارضات تلقائياً عند إضافة أي دواء للوصفة</small>
            </div>
          </div>

          <!-- Vitals -->
          <div class="vitals-grid">
            <div class="vital-box"><span>ضغط الدم (BP)</span><strong id="v-bp">135/85</strong></div>
            <div class="vital-box"><span>النبض (HR)</span><strong id="v-hr">78 bpm</strong></div>
            <div class="vital-box"><span>الحرارة (Temp)</span><strong id="v-temp">37.1 °C</strong></div>
            <div class="vital-box"><span>السكر (Sugar)</span><strong id="v-sugar">142 mg/dL</strong></div>
          </div>

          <!-- Clinical Notes -->
          <div class="form-group">
            <label class="form-label">الشكوى السريرية والتشخيص المبدئي</label>
            <textarea id="emr-symptoms" rows="2" class="form-control"></textarea>
          </div>

          <!-- Smart E-Prescription Builder -->
          <div style="background:var(--bg-subtle); border:1px solid var(--border-color); border-radius:16px; padding:14px; margin-top:14px;">
            <h4 style="font-size:14px; font-weight:800; margin-bottom:10px;">💊 الوصفة الإلكترونية الذكية (E-Prescription)</h4>

            <div style="display:grid; grid-template-columns:1fr; gap:8px; margin-bottom:12px;">
              <select id="rx-drug-select" class="form-control">
                <option value="Concor 5mg Tab|حبة واحدة صباحاً بعد الفطور|لمدة شهر">Concor 5mg Tab (علاج الضغط والقلب)</option>
                <option value="Augmentin 1g Tab (Penicillin)|حبة كل 12 ساعة بعد الطعام|7 أيام">Augmentin 1g Tab (مضاد حيوي - يحتوي بنسلين ⚠️)</option>
                <option value="Panadol Advance 500mg|حبتان عند الحاجة|5 أيام">Panadol Advance 500mg (مسكن وخافض حرارة)</option>
                <option value="Nexium 40mg Cap|كبسولة قبل الإفطار بنصف ساعة|14 يوم">Nexium 40mg Cap (حماية المعدة)</option>
                <option value="Aspirin Protect 100mg|حبة واحدة بعد الغداء|مستمر">Aspirin Protect 100mg (مميع للدم)</option>
                <option value="Lipitor 20mg Tab|حبة واحدة مساءً|لمدة شهر">Lipitor 20mg Tab (تنظيم الدهون)</option>
              </select>
              <button class="btn btn-primary btn-sm" onclick="addDrugToPrescription()">+ إضافة الدواء للوصفة وفحص التعارض</button>
            </div>

            <div id="emr-rx-list"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- =================================================================== -->
    <!-- VIEW 4: HIDDEN ADMIN CONTROL PANEL (UNLOCKED ONLY VIA 808011)       -->
    <!-- =================================================================== -->
    <section id="view-admin" class="hidden">
      <div class="admin-banner">
        <div>
          <span class="badge-pill badge-green" style="margin-bottom:6px;">🔐 وضع مدير المنصة مفعل (كود 808011)</span>
          <h2 style="font-size:18px; font-weight:800;">لوحة إدارة منصة نَبْض برو — كل العراق</h2>
          <p style="font-size:12px; color:#cbd5e1;">إدارة الأطباء والمختبرات والسكرتارية، الخصومات، أيام الدوام، الإعلانات، والنسخ الاحتياطي</p>
        </div>
        <div style="display:flex; flex-wrap:wrap; gap:8px;">
          <button class="btn btn-emerald btn-sm" onclick="exportBackupJSON()">💾 حفظ نسخة احتياطية (Backup)</button>
          <button class="btn btn-amber btn-sm" onclick="document.getElementById('backup-file-input').click()">📂 استعادة نسخة</button>
          <input id="backup-file-input" type="file" accept=".json" class="hidden" onchange="importBackupJSON(event)" />
          <button class="btn btn-rose btn-sm" onclick="lockAndExitAdmin()">🔒 قفل الإدارة</button>
        </div>
      </div>

      <!-- Google Sheets Live Sync Bar -->
      <div class="panel-card" style="background:var(--teal-soft); border:1.5px solid #5eead4;">
        <div class="section-header" style="margin-bottom:8px;">
          <h3 class="section-title" style="color:var(--teal-dark);">📊 رابط مزامنة Google Sheets المباشر (تحديث الأطباء والخصومات من موبايلك)</h3>
          <button class="btn btn-primary btn-sm" onclick="syncDoctorsFromGoogleSheet(true)">🔄 تحديث الآن من الشيت</button>
        </div>
        <div style="display:flex; flex-wrap:wrap; gap:8px;">
          <input id="admin-sheet-url-input" type="url" dir="ltr" class="form-control" style="flex:1; min-width:240px;" placeholder="https://script.google.com/macros/s/..../exec" />
          <button class="btn btn-dark btn-sm" onclick="saveSheetApiUrl()">💾 حفظ الرابط ومزامنة</button>
        </div>
      </div>

      <!-- Admin Stats & Service Fee Control -->
      <div class="stats-grid">
        <div class="stat-card">
          <span>رسم خدمة المنصة (د.ع)</span>
          <div style="display:flex; gap:6px; margin-top:8px;">
            <input id="admin-fee-input" type="number" step="500" min="0" class="form-control" value="2000" />
            <button class="btn btn-dark btn-sm" onclick="saveServiceFee()" style="white-space:nowrap;">حفظ</button>
          </div>
        </div>
        <div class="stat-card">
          <span>رقم التحويل الرسمي (ماستر / إلكتروني)</span>
          <div style="display:flex; gap:6px; margin-top:8px;">
            <input id="admin-transfer-num-input" type="text" dir="ltr" class="form-control" value="6760023637" style="font-weight:900; text-align:center;" />
            <button class="btn btn-indigo btn-sm" onclick="saveTransferNumber()" style="white-space:nowrap;">حفظ</button>
          </div>
        </div>
        <div class="stat-card">
          <span>أرباح المنصة من الرسوم</span>
          <strong id="admin-earnings" style="color:var(--emerald);">0 د.ع</strong>
        </div>
        <div class="stat-card">
          <span>الجهات الطبية النشطة</span>
          <strong id="admin-docs-count" style="color:var(--teal-dark);">0</strong>
        </div>
      </div>

      <div class="admin-grid">
        <!-- Add / Edit Doctor / Lab / Sonar Form -->
        <div class="panel-card" style="height:fit-content;">
          <div class="section-header">
            <h3 id="admin-form-heading" class="section-title">➕ إضافة طبيب / مختبر / سونار</h3>
            <button id="admin-cancel-edit" class="btn btn-outline btn-sm hidden" onclick="resetAdminForm()">إلغاء التعديل</button>
          </div>

          <input type="hidden" id="admin-edit-id" value="" />

          <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px;" class="form-group">
            <div>
              <label class="form-label">نوع الجهة الطبية *</label>
              <select id="adm-category" class="form-control">
                <option value="أطباء">👨‍⚕️ طبيب / عيادة</option>
                <option value="مختبرات">🔬 مختبر تحليلات</option>
                <option value="سونار وأشعة">📡 مركز سونار وأشعة</option>
              </select>
            </div>
            <div>
              <label class="form-label">حالة الاشتراك *</label>
              <select id="adm-active" class="form-control">
                <option value="true">🟢 مفعّل (يستقبل حجوزات)</option>
                <option value="false">🔴 متوقف (إيقاف مؤقت)</option>
              </select>
            </div>
          </div>

          <div class="form-group">
            <label class="form-label">اسم الطبيب أو المركز الطبي *</label>
            <input id="adm-name" type="text" class="form-control" placeholder="مثال: د. سيف الدين الكبيسي / مختبر النخبة" />
          </div>

          <div class="form-group">
            <label class="form-label">الشهادة والوصف العلمي *</label>
            <input id="adm-title" type="text" class="form-control" placeholder="مثال: استشاري جراحة الجملة العصبية" />
          </div>

          <div class="form-group">
            <div class="label-with-edit">
              <label class="form-label">التخصص الطبي</label>
              <button type="button" class="btn-pencil-edit" onclick="openTaxonomyModal('specialties')" title="تعديل قائمة التخصصات">✏️ تعديل</button>
            </div>
            <select id="adm-spec" class="form-control"></select>
          </div>

          <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px;" class="form-group">
            <div>
              <div class="label-with-edit">
                <label class="form-label">المحافظة</label>
                <button type="button" class="btn-pencil-edit" onclick="openTaxonomyModal('govs')" title="تعديل قائمة المحافظات">✏️ تعديل</button>
              </div>
              <select id="adm-gov" class="form-control" onchange="onAdminGovChange()"></select>
            </div>
            <div>
              <div class="label-with-edit">
                <label class="form-label">المنطقة / القضاء</label>
                <button type="button" class="btn-pencil-edit" onclick="openTaxonomyModal('areas')" title="تعديل مناطق هذه المحافظة">✏️ تعديل</button>
              </div>
              <select id="adm-area" class="form-control"></select>
            </div>
          </div>

          <div class="form-group">
            <label class="form-label">عنوان العيادة الدقيق وأقرب نقطة دالة *</label>
            <input id="adm-address" type="text" class="form-control" placeholder="مثال: بغداد - المنصور - شارع 14 رمضان..." />
          </div>

          <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px;" class="form-group">
            <div>
              <label class="form-label">سعر الكشفية (د.ع) *</label>
              <input id="adm-fee" type="number" step="5000" value="25000" class="form-control" />
            </div>
            <div>
              <label class="form-label">نسبة الخصم (%) للعيادة</label>
              <input id="adm-discount" type="number" min="0" max="90" step="5" value="0" class="form-control" placeholder="0" />
            </div>
          </div>

          <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px;" class="form-group">
            <div>
              <label class="form-label">رقم واتساب السكرتير (لإرسال الحجز كبل) *</label>
              <input id="adm-sec-phone" type="tel" value="0770 111 2233" class="form-control" placeholder="0770 000 0000" />
            </div>
            <div>
              <label class="form-label">ساعات الدوام</label>
              <input id="adm-hours" type="text" value="04:00 م - 08:30 م" class="form-control" />
            </div>
          </div>

          <div class="form-group">
            <label class="form-label">أيام الدوام الأسبوعية (اضغط للتحديد)</label>
            <div id="adm-days-picker" class="days-picker-grid"></div>
          </div>

          <button id="admin-submit-btn" class="btn btn-primary btn-block" onclick="saveDoctorAdmin()">نشر في المنصة فوراً</button>
        </div>

        <!-- Right Column: Doctors List + Ads Manager -->
        <div>
          <div class="panel-card">
            <div class="section-header">
              <h3 class="section-title">قائمة الأطباء والمختبرات (تعديل / إيقاف اشتراك / حذف)</h3>
              <span style="font-size:11.5px; color:var(--text-muted);">حفظ تلقائي</span>
            </div>
            <div id="admin-doctors-list"></div>
          </div>

          <!-- Hospital & Doctors Banner Ads Manager -->
          <div class="panel-card">
            <div class="section-header">
              <h3 class="section-title">📢 إدارة البنر الإعلاني المتحرك للمستشفيات والأطباء</h3>
            </div>
            <div style="display:grid; grid-template-columns:1fr; gap:8px; margin-bottom:12px;">
              <input id="ad-title-inp" type="text" class="form-control" placeholder="عنوان الإعلان (مثال: مستشفى الكفيل التخصصي - خصم 25%)" />
              <input id="ad-sub-inp" type="text" class="form-control" placeholder="وصف العرض أو رقم الحجز السريع..." />
              <button class="btn btn-indigo btn-sm" onclick="addNewAd()">+ إضافة إعلان للبنر المتحرك</button>
            </div>
            <div id="admin-ads-list"></div>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- ================= BOOKING WIZARD & DIGITAL TICKET MODAL ================= -->
  <div id="modal-booking" class="modal-backdrop hidden">
    <div class="modal-box">
      <div class="modal-header">
        <strong id="modal-booking-title">حجز موعد طبي إلكتروني</strong>
        <button onclick="closeModal('modal-booking')" style="background:none; border:none; color:#fff; font-size:20px; cursor:pointer;">✕</button>
      </div>

      <!-- STEP 1: BOOKING FORM -->
      <div id="booking-form-step" class="modal-body">
        <div style="background:var(--teal-soft); border:1px solid #99f6e4; border-radius:14px; padding:12px; margin-bottom:14px;">
          <strong id="wiz-doc-name" style="font-size:15px; display:block;">د. زيد المنصور</strong>
          <span id="wiz-doc-sub" style="font-size:12px; color:var(--teal-dark);">باطنية وقلبية • بغداد - الحارثية</span>
          <div id="wiz-fee-summary" style="margin-top:6px; font-size:12px; font-weight:800; color:var(--navy-dark);"></div>
        </div>

        <div class="form-group">
          <label class="form-label">1. اختر اليوم المتاح حسب دوام الطبيب</label>
          <div id="wiz-days" class="days-grid"></div>
        </div>

        <div class="form-group">
          <label class="form-label">2. اختر الساعة المناسبة</label>
          <div id="wiz-slots" class="slots-grid"></div>
        </div>

        <div class="form-group">
          <label class="form-label">3. اسم المريض الكامل *</label>
          <input id="wiz-p-name" type="text" class="form-control" placeholder="اكتب اسم المريض الثلاثي" />
        </div>

        <div class="form-group">
          <label class="form-label">4. رقم هاتف المريض (واتساب) *</label>
          <input id="wiz-p-phone" type="tel" class="form-control" placeholder="0770 000 0000" />
        </div>

        <div class="form-group">
          <label class="form-label">5. طريقة الدفع</label>
          <div class="pay-methods-grid">
            <div id="pay-opt-cash" class="pay-option selected" onclick="selectPaymentMethod('كاش للسكرتير')">
              💵 كاش للسكرتير
            </div>
            <div id="pay-opt-card" class="pay-option" onclick="selectPaymentMethod('تحويل إلكتروني / ماستر')">
              💳 تحويل إلكتروني / ماستر
            </div>
          </div>
        </div>

        <div id="card-input-box" class="form-group hidden">
          <!-- Mandatory Transfer Warning Box -->
          <div style="background:#fffbeb; border:2px solid #f59e0b; border-radius:14px; padding:12px; margin-bottom:10px; color:#78350f;">
            <div style="display:flex; align-items:center; gap:6px; font-weight:900; font-size:13px; color:#b45309; margin-bottom:6px;">
              <span>⚠️ تنبيه هام جداً للتحويل الإلكتروني:</span>
            </div>
            <p style="font-size:12px; font-weight:700; line-height:1.5; margin-bottom:8px;">
              يرجى تحويل مبلغ الرسم الإلكتروني (<strong id="wiz-transfer-fee-lbl" style="color:#be123c;">2,000 د.ع</strong>) إلى الرقم الرسمي التالي وإرفاق صورة التحويل أدناه؛ <u>لا يتم الحجز أو الإرسال للسكرتير بدون صورة التحويل</u>:
            </p>
            <div style="display:flex; align-items:center; justify-content:space-between; background:#ffffff; border:1.5px dashed #d97706; border-radius:10px; padding:8px 12px;">
              <strong id="wiz-transfer-number-display" dir="ltr" style="font-size:18px; font-weight:900; color:#0f172a; letter-spacing:1px;">6760023637</strong>
              <button type="button" class="btn btn-amber btn-sm" onclick="copyTransferNumber()">📋 نسخ الرقم</button>
            </div>
          </div>

          <label class="form-label" style="color:#be123c;">📸 إرفاق صورة إشعار التحويل (إجباري لإتمام الحجز) *</label>
          <input id="wiz-transfer-receipt" type="file" accept="image/*" class="form-control" onchange="handleReceiptUpload(event)" style="padding:8px;" />
          <div id="wiz-receipt-preview-wrap" class="hidden" style="margin-top:8px; text-align:center; background:#f8fafc; border:1px solid var(--border-color); border-radius:12px; padding:8px;">
            <span style="display:block; font-size:11px; font-weight:800; color:var(--emerald); margin-bottom:5px;">✅ تم إرفاق صورة التحويل بنجاح</span>
            <img id="wiz-receipt-preview-img" src="" alt="صورة التحويل" style="max-height:140px; max-width:100%; border-radius:8px; border:1px solid #cbd5e1;" />
          </div>
        </div>

        <div class="form-group" style="background:#f8fafc; border:1px solid var(--border-color); border-radius:12px; padding:9px 12px; display:flex; align-items:center; gap:8px;">
          <input id="wiz-auto-wa-sec" type="checkbox" checked style="width:17px; height:17px; accent-color:var(--teal-primary);" />
          <label for="wiz-auto-wa-sec" style="font-size:12px; font-weight:800; color:var(--navy-dark); cursor:pointer;">
            إرسال تفاصيل الحجز كبل (فوراً) إلى واتساب السكرتير بعد التأكيد
          </label>
        </div>

        <button class="btn btn-primary btn-block" onclick="confirmBooking()">تأكيد الحجز وإرساله للسكرتير فوراً 🚀</button>
      </div>

      <!-- STEP 2: DIGITAL TICKET PASS -->
      <div id="booking-ticket-step" class="modal-body hidden">
        <div style="background:var(--emerald-soft); border:1px solid #a7f3d0; color:#065f46; padding:9px 12px; border-radius:12px; font-size:12px; font-weight:800; margin-bottom:10px; text-align:center;">
          ✅ تم إرسال الحجز كبل إلى شاشة السكرتير ورقم واتساب العيادة!
        </div>

        <div id="printable-ticket-zone" class="ticket-card">
          <div class="ticket-top">
            <div>
              <span style="font-size:11px; color:var(--teal-dark); font-weight:800;">وصل حجز رسمي • منصة نَبْض برو</span>
              <h3 id="tkt-number" style="font-size:20px; font-weight:900; color:var(--navy-dark);">#NB-4095</h3>
            </div>
            <span id="tkt-queue" class="badge-pill badge-green" style="font-size:13px;">التسلسل #6</span>
          </div>

          <div class="ticket-row"><span>اسم المريض:</span><strong id="tkt-patient"></strong></div>
          <div class="ticket-row"><span>هاتف المريض:</span><strong id="tkt-p-phone" dir="ltr"></strong></div>
          <div class="ticket-row"><span>الجهة / الطبيب:</span><strong id="tkt-doctor"></strong></div>
          <div class="ticket-row"><span>التخصص:</span><strong id="tkt-spec"></strong></div>
          <div class="ticket-row"><span>اليوم والتاريخ والساعة:</span><strong id="tkt-time" style="color:var(--teal-dark);"></strong></div>
          <div class="ticket-row"><span>العنوان الكامل:</span><strong id="tkt-address"></strong></div>
          <div class="ticket-row"><span>هاتف سكرتير العيادة:</span><strong id="tkt-doc-phone" dir="ltr"></strong></div>
          <div class="ticket-row" style="border-top:1px dashed #cbd5e1; margin-top:6px; padding-top:8px;">
            <span>تفاصيل الحساب:</span>
            <strong id="tkt-total-fee"></strong>
          </div>
          <div class="ticket-row">
            <span>طريقة وحالة الدفع:</span>
            <strong id="tkt-pay-status"></strong>
          </div>
          <div id="tkt-receipt-row" class="hidden" style="margin-top:8px; text-align:center; background:#f8fafc; border:1px solid #e2e8f0; border-radius:12px; padding:8px;">
            <span style="display:block; font-size:11px; font-weight:800; color:var(--emerald); margin-bottom:4px;">📎 صورة إشعار التحويل المرفقة على الرقم (<span id="tkt-transfer-num" dir="ltr">6760023637</span>):</span>
            <img id="tkt-receipt-img" src="" alt="صورة التحويل" style="max-height:120px; max-width:100%; border-radius:8px;" />
          </div>

          <!-- Inline SVG QR Code -->
          <div class="qr-box">
            <svg width="88" height="88" viewBox="0 0 100 100" fill="#0f172a">
              <rect x="10" y="10" width="25" height="25" fill="none" stroke="#0f172a" stroke-width="5"/>
              <rect x="17" y="17" width="11" height="11"/>
              <rect x="65" y="10" width="25" height="25" fill="none" stroke="#0f172a" stroke-width="5"/>
              <rect x="72" y="17" width="11" height="11"/>
              <rect x="10" y="65" width="25" height="25" fill="none" stroke="#0f172a" stroke-width="5"/>
              <rect x="17" y="72" width="11" height="11"/>
              <rect x="45" y="12" width="8" height="8"/><rect x="45" y="28" width="8" height="14"/>
              <rect x="12" y="45" width="14" height="8"/><rect x="34" y="45" width="18" height="8"/>
              <rect x="62" y="45" width="10" height="10"/><rect x="80" y="45" width="10" height="18"/>
              <rect x="45" y="62" width="12" height="12"/><rect x="65" y="72" width="10" height="18"/>
              <rect x="80" y="76" width="10" height="14"/>
            </svg>
            <span style="font-size:10.5px; color:var(--text-muted); margin-top:4px;">وصل حجز إلكتروني معتمد — يُبرز للسكرتير عند الوصول</span>
          </div>
        </div>

        <div class="no-print" style="display:grid; grid-template-columns:1fr; gap:8px; margin-top:12px;">
          <button class="btn btn-emerald btn-block" onclick="sendTicketToSecretaryWA(latestTicket)">
            📲 إرسال الحجز لواتساب سكرتير الطبيب (<span id="btn-sec-wa-num" dir="ltr"></span>)
          </button>
          <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px;">
            <button class="btn btn-primary" onclick="sendTicketToPatientWA(latestTicket)">📱 إرسال لواتساب المريض</button>
            <button class="btn btn-dark" onclick="window.print()">🖨️ طباعة / حفظ PDF</button>
          </div>
          <button class="btn btn-outline btn-block" onclick="closeModal('modal-booking')">تم وإغلاق</button>
        </div>
      </div>
    </div>
  </div>

  <!-- ================= TAXONOMY EDITOR MODAL (GOVS / AREAS / SPECIALTIES) ================= -->
  <div id="modal-taxonomy" class="modal-backdrop hidden">
    <div class="modal-box" style="max-width:440px;">
      <div class="modal-header">
        <strong id="tax-modal-title">✏️ تعديل وإدارة القائمة</strong>
        <button onclick="closeModal('modal-taxonomy')" style="background:none; border:none; color:#fff; font-size:20px; cursor:pointer;">✕</button>
      </div>
      <div class="modal-body">
        <div class="form-group">
          <label id="tax-add-label" class="form-label">إضافة عنصر جديد</label>
          <div style="display:flex; gap:8px;">
            <input id="tax-new-input" type="text" class="form-control" placeholder="اكتب الاسم هنا..." onkeydown="if(event.key==='Enter'){event.preventDefault(); addTaxonomyItem();}" />
            <button type="button" class="btn btn-primary" onclick="addTaxonomyItem()" style="white-space:nowrap;">+ إضافة</button>
          </div>
        </div>

        <div style="border-top:1px solid var(--border-color); margin:12px 0; padding-top:10px;">
          <label id="tax-list-label" class="form-label" style="margin-bottom:8px;">العناصر الحالية (تعديل الاسم أو حذف)</label>
          <div id="tax-items-list" style="max-height:280px; overflow-y:auto;"></div>
        </div>

        <button type="button" class="btn btn-dark btn-block" onclick="closeModal('modal-taxonomy')">تم وحفظ التغييرات</button>
      </div>
    </div>
  </div>

  <!-- ================= SECRET ADMIN PASSCODE MODAL (808011) ================= -->
  <div id="modal-admin-auth" class="modal-backdrop hidden">
    <div class="modal-box" style="max-width:360px;">
      <div class="modal-header">
        <strong>🔐 منطقة الإدارة المحمية</strong>
        <button onclick="closeModal('modal-admin-auth')" style="background:none; border:none; color:#fff; font-size:20px; cursor:pointer;">✕</button>
      </div>
      <form class="modal-body" onsubmit="verifyAdminCode(event)">
        <p style="font-size:12.5px; color:var(--text-muted); text-align:center; margin-bottom:12px;">
          أدخل الرمز السري الخاص بمدير المنصة للوصول إلى لوحة التحكم
        </p>
        <input
          id="admin-code-input"
          type="password"
          inputmode="numeric"
          maxlength="8"
          placeholder="••••••"
          oninput="normalizeDigits(this)"
          class="form-control"
          style="text-align:center; font-size:22px; letter-spacing:8px; font-weight:900; margin-bottom:10px;"
        />
        <p id="admin-code-error" class="hidden" style="color:var(--rose); font-size:12px; font-weight:800; text-align:center; margin-bottom:10px;">
          الرمز السري غير صحيح، حاول مرة أخرى
        </p>
        <button type="submit" class="btn btn-dark btn-block">تحقق وفتح لوحة الإدارة</button>
      </form>
    </div>
  </div>

  <!-- ================= WALK-IN PATIENT MODAL ================= -->
  <div id="modal-walkin" class="modal-backdrop hidden">
    <div class="modal-box" style="max-width:400px;">
      <div class="modal-header">
        <strong>إضافة مراجع حضوري للعيادة</strong>
        <button onclick="closeModal('modal-walkin')" style="background:none; border:none; color:#fff; font-size:20px; cursor:pointer;">✕</button>
      </div>
      <div class="modal-body">
        <div class="form-group">
          <label class="form-label">الطبيب / الجهة الطبية *</label>
          <select id="walkin-doc-select" class="form-control"></select>
        </div>
        <div class="form-group">
          <label class="form-label">اسم المراجع الكامل *</label>
          <input id="walkin-name" type="text" class="form-control" placeholder="مثال: سجاد كريم الموسوي" />
        </div>
        <div class="form-group">
          <label class="form-label">رقم الهاتف</label>
          <input id="walkin-phone" type="tel" class="form-control" value="0770 444 5566" />
        </div>
        <div class="form-group">
          <label class="form-label">الحساسية الدوائية (إن وجدت)</label>
          <input id="walkin-allergy" type="text" class="form-control" placeholder="مثال: لا يوجد / البنسلين" />
        </div>
        <button class="btn btn-primary btn-block" onclick="addWalkInPatient()">إضافة للطابور فوراً</button>
      </div>
    </div>
  </div>

  <!-- ================= PRESCRIPTION PREVIEW MODAL ================= -->
  <div id="modal-rx-preview" class="modal-backdrop hidden">
    <div class="modal-box" style="max-width:440px;">
      <div class="modal-header">
        <strong>الوصفة الطبية الإلكترونية الموثقة</strong>
        <button onclick="closeModal('modal-rx-preview')" style="background:none; border:none; color:#fff; font-size:20px; cursor:pointer;">✕</button>
      </div>
      <div class="modal-body">
        <div id="rx-print-area" style="border:1.5px solid var(--teal-primary); border-radius:16px; padding:16px; background:#fff;">
          <div style="display:flex; justify-content:space-between; border-bottom:1px solid var(--border-color); padding-bottom:10px; margin-bottom:10px;">
            <div>
              <strong style="font-size:15px; color:var(--teal-dark);">عيادات نَبْض برو الذكية</strong>
              <div style="font-size:11px; color:var(--text-muted);">العراق • وصفة طبية إلكترونية</div>
            </div>
            <span style="font-size:11px; font-weight:800;">RX-2026</span>
          </div>
          <div style="font-size:12.5px; margin-bottom:10px;">
            <strong>المريض:</strong> <span id="rx-prev-patient"></span>
          </div>
          <div id="rx-prev-drugs" style="border-top:1px dashed #cbd5e1; padding-top:10px;"></div>
        </div>
        <button class="btn btn-dark btn-block" style="margin-top:12px;" onclick="window.print()">🖨️ طباعة الوصفة</button>
      </div>
    </div>
  </div>

  <!-- ================= TRANSFER RECEIPT PREVIEW MODAL ================= -->
  <div id="modal-receipt-view" class="modal-backdrop hidden">
    <div class="modal-box" style="max-width:420px;">
      <div class="modal-header">
        <strong>📸 صورة إشعار التحويل الإلكتروني</strong>
        <button onclick="closeModal('modal-receipt-view')" style="background:none; border:none; color:#fff; font-size:20px; cursor:pointer;">✕</button>
      </div>
      <div class="modal-body" style="text-align:center;">
        <p id="rec-modal-caption" style="font-size:12.5px; font-weight:800; color:var(--navy-dark); margin-bottom:10px;"></p>
        <img id="rec-modal-img" src="" alt="صورة التحويل" style="max-width:100%; max-height:65vh; border-radius:12px; border:1px solid var(--border-color);" />
        <button class="btn btn-dark btn-block" style="margin-top:12px;" onclick="closeModal('modal-receipt-view')">إغلاق</button>
      </div>
    </div>
  </div>

  <!-- Toast Container -->
  <div id="toast" class="toast-box hidden"></div>

  <!-- Footer -->
  <footer class="app-footer">
    <span>© 2026 منصة نَبْض برو (Nabdh Pro) — منظومة حجز الأطباء والمختبرات والسونار في كل العراق</span>
    <span onclick="openAdminAuthModal()" style="cursor:pointer; opacity:0.35;" title="الإدارة">🔑</span>
  </footer>

  <!-- ================= JAVASCRIPT LOGIC ================= -->
  <script>
    const SECRET_PASSCODE = "808011";
    let adminUnlocked = false;
    let tapCount = 0;
    let tapTimer = null;
    // Load Service Fee & Official Electronic Transfer Number from LocalStorage
    let serviceFee = parseInt(localStorage.getItem("nabdh_fee")) || 2000;
    let transferAccountNumber = localStorage.getItem("nabdh_transfer_num") || "6760023637";
    let uploadedReceiptDataUrl = "";

    // Week Days Constant
    const ALL_WEEK_DAYS = ["السبت", "الأحد", "الاثنين", "الثلاثاء", "الأربعاء", "الخميس", "الجمعة"];
    let adminSelectedWorkDays = ["السبت", "الأحد", "الاثنين", "الثلاثاء", "الأربعاء", "الخميس"];

    // Default Specialties (Includes Doctors, Labs & Sonar)
    const defaultSpecialties = [
      "باطنية وقلبية",
      "أطفال وحديثي الولادة",
      "نسائية وتوليد",
      "طب وجراحة الأسنان",
      "جلدية وتجميل",
      "كسور وعظام",
      "طب وجراحة العيون",
      "تحليلات مرضية شاملة",
      "سونار ودوبلر ملون",
      "رنين ومفراس وأشعة"
    ];

    // All 18 Iraqi Governorates + Major Districts/Areas
    const defaultGovAreasMap = {
      "بغداد": ["الحارثية", "المنصور", "الكرادة", "اليرموك", "حي العامل", "البياع", "السيدية", "زيونة", "الأعظمية", "الكاظمية", "الدورة"],
      "البصرة": ["العشار", "الجزائر", "البراضعية", "التميمية", "الزبير", "أبو الخصيب", "شط العرب"],
      "نينوى": ["الجانب الأيسر (الموصل)", "الجانب الأيمن (الموصل)", "حي الزهور", "المجموعة الثقافية", "تلعفر"],
      "أربيل": ["عينكاوا", "شارع 100", "إمباير", "شارع 60", "شورش", "شقلاوة"],
      "السليمانية": ["سالم", "بختياري", "سركاريز", "توجي ملك", "رانية"],
      "دهوك": ["مركز دهوك", "زاخو", "سميل", "عقرة"],
      "كركوك": ["طريق بغداد", "الشورجة", "رحيم آوه", "القادسية", "عرفة"],
      "الأنبار": ["الرمادي", "الفلوجة", "هيت", "حديثة", "القائم"],
      "ديالى": ["بعقوبة", "المقدادية", "خانقين", "الخالص"],
      "بابل": ["الحلة - شارع 40", "الحلة - شارع 60", "المسيب", "المحاويل", "الهاشمية"],
      "كربلاء": ["حي الحسين", "باب بغداد", "حي الموظفين", "حي الأسرة", "الهندية"],
      "النجف": ["حي الأمير", "الكوفة", "حي السعد", "حي الفرات", "المشخاب"],
      "واسط": ["الكوت - الهورة", "الكوت - الكفاءات", "الحي", "الصويرة", "النعمانية"],
      "صلاح الدين": ["تكريت", "سامراء", "بلد", "الدجيل", "بيجي"],
      "القادسية": ["الديوانية - العروبة", "الديوانية - الصوب الصغير", "عفك", "الشامية"],
      "ذي قار": ["الناصرية - الحبوبي", "الناصرية - الصوب الشامي", "الشطرة", "سوق الشيوخ", "الرفاعي"],
      "المثنى": ["السماوة - المركز", "الرميثة", "الخضر"],
      "ميسان": ["العمارة - دجلة", "العمارة - الماجدية", "المجر الكبير", "قلعة صالح"]
    };

    let specialties = JSON.parse(localStorage.getItem("nabdh_specialties")) || defaultSpecialties;
    let govAreasMap = JSON.parse(localStorage.getItem("nabdh_gov_areas")) || defaultGovAreasMap;
    let currentTaxType = "govs";
    let editingTaxIndex = -1;

    // Default Banner Ads
    const defaultAds = [
      {
        id: "AD-1",
        tag: "إعلان مميز • مستشفيات العراق",
        title: "مستشفى الكفيل التخصصي ومستشفيات بغداد الأهلية",
        sub: "خصم 20% على الفحوصات الشاملة والسونار الملون عند الحجز عبر منصة نَبْض برو"
      },
      {
        id: "AD-2",
        tag: "عرض خاص • المختبرات المعتمدة",
        title: "باقة الفحص الدوري الشامل (فيتامين D + الغدة + السكر التراكمي)",
        sub: "احجز موعدك الآن في أقرب مختبر بمحافظتك وتصل النتيجة والوصولات مباشرة"
      },
      {
        id: "AD-3",
        tag: "انضم كطبيب أو مركز طبي",
        title: "نظام إدارة العيادات الذكي — الحجز يصل كبل لواتساب السكرتير",
        sub: "نظّم حجوزات عيادتك بدون مكالمات متكررة مع تذاكر QR وإحصائيات دقيقة"
      }
    ];

    let bannerAds = JSON.parse(localStorage.getItem("nabdh_ads")) || defaultAds;
    let currentAdIndex = 0;
    let adInterval = null;

    // Initial Nationwide Iraq Doctors, Labs & Sonar Centers
    const initialDoctors = [
      {
        id: "DOC-1",
        category: "أطباء",
        active: true,
        name: "د. زيد المنصور",
        title: "استشاري الأمراض الباطنية والقلبية - بورد عربي",
        specialty: "باطنية وقلبية",
        gov: "بغداد",
        area: "الحارثية",
        address: "بغداد - الحارثية - شارع الكندي - مجمع النخبة الطبي",
        feeNum: 25000,
        discountPct: 20,
        secPhone: "0771 452 9910",
        workDays: ["السبت", "الأحد", "الاثنين", "الثلاثاء", "الأربعاء", "الخميس"],
        workHours: "04:00 م - 08:30 م",
        rating: "4.9",
        reviews: 640
      },
      {
        id: "DOC-2",
        category: "أطباء",
        active: true,
        name: "د. نور الهدى العبيدي",
        title: "أخصائية النسائية والتوليد والعقم وجراحتها",
        specialty: "نسائية وتوليد",
        gov: "بغداد",
        area: "المنصور",
        address: "بغداد - المنصور - تقاطع الرواد - عمارة الأمل الطبية",
        feeNum: 30000,
        discountPct: 0,
        secPhone: "0780 319 4421",
        workDays: ["السبت", "الاثنين", "الأربعاء", "الخميس"],
        workHours: "03:30 م - 08:00 م",
        rating: "4.9",
        reviews: 512
      },
      {
        id: "LAB-1",
        category: "مختبرات",
        active: true,
        name: "مختبر الدقة التخصصي للتحليلات المرضية",
        title: "تحليلات هرمونية، مناعية، فحوصات ما قبل الزواج، وسحب منزلي",
        specialty: "تحليلات مرضية شاملة",
        gov: "بغداد",
        area: "الكرادة",
        address: "بغداد - الكرادة داخل - قرب تقاطع المسبح",
        feeNum: 15000,
        discountPct: 15,
        secPhone: "0772 600 8899",
        workDays: ["السبت", "الأحد", "الاثنين", "الثلاثاء", "الأربعاء", "الخميس", "الجمعة"],
        workHours: "08:00 ص - 10:00 م",
        rating: "4.9",
        reviews: 820
      },
      {
        id: "SON-1",
        category: "سونار وأشعة",
        active: true,
        name: "مركز النور للسونار الملون والدوبلر والأشعة",
        title: "سونار رباعي الأبعاد 4D، دوبلر الأوعية الدموية، وأشعة رقمية",
        specialty: "سونار ودوبلر ملون",
        gov: "البصرة",
        area: "العشار",
        address: "البصرة - العشار - شارع الاستقلال - مجمع الفيحاء الطبي",
        feeNum: 20000,
        discountPct: 10,
        secPhone: "0770 882 1104",
        workDays: ["السبت", "الأحد", "الاثنين", "الثلاثاء", "الأربعاء", "الخميس"],
        workHours: "03:00 م - 09:00 م",
        rating: "4.8",
        reviews: 415
      },
      {
        id: "DOC-4",
        category: "أطباء",
        active: true,
        name: "د. شيرين كاوه بارزاني",
        title: "أخصائية الأمراض الجلدية والتجميل والليزر",
        specialty: "جلدية وتجميل",
        gov: "أربيل",
        area: "عينكاوا",
        address: "أربيل - عينكاوا - قرب تقاطع إمباير - مركز أربيل الطبي",
        feeNum: 25000,
        discountPct: 0,
        secPhone: "0750 612 7789",
        workDays: ["الأحد", "الثلاثاء", "الخميس"],
        workHours: "04:00 م - 08:00 م",
        rating: "4.9",
        reviews: 785
      },
      {
        id: "DOC-5",
        category: "أطباء",
        active: true,
        name: "د. مرتضى صادق النجفي",
        title: "أخصائي جراحة العظام والكسور والمفاصل",
        specialty: "كسور وعظام",
        gov: "النجف",
        area: "حي الأمير",
        address: "النجف الأشرف - حي الأمير - شارع الأطباء - مجمع الغري",
        feeNum: 20000,
        discountPct: 25,
        secPhone: "0772 901 3345",
        workDays: ["السبت", "الأحد", "الثلاثاء", "الأربعاء"],
        workHours: "04:30 م - 08:30 م",
        rating: "4.8",
        reviews: 418
      }
    ];

    let doctors = JSON.parse(localStorage.getItem("nabdh_docs_iq_v2")) || initialDoctors;
    let selectedCategory = "all";

    // Initial Bookings / Patients Queue
    const initialBookings = [
      {
        id: "P-101",
        ticketNo: "NB-4081",
        seq: 1,
        patientName: "علي محمود الكبيسي",
        phone: "0771 452 9910",
        doctorId: "DOC-1",
        doctorName: "د. زيد المنصور",
        secPhone: "0771 452 9910",
        govArea: "بغداد - الحارثية",
        time: "اليوم الثلاثاء (17/11/2026) • 04:15 م",
        docFee: 20000,
        serviceFee: 2000,
        payMethod: "ماستر كارد (4821)",
        paid: true,
        status: "in_room",
        age: 46,
        gender: "ذكر",
        blood: "O+",
        allergy: "حساسية البنسلين (Penicillin)",
        vitals: { bp: "135/85", hr: "78 bpm", temp: "37.1 °C", sugar: "142 mg/dL" },
        symptoms: "ألم ضاغط في منتصف الصدر مع ارتفاع طفيف في ضغط الدم",
        rx: [
          { name: "Concor 5mg Tab", dose: "حبة واحدة صباحاً بعد الفطور", days: "لمدة شهر" }
        ]
      },
      {
        id: "P-102",
        ticketNo: "NB-4082",
        seq: 2,
        patientName: "زهراء حسين الكرادي",
        phone: "0780 319 4421",
        doctorId: "LAB-1",
        doctorName: "مختبر الدقة التخصصي للتحليلات المرضية",
        secPhone: "0772 600 8899",
        govArea: "بغداد - الكرادة",
        time: "اليوم الثلاثاء (17/11/2026) • 05:00 م",
        docFee: 12750,
        serviceFee: 2000,
        payMethod: "كاش للسكرتير",
        paid: false,
        status: "waiting",
        age: 29,
        gender: "أنثى",
        blood: "A+",
        allergy: "لا يوجد",
        vitals: { bp: "118/76", hr: "82 bpm", temp: "36.8 °C", sugar: "95 mg/dL" },
        symptoms: "تحليلات شاملة ومتابعة دورية",
        rx: []
      }
    ];

    let bookings = JSON.parse(localStorage.getItem("nabdh_bookings_iq_v2")) || initialBookings;
    let activePatientId = bookings[0]?.id || "P-101";

    // Wizard State
    let selectedDoc = doctors[0];
    let selectedDay = "";
    let selectedSlot = "05:30 م";
    let selectedPayMethod = "كاش للسكرتير";
    let latestTicket = null;

    // Google Sheets Live API URL (الصق رابط تطبيق الويب هنا ليتم التحديث تلقائياً من الشيت)
    let SHEET_API_URL = localStorage.getItem("nabdh_sheet_api_url") || "";

    // Helper: Parse Discount (supports both fixed IQD amount like "5000" and percentage like "2%" or "20%")
    function parseDiscountInfo(doc) {
      const fee = Number(doc.feeNum) || 0;
      const raw = String(doc.discountRaw !== undefined ? doc.discountRaw : (doc.discountPct || "0")).trim();
      if (!raw || raw === "0") {
        return { finalFee: fee, hasDiscount: false, badgeText: "" };
      }
      if (raw.includes("%")) {
        const pct = Math.min(95, Math.max(0, parseFloat(raw.replace("%", "")) || 0));
        if (pct <= 0) return { finalFee: fee, hasDiscount: false, badgeText: "" };
        const finalFee = Math.max(0, Math.round(fee * (100 - pct) / 100));
        return { finalFee, hasDiscount: true, badgeText: `خصم ${pct}%` };
      } else {
        const amt = Math.max(0, parseFloat(raw.replace(/,/g, "")) || 0);
        if (amt <= 0) return { finalFee: fee, hasDiscount: false, badgeText: "" };
        // If someone enters a small number <= 90 without % from old admin form, treat as %, otherwise fixed IQD
        if (doc.discountRaw === undefined && amt <= 90) {
          const finalFee = Math.max(0, Math.round(fee * (100 - amt) / 100));
          return { finalFee, hasDiscount: true, badgeText: `خصم ${amt}%` };
        }
        const finalFee = Math.max(0, fee - amt);
        return { finalFee, hasDiscount: true, badgeText: `خصم ${amt.toLocaleString()} د.ع` };
      }
    }

    // Helper: Calculate Final Doctor Fee after Discount
    function getFinalDoctorFee(doc) {
      return parseDiscountInfo(doc).finalFee;
    }

    // Sync Doctors Live from Google Sheets
    async function syncDoctorsFromGoogleSheet(showNotification = false) {
      const url = (SHEET_API_URL || "").trim();
      if (!url || !url.startsWith("http")) return;
      try {
        const res = await fetch(url);
        const rows = await res.json();
        if (!Array.isArray(rows) || rows.length === 0) return;

        const sheetDoctors = rows
          .filter(r => r.name && String(r.name).trim() !== "")
          .map((r, idx) => {
            const spec = String(r.specialty || "باطنية وقلبية").trim();
            const cat = spec.includes("مختبر") || spec.includes("تحليلات")
              ? "مختبرات"
              : (spec.includes("سونار") || spec.includes("أشعة") || spec.includes("رنين"))
                ? "سونار وأشعة"
                : "أطباء";
            const statusStr = String(r.status || "موجود").trim();
            const isActive = statusStr === "موجود" || statusStr.toLowerCase() === "true";
            const city = String(r.city || "بغداد").trim();
            const area = String(r.area || "حي العامل").trim();
            const daysArr = String(r.days || "السبت، الأحد، الاثنين، الثلاثاء، الأربعاء، الخميس")
              .split(/[،,\-]+/)
              .map(s => s.trim())
              .filter(Boolean);

            return {
              id: "GS-DOC-" + (idx + 1),
              category: cat,
              active: isActive,
              statusText: statusStr,
              name: String(r.name).trim(),
              title: spec,
              specialty: spec,
              gov: city,
              area: area,
              address: `${city} - ${area}`,
              feeNum: Number(r.fee) || 25000,
              discountRaw: String(r.discount || "0").trim(),
              secPhone: String(r.secretary_phone || "07700000000").trim(),
              workDays: daysArr.length ? daysArr : ALL_WEEK_DAYS.slice(0, 6),
              workHours: String(r.shift || "مسائي 04:00 م - 08:00 م").trim(),
              rating: "4.9",
              reviews: 120
            };
          });

        if (sheetDoctors.length > 0) {
          doctors = sheetDoctors;
          saveState();
          renderDoctors();
          renderReception();
          if (adminUnlocked) renderAdminPanel();
          if (showNotification) showToast("✅ تم تحديث قائمة الأطباء لحظياً من Google Sheets (" + sheetDoctors.length + ")");
        }
      } catch (err) {
        console.error("Google Sheets Sync Error:", err);
        if (showNotification) showToast("⚠️ تعذر الاتصال بـ Google Sheets، تأكد من الرابط وصلاحية Anyone");
      }
    }

    // Helper: Format Iraqi Phone to International WhatsApp (9647...)
    function toIraqWhatsAppNumber(raw) {
      let digits = String(raw || "").replace(/[^0-9]/g, "");
      if (digits.startsWith("00964")) digits = digits.slice(2);
      else if (digits.startsWith("07")) digits = "964" + digits.slice(1);
      else if (digits.startsWith("7")) digits = "964" + digits;
      return digits;
    }

    // Persist Helper
    function saveState() {
      localStorage.setItem("nabdh_docs_iq_v2", JSON.stringify(doctors));
      localStorage.setItem("nabdh_bookings_iq_v2", JSON.stringify(bookings));
      localStorage.setItem("nabdh_fee", serviceFee);
      localStorage.setItem("nabdh_transfer_num", transferAccountNumber);
      localStorage.setItem("nabdh_specialties", JSON.stringify(specialties));
      localStorage.setItem("nabdh_gov_areas", JSON.stringify(govAreasMap));
      localStorage.setItem("nabdh_ads", JSON.stringify(bannerAds));
    }

    // ================= INITIALIZATION =================
    window.addEventListener("DOMContentLoaded", () => {
      document.getElementById("public-fee-hint").textContent = serviceFee.toLocaleString() + " د.ع";
      renderBannerCarousel();
      startAdAutoSlide();
      syncTaxonomyUI();
      renderAdminWorkDaysPicker();
      renderDoctors();
      renderReception();
      renderDoctorWorkspace();
      syncDoctorsFromGoogleSheet(false);
    });

    // ================= AD CAROUSEL LOGIC =================
    function renderBannerCarousel() {
      const slideEl = document.getElementById("ad-slide-content");
      const dotsEl = document.getElementById("ad-dots");
      if (!bannerAds.length) {
        document.getElementById("ad-carousel").classList.add("hidden");
        return;
      }
      document.getElementById("ad-carousel").classList.remove("hidden");
      if (currentAdIndex >= bannerAds.length) currentAdIndex = 0;

      const ad = bannerAds[currentAdIndex];
      slideEl.innerHTML = `
        <div style="flex:1; min-width:220px;">
          <span class="ad-tag">📢 ${ad.tag || "إعلان طبي"}</span>
          <h3 style="font-size:16px; font-weight:800; margin-bottom:4px;">${ad.title}</h3>
          <p style="font-size:12px; color:#e2e8f0;">${ad.sub}</p>
        </div>
        <button class="btn btn-primary btn-sm" onclick="document.getElementById('doctors-grid').scrollIntoView({behavior:'smooth'})">
          تصفح العروض والحجز
        </button>
      `;

      dotsEl.innerHTML = bannerAds.map((_, idx) =>
        `<span class="ad-dot ${idx === currentAdIndex ? "active" : ""}" onclick="goToAd(${idx})"></span>`
      ).join("");
    }

    function nextAd() {
      if (!bannerAds.length) return;
      currentAdIndex = (currentAdIndex + 1) % bannerAds.length;
      renderBannerCarousel();
    }

    function prevAd() {
      if (!bannerAds.length) return;
      currentAdIndex = (currentAdIndex - 1 + bannerAds.length) % bannerAds.length;
      renderBannerCarousel();
    }

    function goToAd(idx) {
      currentAdIndex = idx;
      renderBannerCarousel();
    }

    function startAdAutoSlide() {
      clearInterval(adInterval);
      adInterval = setInterval(nextAd, 5000);
    }

    function addNewAd() {
      const title = document.getElementById("ad-title-inp").value.trim();
      const sub = document.getElementById("ad-sub-inp").value.trim();
      if (!title) {
        showToast("يرجى كتابة عنوان الإعلان");
        return;
      }
      bannerAds.unshift({
        id: "AD-" + Date.now(),
        tag: "إعلان مستشفيات وأطباء",
        title,
        sub: sub || "احجز موعدك الآن عبر منصة نَبْض برو"
      });
      document.getElementById("ad-title-inp").value = "";
      document.getElementById("ad-sub-inp").value = "";
      saveState();
      renderBannerCarousel();
      renderAdminAdsList();
      showToast("تم نشر الإعلان في البنر المتحرك فوراً");
    }

    function deleteAd(id) {
      bannerAds = bannerAds.filter(a => a.id !== id);
      saveState();
      renderBannerCarousel();
      renderAdminAdsList();
      showToast("تم حذف الإعلان");
    }

    function renderAdminAdsList() {
      const wrap = document.getElementById("admin-ads-list");
      wrap.innerHTML = bannerAds.map(ad => `
        <div class="admin-doc-row">
          <div>
            <strong style="font-size:13px; display:block;">${ad.title}</strong>
            <span style="font-size:11.5px; color:var(--text-muted);">${ad.sub}</span>
          </div>
          <button class="btn btn-rose btn-sm" onclick="deleteAd('${ad.id}')">🗑️ حذف</button>
        </div>
      `).join("");
    }

    // ================= TAXONOMY (GOVERNORATES, AREAS & SPECIALTIES) =================
    function syncTaxonomyUI() {
      const govList = Object.keys(govAreasMap);
      const prevFilterGov = document.getElementById("filter-gov").value || "all";
      const prevFilterSpec = document.getElementById("filter-specialty").value || "all";
      const prevAdmGov = document.getElementById("adm-gov").value || govList[0] || "بغداد";
      const prevAdmSpec = document.getElementById("adm-spec").value || specialties[0];

      const fGov = document.getElementById("filter-gov");
      fGov.innerHTML = `<option value="all">جميع محافظات العراق (18)</option>` +
        govList.map(g => `<option value="${g}">${g}</option>`).join("");
      fGov.value = (prevFilterGov === "all" || govList.includes(prevFilterGov)) ? prevFilterGov : "all";

      updatePublicAreaOptions();

      const fSpec = document.getElementById("filter-specialty");
      fSpec.innerHTML = `<option value="all">جميع التخصصات الطبية</option>` +
        specialties.map(s => `<option value="${s}">${s}</option>`).join("");
      fSpec.value = specialties.includes(prevFilterSpec) ? prevFilterSpec : "all";

      const aSpec = document.getElementById("adm-spec");
      aSpec.innerHTML = specialties.map(s => `<option value="${s}">${s}</option>`).join("");
      if (specialties.includes(prevAdmSpec)) aSpec.value = prevAdmSpec;

      const aGov = document.getElementById("adm-gov");
      aGov.innerHTML = govList.map(g => `<option value="${g}">${g}</option>`).join("");
      aGov.value = govList.includes(prevAdmGov) ? prevAdmGov : (govList[0] || "");
      updateAdminAreaOptions();

      const pillsWrap = document.getElementById("specialty-pills");
      const activeSpec = fSpec.value;
      pillsWrap.innerHTML = `<button class="spec-pill ${activeSpec === "all" ? "active" : ""}" onclick="selectSpecPill(this, 'all')">الكل</button>` +
        specialties.map(s => `<button class="spec-pill ${activeSpec === s ? "active" : ""}" onclick="selectSpecPill(this, '${s.replace(/'/g, "\\'")}')">${s}</button>`).join("");
    }

    function updatePublicAreaOptions() {
      const selectedGov = document.getElementById("filter-gov").value;
      const fArea = document.getElementById("filter-area");
      const prevArea = fArea.value;

      let areaList = [];
      if (selectedGov === "all") {
        const set = new Set();
        Object.values(govAreasMap).forEach(arr => arr.forEach(a => set.add(a)));
        areaList = Array.from(set);
      } else {
        areaList = govAreasMap[selectedGov] || [];
      }

      fArea.innerHTML = `<option value="all">جميع المناطق والأقضية</option>` +
        areaList.map(a => `<option value="${a}">${a}</option>`).join("");
      fArea.value = areaList.includes(prevArea) ? prevArea : "all";
    }

    function onPublicGovChange() {
      updatePublicAreaOptions();
      filterDoctors();
    }

    function updateAdminAreaOptions() {
      const selectedGov = document.getElementById("adm-gov").value;
      const aArea = document.getElementById("adm-area");
      const prevArea = aArea.value;
      const areaList = govAreasMap[selectedGov] || ["المركز"];

      aArea.innerHTML = areaList.map(a => `<option value="${a}">${a}</option>`).join("");
      if (areaList.includes(prevArea)) aArea.value = prevArea;
    }

    function onAdminGovChange() {
      updateAdminAreaOptions();
    }

    function getActiveTaxArray() {
      if (currentTaxType === "govs") return Object.keys(govAreasMap);
      if (currentTaxType === "areas") {
        const g = document.getElementById("adm-gov").value || Object.keys(govAreasMap)[0];
        if (!govAreasMap[g]) govAreasMap[g] = [];
        return govAreasMap[g];
      }
      return specialties;
    }

    function openTaxonomyModal(type) {
      currentTaxType = type;
      editingTaxIndex = -1;
      document.getElementById("tax-new-input").value = "";

      if (type === "govs") {
        document.getElementById("tax-modal-title").textContent = "✏️ تعديل وإدارة المحافظات";
        document.getElementById("tax-add-label").textContent = "إضافة محافظة جديدة";
        document.getElementById("tax-new-input").placeholder = "اكتب اسم المحافظة هنا...";
        document.getElementById("tax-list-label").textContent = "المحافظات الحالية (تعديل الاسم أو حذف)";
      } else if (type === "areas") {
        const currentGov = document.getElementById("adm-gov").value || "بغداد";
        document.getElementById("tax-modal-title").textContent = `✏️ مناطق وأقضية محافظة (${currentGov})`;
        document.getElementById("tax-add-label").textContent = `إضافة منطقة أو قضاء جديد في ${currentGov}`;
        document.getElementById("tax-new-input").placeholder = `اكتب اسم المنطقة في ${currentGov}...`;
        document.getElementById("tax-list-label").textContent = `المناطق المسجلة في ${currentGov}:`;
      } else {
        document.getElementById("tax-modal-title").textContent = "✏️ تعديل وإدارة التخصصات الطبية";
        document.getElementById("tax-add-label").textContent = "إضافة تخصص طبي جديد";
        document.getElementById("tax-new-input").placeholder = "اكتب اسم التخصص الجديد...";
        document.getElementById("tax-list-label").textContent = "التخصصات الطبية الحالية:";
      }

      renderTaxonomyList();
      openModal("modal-taxonomy");
    }

    function renderTaxonomyList() {
      const list = getActiveTaxArray();
      const container = document.getElementById("tax-items-list");
      container.innerHTML = "";

      list.forEach((item, idx) => {
        const row = document.createElement("div");
        row.className = "taxonomy-item-row";

        if (editingTaxIndex === idx) {
          row.innerHTML = `
            <input id="tax-inline-input-${idx}" type="text" value="${item}" onkeydown="if(event.key==='Enter'){event.preventDefault(); saveTaxonomyEdit(${idx});}" />
            <div style="display:flex; gap:5px;">
              <button type="button" class="btn btn-emerald btn-sm" onclick="saveTaxonomyEdit(${idx})">حفظ</button>
              <button type="button" class="btn btn-outline btn-sm" onclick="editingTaxIndex=-1; renderTaxonomyList();">إلغاء</button>
            </div>
          `;
        } else {
          row.innerHTML = `
            <span style="font-size:13px; font-weight:800; color:var(--navy-dark);">${item}</span>
            <div style="display:flex; gap:5px;">
              <button type="button" class="btn btn-amber btn-sm" onclick="startTaxonomyEdit(${idx})">✏️ تعديل</button>
              <button type="button" class="btn btn-rose btn-sm" onclick="deleteTaxonomyItem(${idx})">🗑️</button>
            </div>
          `;
        }
        container.appendChild(row);
      });
    }

    function addTaxonomyItem() {
      const inp = document.getElementById("tax-new-input");
      const val = inp.value.trim();
      if (!val) {
        showToast("يرجى كتابة الاسم أولاً");
        return;
      }

      if (currentTaxType === "govs") {
        if (govAreasMap[val]) {
          showToast("هذه المحافظة موجودة مسبقاً");
          return;
        }
        govAreasMap[val] = ["المركز"];
      } else {
        const list = getActiveTaxArray();
        if (list.includes(val)) {
          showToast("هذا الاسم موجود مسبقاً");
          return;
        }
        list.push(val);
      }

      inp.value = "";
      saveState();
      syncTaxonomyUI();
      renderTaxonomyList();
      showToast("تمت إضافة «" + val + "» بنجاح");
    }

    function startTaxonomyEdit(idx) {
      editingTaxIndex = idx;
      renderTaxonomyList();
      setTimeout(() => {
        const inp = document.getElementById("tax-inline-input-" + idx);
        if (inp) { inp.focus(); inp.select(); }
      }, 50);
    }

    function saveTaxonomyEdit(idx) {
      const inp = document.getElementById("tax-inline-input-" + idx);
      if (!inp) return;
      const newVal = inp.value.trim();
      if (!newVal) {
        showToast("لا يمكن ترك الاسم فارغاً");
        return;
      }

      if (currentTaxType === "govs") {
        const keys = Object.keys(govAreasMap);
        const oldVal = keys[idx];
        if (oldVal !== newVal) {
          const rebuilt = {};
          keys.forEach(k => {
            rebuilt[k === oldVal ? newVal : k] = govAreasMap[k];
          });
          govAreasMap = rebuilt;
          doctors.forEach(doc => { if (doc.gov === oldVal) doc.gov = newVal; });
        }
      } else if (currentTaxType === "areas") {
        const currentGov = document.getElementById("adm-gov").value;
        const list = govAreasMap[currentGov];
        const oldVal = list[idx];
        list[idx] = newVal;
        doctors.forEach(doc => { if (doc.gov === currentGov && doc.area === oldVal) doc.area = newVal; });
      } else {
        const oldVal = specialties[idx];
        specialties[idx] = newVal;
        doctors.forEach(doc => { if (doc.specialty === oldVal) doc.specialty = newVal; });
      }

      editingTaxIndex = -1;
      saveState();
      syncTaxonomyUI();
      renderTaxonomyList();
      renderAdminPanel();
      renderDoctors();
      showToast("تم تعديل الاسم إلى «" + newVal + "»");
    }

    function deleteTaxonomyItem(idx) {
      const list = getActiveTaxArray();
      if (list.length <= 1) {
        showToast("يجب الإبقاء على عنصر واحد على الأقل");
        return;
      }

      let removed = "";
      if (currentTaxType === "govs") {
        removed = list[idx];
        delete govAreasMap[removed];
      } else {
        removed = list.splice(idx, 1)[0];
      }

      if (editingTaxIndex === idx) editingTaxIndex = -1;
      saveState();
      syncTaxonomyUI();
      renderTaxonomyList();
      filterDoctors();
      showToast("تم حذف «" + removed + "»");
    }

    // ================= TAB NAVIGATION =================
    function switchTab(tab) {
      if (tab === "admin" && !adminUnlocked) {
        openAdminAuthModal();
        return;
      }

      ["booking", "reception", "doctor", "admin"].forEach(name => {
        const sec = document.getElementById("view-" + name);
        if (sec) sec.classList.add("hidden");
        const btn = document.getElementById("nav-" + name);
        if (btn) btn.classList.remove("active");
      });

      const activeSec = document.getElementById("view-" + tab);
      if (activeSec) activeSec.classList.remove("hidden");
      const activeBtn = document.getElementById("nav-" + tab);
      if (activeBtn) activeBtn.classList.add("active");
    }

    // ================= SECRET ADMIN ACCESS (808011) =================
    function normalizeDigits(el) {
      const ar = "٠١٢٣٤٥٦٧٨٩";
      const fa = "۰۱۲۳۴۵۶۷۸۹";
      el.value = el.value
        .replace(/[٠-٩]/g, d => ar.indexOf(d))
        .replace(/[۰-۹]/g, d => fa.indexOf(d));
    }

    function handleLogoSecretTap() {
      tapCount++;
      clearTimeout(tapTimer);
      if (tapCount >= 3) {
        tapCount = 0;
        openAdminAuthModal();
      } else {
        tapTimer = setTimeout(() => { tapCount = 0; }, 750);
      }
    }

    document.addEventListener("keydown", e => {
      if (["INPUT", "TEXTAREA", "SELECT"].includes(document.activeElement.tagName)) return;
      const ar = "٠١٢٣٤٥٦٧٨٩";
      let k = e.key;
      if (ar.includes(k)) k = String(ar.indexOf(k));
      if (/^[0-9]$/.test(k)) {
        keyBuffer = (keyBuffer + k).slice(-6);
        if (keyBuffer === SECRET_PASSCODE) {
          keyBuffer = "";
          unlockAdminPanel();
        }
      }
    });

    function openAdminAuthModal() {
      if (adminUnlocked) {
        switchTab("admin");
        return;
      }
      const inp = document.getElementById("admin-code-input");
      inp.value = "";
      document.getElementById("admin-code-error").classList.add("hidden");
      openModal("modal-admin-auth");
      setTimeout(() => inp.focus(), 100);
    }

    function verifyAdminCode(e) {
      e.preventDefault();
      const inp = document.getElementById("admin-code-input");
      normalizeDigits(inp);
      if (inp.value.trim() === SECRET_PASSCODE) {
        closeModal("modal-admin-auth");
        unlockAdminPanel();
      } else {
        document.getElementById("admin-code-error").classList.remove("hidden");
      }
    }

    function saveSheetApiUrl() {
      const val = document.getElementById("admin-sheet-url-input").value.trim();
      SHEET_API_URL = val;
      localStorage.setItem("nabdh_sheet_api_url", val);
      if (val) {
        syncDoctorsFromGoogleSheet(true);
      } else {
        showToast("تم مسح رابط Google Sheets");
      }
    }

    function unlockAdminPanel() {
      adminUnlocked = true;
      document.getElementById("admin-sheet-url-input").value = SHEET_API_URL;
      document.getElementById("admin-fee-input").value = serviceFee;
      document.getElementById("admin-transfer-num-input").value = transferAccountNumber;
      renderAdminPanel();
      renderAdminAdsList();
      switchTab("admin");
      showToast("تم فتح لوحة الإدارة السرية بنجاح");
    }

    function lockAndExitAdmin() {
      adminUnlocked = false;
      switchTab("booking");
      showToast("تم قفل وإخفاء لوحة الإدارة");
    }

    // ================= ADMIN WORK DAYS PICKER =================
    function renderAdminWorkDaysPicker() {
      const wrap = document.getElementById("adm-days-picker");
      wrap.innerHTML = ALL_WEEK_DAYS.map(day => {
        const isSel = adminSelectedWorkDays.includes(day);
        return `<button type="button" class="day-toggle-btn ${isSel ? "selected" : ""}" onclick="toggleAdminWorkDay('${day}')">${day}</button>`;
      }).join("");
    }

    function toggleAdminWorkDay(day) {
      if (adminSelectedWorkDays.includes(day)) {
        if (adminSelectedWorkDays.length <= 1) {
          showToast("يجب اختيار يوم دوام واحد على الأقل");
          return;
        }
        adminSelectedWorkDays = adminSelectedWorkDays.filter(d => d !== day);
      } else {
        adminSelectedWorkDays.push(day);
      }
      renderAdminWorkDaysPicker();
    }

    // ================= ADMIN OPERATIONS =================
    function saveServiceFee() {
      const val = parseInt(document.getElementById("admin-fee-input").value) || 0;
      serviceFee = Math.max(0, val);
      saveState();
      document.getElementById("public-fee-hint").textContent = serviceFee.toLocaleString() + " د.ع";
      renderAdminPanel();
      showToast("تم تحديث رسم الخدمة إلى " + serviceFee.toLocaleString() + " د.ع");
    }

    function saveTransferNumber() {
      const val = document.getElementById("admin-transfer-num-input").value.trim();
      if (!val) {
        showToast("يرجى إدخال رقم التحويل الرسمي");
        return;
      }
      transferAccountNumber = val;
      saveState();
      showToast("تم حفظ رقم التحويل الرسمي: " + transferAccountNumber);
    }

    function renderAdminPanel() {
      const totalEarnings = bookings.reduce((sum, b) => sum + (b.serviceFee || serviceFee), 0);
      const activeCount = doctors.filter(d => d.active !== false).length;
      document.getElementById("admin-earnings").textContent = totalEarnings.toLocaleString() + " د.ع";
      document.getElementById("admin-docs-count").textContent = `${activeCount} / ${doctors.length}`;

      const list = document.getElementById("admin-doctors-list");
      list.innerHTML = "";

      doctors.forEach(doc => {
        const govLabel = doc.gov || "بغداد";
        const isActive = doc.active !== false;
        const disc = parseInt(doc.discountPct) || 0;
        const finalFee = getFinalDoctorFee(doc);

        const div = document.createElement("div");
        div.className = "admin-doc-row" + (isActive ? "" : " suspended");
        div.innerHTML = `
          <div style="flex:1; min-width:220px;">
            <div style="display:flex; flex-wrap:wrap; align-items:center; gap:6px; margin-bottom:3px;">
              <strong style="font-size:14px;">${doc.name}</strong>
              <span class="badge-cat">${doc.category || "أطباء"}</span>
              <span class="badge-spec">${doc.specialty}</span>
              ${disc > 0 ? `<span class="badge-pill badge-rose">خصم ${disc}%</span>` : ""}
              <span class="badge-pill ${isActive ? "badge-green" : "badge-rose"}">${isActive ? "🟢 مفعّل" : "🔴 متوقف"}</span>
            </div>
            <div style="font-size:12px; color:var(--text-muted);">
              ${govLabel} - ${doc.area} • الكشفية: <strong>${finalFee.toLocaleString()} د.ع</strong>
              ${disc > 0 ? `<span style="text-decoration:line-through; color:#94a3b8;">(${doc.feeNum.toLocaleString()})</span>` : ""}
              • واتساب السكرتير: <strong dir="ltr">${doc.secPhone || doc.phone}</strong>
            </div>
            <div style="font-size:11px; color:#64748b;">الدوام: ${(doc.workDays || ALL_WEEK_DAYS.slice(0, 6)).join("، ")} (${doc.workHours || "04:00 م - 08:30 م"})</div>
          </div>
          <div style="display:flex; flex-wrap:wrap; gap:6px;">
            <button class="btn ${isActive ? "btn-outline" : "btn-emerald"} btn-sm" onclick="toggleDoctorSubscription('${doc.id}')">
              ${isActive ? "⏸️ إيقاف الاشتراك" : "▶️ تفعيل الاشتراك"}
            </button>
            <button class="btn btn-amber btn-sm" onclick="editDoctorAdmin('${doc.id}')">✏️ تعديل</button>
            <button class="btn btn-rose btn-sm" onclick="deleteDoctorAdmin('${doc.id}')">🗑️ حذف</button>
          </div>
        `;
        list.appendChild(div);
      });
    }

    function toggleDoctorSubscription(id) {
      const doc = doctors.find(d => d.id === id);
      if (!doc) return;
      doc.active = doc.active === false ? true : false;
      saveState();
      renderAdminPanel();
      renderDoctors();
      showToast(doc.active ? `تم تفعيل اشتراك ${doc.name}` : `تم إيقاف اشتراك ${doc.name} مؤقتاً`);
    }

    function saveDoctorAdmin() {
      const editId = document.getElementById("admin-edit-id").value;
      const category = document.getElementById("adm-category").value;
      const active = document.getElementById("adm-active").value === "true";
      const name = document.getElementById("adm-name").value.trim();
      const title = document.getElementById("adm-title").value.trim();
      const specialty = document.getElementById("adm-spec").value;
      const gov = document.getElementById("adm-gov").value;
      const area = document.getElementById("adm-area").value;
      const address = document.getElementById("adm-address").value.trim();
      const feeNum = parseInt(document.getElementById("adm-fee").value) || 25000;
      const discountPct = Math.min(90, Math.max(0, parseInt(document.getElementById("adm-discount").value) || 0));
      const secPhone = document.getElementById("adm-sec-phone").value.trim() || "0770 111 2233";
      const workHours = document.getElementById("adm-hours").value.trim() || "04:00 م - 08:30 م";
      const workDays = [...adminSelectedWorkDays];

      if (!name || !address) {
        showToast("يرجى إدخال الاسم وعنوان العيادة");
        return;
      }

      if (editId) {
        const idx = doctors.findIndex(d => d.id === editId);
        if (idx !== -1) {
          doctors[idx] = {
            ...doctors[idx],
            category,
            active,
            name,
            title: title || specialty,
            specialty,
            gov,
            area,
            address,
            feeNum,
            discountPct,
            secPhone,
            workDays,
            workHours
          };
          showToast("تم حفظ تعديلات " + name);
        }
      } else {
        doctors.unshift({
          id: "DOC-" + Date.now(),
          category,
          active,
          name,
          title: title || "أخصائي " + specialty,
          specialty,
          gov,
          area,
          address,
          feeNum,
          discountPct,
          secPhone,
          workDays,
          workHours,
          rating: "5.0",
          reviews: 1
        });
        showToast("تم نشر " + name + " في المنصة فوراً!");
      }

      saveState();
      resetAdminForm();
      renderAdminPanel();
      renderDoctors();
      renderReception();
    }

    function editDoctorAdmin(id) {
      const doc = doctors.find(d => d.id === id);
      if (!doc) return;
      document.getElementById("admin-edit-id").value = doc.id;
      document.getElementById("adm-category").value = doc.category || "أطباء";
      document.getElementById("adm-active").value = doc.active === false ? "false" : "true";
      document.getElementById("adm-name").value = doc.name;
      document.getElementById("adm-title").value = doc.title;
      document.getElementById("adm-spec").value = doc.specialty;
      document.getElementById("adm-gov").value = doc.gov || "بغداد";
      updateAdminAreaOptions();
      document.getElementById("adm-area").value = doc.area;
      document.getElementById("adm-address").value = doc.address;
      document.getElementById("adm-fee").value = doc.feeNum;
      document.getElementById("adm-discount").value = doc.discountPct || 0;
      document.getElementById("adm-sec-phone").value = doc.secPhone || doc.phone || "0770 111 2233";
      document.getElementById("adm-hours").value = doc.workHours || "04:00 م - 08:30 م";
      adminSelectedWorkDays = [...(doc.workDays || ALL_WEEK_DAYS.slice(0, 6))];
      renderAdminWorkDaysPicker();

      document.getElementById("admin-form-heading").textContent = "✏️ تعديل: " + doc.name;
      document.getElementById("admin-submit-btn").textContent = "حفظ التعديلات";
      document.getElementById("admin-cancel-edit").classList.remove("hidden");
      document.getElementById("view-admin").scrollIntoView({ behavior: "smooth" });
    }

    function deleteDoctorAdmin(id) {
      doctors = doctors.filter(d => d.id !== id);
      saveState();
      renderAdminPanel();
      renderDoctors();
      showToast("تم الحذف من المنصة");
    }

    function resetAdminForm() {
      document.getElementById("admin-edit-id").value = "";
      document.getElementById("adm-category").value = "أطباء";
      document.getElementById("adm-active").value = "true";
      document.getElementById("adm-name").value = "";
      document.getElementById("adm-title").value = "";
      document.getElementById("adm-address").value = "";
      document.getElementById("adm-fee").value = "25000";
      document.getElementById("adm-discount").value = "0";
      adminSelectedWorkDays = ["السبت", "الأحد", "الاثنين", "الثلاثاء", "الأربعاء", "الخميس"];
      renderAdminWorkDaysPicker();
      document.getElementById("admin-form-heading").textContent = "➕ إضافة طبيب / مختبر / سونار";
      document.getElementById("admin-submit-btn").textContent = "نشر في المنصة فوراً";
      document.getElementById("admin-cancel-edit").classList.add("hidden");
    }

    // ================= BACKUP & RESTORE (JSON) =================
    function exportBackupJSON() {
      const backupPayload = {
        app: "NabdhPro_Iraq_Backup",
        exportedAt: new Date().toISOString(),
        serviceFee,
        specialties,
        govAreasMap,
        bannerAds,
        doctors,
        bookings
      };
      const blob = new Blob([JSON.stringify(backupPayload, null, 2)], { type: "application/json" });
      const url = URL.createObjectURL(blob);
      const a = document.createElement("a");
      a.href = url;
      a.download = `NabdhPro_Iraq_Backup_${new Date().toISOString().slice(0, 10)}.json`;
      a.click();
      URL.revokeObjectURL(url);
      showToast("تم تنزيل ملف النسخة الاحتياطية بنجاح 💾");
    }

    function importBackupJSON(event) {
      const file = event.target.files[0];
      if (!file) return;
      const reader = new FileReader();
      reader.onload = e => {
        try {
          const data = JSON.parse(e.target.result);
          if (data.doctors) doctors = data.doctors;
          if (data.bookings) bookings = data.bookings;
          if (data.specialties) specialties = data.specialties;
          if (data.govAreasMap) govAreasMap = data.govAreasMap;
          if (data.bannerAds) bannerAds = data.bannerAds;
          if (typeof data.serviceFee === "number") serviceFee = data.serviceFee;

          saveState();
          syncTaxonomyUI();
          renderBannerCarousel();
          renderAdminPanel();
          renderAdminAdsList();
          renderDoctors();
          renderReception();
          renderDoctorWorkspace();
          showToast("تمت استعادة النسخة الاحتياطية بالكامل بنجاح ✅");
        } catch (err) {
          showToast("ملف النسخة الاحتياطية غير صالح");
        }
      };
      reader.readAsText(file);
      event.target.value = "";
    }

    // ================= DOCTORS / LABS / SONAR DIRECTORY =================
    function selectCategory(btn, cat) {
      document.querySelectorAll(".cat-btn").forEach(b => b.classList.remove("active"));
      btn.classList.add("active");
      selectedCategory = cat;
      filterDoctors();
    }

    function selectSpecPill(btn, spec) {
      document.querySelectorAll(".spec-pill").forEach(p => p.classList.remove("active"));
      btn.classList.add("active");
      document.getElementById("filter-specialty").value = spec;
      filterDoctors();
    }

    function filterDoctors() {
      const gov = document.getElementById("filter-gov").value;
      const area = document.getElementById("filter-area").value;
      const spec = document.getElementById("filter-specialty").value;
      const q = document.getElementById("filter-query").value.trim();

      const filtered = doctors.filter(d => {
        if (d.active === false) return false; // Hide suspended subscriptions
        const docGov = d.gov || "بغداد";
        const docCat = d.category || "أطباء";
        const mCat = selectedCategory === "all" || docCat === selectedCategory;
        const mGov = gov === "all" || docGov === gov;
        const mArea = area === "all" || d.area === area;
        const mSpec = spec === "all" || d.specialty === spec;
        const mQ = !q || d.name.includes(q) || d.title.includes(q) || d.area.includes(q) || docGov.includes(q);
        return mCat && mGov && mArea && mSpec && mQ;
      });
      renderDoctors(filtered);
    }

    function renderDoctors(list = null) {
      const activeList = list || doctors.filter(d => d.active !== false);
      const grid = document.getElementById("doctors-grid");
      document.getElementById("visible-docs-count").textContent = activeList.length;
      grid.innerHTML = "";

      if (activeList.length === 0) {
        grid.innerHTML = `<div class="panel-card" style="grid-column:1/-1; text-align:center; padding:32px;">
          <p style="font-weight:800; margin-bottom:10px;">لا توجد جهات طبية مطابقة لخيارات البحث الحالية</p>
          <button class="btn btn-primary btn-sm" onclick="resetSearch()">عرض جميع الأطباء والمختبرات</button>
        </div>`;
        return;
      }

      activeList.forEach(doc => {
        const docGov = doc.gov || "بغداد";
        const discInfo = parseDiscountInfo(doc);
        const disc = discInfo.hasDiscount ? 1 : 0;
        const finalFee = discInfo.finalFee;
        const days = doc.workDays || ALL_WEEK_DAYS.slice(0, 6);
        const initials = doc.name.replace("د.", "").trim().split(" ").slice(0, 2).map(w => w[0]).join(".");

        const card = document.createElement("div");
        card.className = "doc-card";
        card.innerHTML = `
          ${discInfo.hasDiscount ? `<div class="discount-ribbon">${discInfo.badgeText}</div>` : ""}
          <div>
            <div class="doc-top">
              <div class="doc-avatar">${initials || "ن"}</div>
              <div style="flex:1;">
                <div class="doc-meta-top">
                  <span class="badge-cat">${doc.category || "أطباء"}</span>
                  <span class="badge-spec">${doc.specialty}</span>
                  <span class="badge-rating">★ ${doc.rating}</span>
                </div>
                <h4 class="doc-name">${doc.name}</h4>
                <p class="doc-title">${doc.title}</p>
              </div>
            </div>

            <div class="doc-details">
              <div class="doc-detail-row">
                <span>📍 <strong>${docGov} - ${doc.area}</strong> — ${doc.address}</span>
              </div>
              <div class="doc-detail-row">
                <span>💵 الكشفية:</span>
                <div>
                  ${disc > 0 ? `<span style="text-decoration:line-through; color:#94a3b8; margin-left:6px;">${doc.feeNum.toLocaleString()}</span>` : ""}
                  <strong style="color:var(--navy-dark); font-size:14px;">${finalFee.toLocaleString()} د.ع</strong>
                </div>
              </div>
              <div>
                <span style="font-size:11px; color:var(--text-muted);">🗓️ أيام الدوام (${doc.workHours || "04:00 م - 08:30 م"}):</span>
                <div class="work-days-badges">
                  ${days.map(d => `<span class="day-chip">${d}</span>`).join("")}
                </div>
              </div>
            </div>
          </div>

          <div class="doc-bottom">
            <div class="next-slot-box">
              <span>إرسال مباشر للسكرتير</span>
              <strong>${days[0]} • ${doc.workHours ? doc.workHours.split("-")[0].trim() : "04:30 م"}</strong>
            </div>
            <button class="btn btn-dark" onclick="openBookingModal('${doc.id}')">احجز موعدك</button>
          </div>
        `;
        grid.appendChild(card);
      });
    }

    function resetSearch() {
      selectedCategory = "all";
      document.querySelectorAll(".cat-btn").forEach(b => b.classList.toggle("active", b.dataset.cat === "all"));
      document.getElementById("filter-gov").value = "all";
      updatePublicAreaOptions();
      document.getElementById("filter-specialty").value = "all";
      document.getElementById("filter-query").value = "";
      renderDoctors();
    }

    // ================= BOOKING WIZARD & INSTANT SECRETARY DISPATCH =================
    function buildUpcomingDoctorDates(doc) {
      const allowedDays = doc.workDays && doc.workDays.length ? doc.workDays : ALL_WEEK_DAYS.slice(0, 6);
      const arDays = ["الأحد", "الاثنين", "الثلاثاء", "الأربعاء", "الخميس", "الجمعة", "السبت"];
      const results = [];
      const base = new Date();

      for (let offset = 0; offset < 14 && results.length < 4; offset++) {
        const d = new Date(base);
        d.setDate(base.getDate() + offset);
        const dayName = arDays[d.getDay()];
        if (allowedDays.includes(dayName)) {
          const dateStr = `${d.getDate()}/${d.getMonth() + 1}/${d.getFullYear()}`;
          const prefix = offset === 0 ? "اليوم " : offset === 1 ? "غداً " : "";
          results.push(`${prefix}${dayName} (${dateStr})`);
        }
      }
      return results.length ? results : ["اليوم الثلاثاء (17/11/2026)"];
    }

    function openBookingModal(docId) {
      selectedDoc = doctors.find(d => d.id === docId) || doctors[0];
      const docGov = selectedDoc.gov || "بغداد";
      const upcomingDays = buildUpcomingDoctorDates(selectedDoc);
      selectedDay = upcomingDays[0];
      selectedSlot = "05:30 م";
      selectedPayMethod = "كاش للسكرتير";

      const discInfo = parseDiscountInfo(selectedDoc);
      const finalFee = discInfo.finalFee;

      document.getElementById("booking-form-step").classList.remove("hidden");
      document.getElementById("booking-ticket-step").classList.add("hidden");
      document.getElementById("modal-booking-title").textContent = "حجز موعد — " + selectedDoc.name;

      document.getElementById("wiz-doc-name").textContent = selectedDoc.name;
      document.getElementById("wiz-doc-sub").textContent = `${selectedDoc.specialty} • ${docGov} - ${selectedDoc.area} (${selectedDoc.workHours || ""})`;
      document.getElementById("wiz-fee-summary").innerHTML = discInfo.hasDiscount
        ? `الكشفية: <span style="text-decoration:line-through; color:#64748b;">${selectedDoc.feeNum.toLocaleString()}</span> <span style="color:var(--rose);">${finalFee.toLocaleString()} د.ع (${discInfo.badgeText})</span> + رسم الخدمة: ${serviceFee.toLocaleString()} د.ع`
        : `الكشفية: ${finalFee.toLocaleString()} د.ع + رسم الخدمة: ${serviceFee.toLocaleString()} د.ع`;

      selectPaymentMethod("كاش للسكرتير");
      renderWizardDaysSlots(upcomingDays);
      openModal("modal-booking");
    }

    function renderWizardDaysSlots(daysList = null) {
      const days = daysList || buildUpcomingDoctorDates(selectedDoc);
      const daysWrap = document.getElementById("wiz-days");
      daysWrap.innerHTML = "";
      days.forEach(d => {
        const b = document.createElement("button");
        b.type = "button";
        b.className = "slot-btn" + (d === selectedDay ? " selected" : "");
        b.textContent = d;
        b.onclick = () => { selectedDay = d; renderWizardDaysSlots(days); };
        daysWrap.appendChild(b);
      });

      const slots = [
        { t: "04:30 م", busy: false },
        { t: "05:00 م", busy: false },
        { t: "05:30 م", busy: false },
        { t: "06:00 م", busy: false },
        { t: "06:30 م", busy: true },
        { t: "07:00 م", busy: false }
      ];
      const slotsWrap = document.getElementById("wiz-slots");
      slotsWrap.innerHTML = "";
      slots.forEach(s => {
        const b = document.createElement("button");
        b.type = "button";
        b.disabled = s.busy;
        b.className = "slot-btn" + (!s.busy && s.t === selectedSlot ? " selected" : "");
        b.textContent = s.t;
        b.onclick = () => { selectedSlot = s.t; renderWizardDaysSlots(days); };
        slotsWrap.appendChild(b);
      });
    }

    function selectPaymentMethod(method) {
      selectedPayMethod = method;
      const isElectronic = method === "تحويل إلكتروني / ماستر";
      document.getElementById("pay-opt-cash").classList.toggle("selected", !isElectronic);
      document.getElementById("pay-opt-card").classList.toggle("selected", isElectronic);
      document.getElementById("card-input-box").classList.toggle("hidden", !isElectronic);

      if (isElectronic) {
        document.getElementById("wiz-transfer-fee-lbl").textContent = serviceFee.toLocaleString() + " د.ع";
        document.getElementById("wiz-transfer-number-display").textContent = transferAccountNumber;
        showToast("⚠️ تنبيه: يرجى التحويل إلى " + transferAccountNumber + " وإرفاق صورة التحويل");
      }
    }

    function copyTransferNumber() {
      const tempInp = document.createElement("input");
      tempInp.value = transferAccountNumber;
      document.body.appendChild(tempInp);
      tempInp.select();
      document.execCommand("copy");
      document.body.removeChild(tempInp);
      showToast("📋 تم نسخ رقم التحويل: " + transferAccountNumber);
    }

    function handleReceiptUpload(event) {
      const file = event.target.files[0];
      if (!file) {
        uploadedReceiptDataUrl = "";
        document.getElementById("wiz-receipt-preview-wrap").classList.add("hidden");
        return;
      }
      const reader = new FileReader();
      reader.onload = e => {
        const img = new Image();
        img.onload = () => {
          const canvas = document.createElement("canvas");
          const maxW = 640;
          const scale = img.width > maxW ? maxW / img.width : 1;
          canvas.width = img.width * scale;
          canvas.height = img.height * scale;
          const ctx = canvas.getContext("2d");
          ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
          uploadedReceiptDataUrl = canvas.toDataURL("image/jpeg", 0.75);
          document.getElementById("wiz-receipt-preview-img").src = uploadedReceiptDataUrl;
          document.getElementById("wiz-receipt-preview-wrap").classList.remove("hidden");
          showToast("✅ تم تحميل صورة التحويل بنجاح");
        };
        img.src = e.target.result;
      };
      reader.readAsDataURL(file);
    }

    function confirmBooking() {
      const pName = document.getElementById("wiz-p-name").value.trim();
      const pPhone = document.getElementById("wiz-p-phone").value.trim();
      if (!pName || !pPhone) {
        showToast("يرجى إدخال اسم المريض ورقم الهاتف");
        return;
      }

      const isElectronic = selectedPayMethod === "تحويل إلكتروني / ماستر";
      if (isElectronic && !uploadedReceiptDataUrl) {
        showToast("⚠️ تنبيه: لا يمكن إتمام الحجز بدون تصوير وإرفاق صورة التحويل على الرقم " + transferAccountNumber);
        document.getElementById("wiz-transfer-receipt").focus();
        return;
      }

      const docGov = selectedDoc.gov || "بغداد";
      const payLabel = isElectronic ? `تحويل إلكتروني (${transferAccountNumber})` : "كاش للسكرتير";
      const ticketNo = "NB-" + Math.floor(4085 + Math.random() * 900);
      const finalDocFee = getFinalDoctorFee(selectedDoc);
      const total = finalDocFee + serviceFee;
      const docQueueCount = bookings.filter(b => b.doctorId === selectedDoc.id).length + 1;
      const secPhone = selectedDoc.secPhone || selectedDoc.phone || "0770 111 2233";

      const record = {
        id: "P-" + Date.now(),
        ticketNo,
        seq: docQueueCount,
        patientName: pName,
        phone: pPhone,
        doctorId: selectedDoc.id,
        doctorName: selectedDoc.name,
        secPhone,
        govArea: `${docGov} - ${selectedDoc.area}`,
        time: `${selectedDay} • ${selectedSlot}`,
        docFee: finalDocFee,
        serviceFee: serviceFee,
        payMethod: payLabel,
        paid: isElectronic,
        receiptImg: isElectronic ? uploadedReceiptDataUrl : "",
        transferTo: isElectronic ? transferAccountNumber : "",
        status: "waiting",
        age: 35,
        gender: "ذكر",
        blood: "O+",
        allergy: "لا يوجد",
        vitals: { bp: "120/80", hr: "76 bpm", temp: "36.9 °C", sugar: "100 mg/dL" },
        symptoms: "حجز إلكتروني عبر منصة نَبْض برو",
        rx: []
      };

      bookings.unshift(record);
      latestTicket = record;
      saveState();

      // Fill Ticket UI
      document.getElementById("tkt-number").textContent = "#" + ticketNo;
      document.getElementById("tkt-queue").textContent = "التسلسل #" + docQueueCount;
      document.getElementById("tkt-patient").textContent = pName;
      document.getElementById("tkt-p-phone").textContent = pPhone;
      document.getElementById("tkt-doctor").textContent = selectedDoc.name;
      document.getElementById("tkt-spec").textContent = selectedDoc.specialty;
      document.getElementById("tkt-time").textContent = `${selectedDay} — ${selectedSlot}`;
      document.getElementById("tkt-address").textContent = `${docGov} (${selectedDoc.area}) — ${selectedDoc.address}`;
      document.getElementById("tkt-doc-phone").textContent = secPhone;
      document.getElementById("btn-sec-wa-num").textContent = secPhone;
      document.getElementById("tkt-total-fee").textContent =
        `${total.toLocaleString()} د.ع (كشفية ${finalDocFee.toLocaleString()} + خدمة ${serviceFee.toLocaleString()})`;
      document.getElementById("tkt-pay-status").innerHTML = isElectronic
        ? `<span style="color:var(--emerald);">✅ تم التحويل على ${transferAccountNumber} ومرفق الوصل</span>`
        : `<span style="color:var(--amber);">💵 يُدفع كاش عند السكرتير</span>`;

      const tktReceiptRow = document.getElementById("tkt-receipt-row");
      if (isElectronic && uploadedReceiptDataUrl) {
        document.getElementById("tkt-transfer-num").textContent = transferAccountNumber;
        document.getElementById("tkt-receipt-img").src = uploadedReceiptDataUrl;
        tktReceiptRow.classList.remove("hidden");
      } else {
        tktReceiptRow.classList.add("hidden");
      }

      // Reset upload buffer for next booking
      uploadedReceiptDataUrl = "";
      document.getElementById("wiz-transfer-receipt").value = "";
      document.getElementById("wiz-receipt-preview-wrap").classList.add("hidden");

      document.getElementById("booking-form-step").classList.add("hidden");
      document.getElementById("booking-ticket-step").classList.remove("hidden");
      document.getElementById("modal-booking-title").textContent = "تم إرسال الحجز للسكرتير بنجاح!";

      renderReception();
      renderDoctorWorkspace();
      showToast(isElectronic
        ? "⚠️ تم التحقق من صورة التحويل (" + transferAccountNumber + ") وإرسال الحجز كبل لواتساب السكرتير!"
        : "🚀 وصل الحجز كبل إلى شاشة سكرتير " + selectedDoc.name);

      // Automatically trigger WhatsApp message to Doctor's Secretary
      if (document.getElementById("wiz-auto-wa-sec").checked) {
        setTimeout(() => {
          sendTicketToSecretaryWA(record);
        }, 450);
      }
    }

    function buildTicketMessageText(tkt) {
      const total = tkt.docFee + (tkt.serviceFee || 0);
      const lines = [
        `🏥 *حجز جديد — منصة نَبْض برو الطبية*`,
        `🔖 *رقم الوصل:* #${tkt.ticketNo} (التسلسل: ${tkt.seq || 1})`,
        `👤 *اسم المريض:* ${tkt.patientName}`,
        `📞 *رقم هاتف المريض:* ${tkt.phone}`,
        `👨‍⚕️ *الطبيب / الجهة:* ${tkt.doctorName}`,
        `📍 *الموقع:* ${tkt.govArea}`,
        `🗓️ *الموعد:* ${tkt.time}`,
        `💵 *المبلغ الكلي:* ${total.toLocaleString()} د.ع`,
        `💳 *طريقة الدفع:* ${tkt.payMethod} (${tkt.paid ? "مدفوع" : "يُدفع عند السكرتير"})`
      ];
      if (tkt.receiptImg) {
        lines.push(`⚠️ *تنبيه التحويل:* تم تحويل الرسم إلكترونياً على الرقم (${tkt.transferTo || transferAccountNumber}) وتم تصوير وإرفاق إشعار التحويل في النظام ✅`);
      }
      return lines.join("\n");
    }

    function sendTicketToSecretaryWA(tkt) {
      if (!tkt) return;
      const waPhone = toIraqWhatsAppNumber(tkt.secPhone);
      const text = encodeURIComponent(buildTicketMessageText(tkt));
      window.open(`https://wa.me/${waPhone}?text=${text}`, "_blank");
    }

    function sendTicketToPatientWA(tkt) {
      if (!tkt) return;
      const waPhone = toIraqWhatsAppNumber(tkt.phone);
      const text = encodeURIComponent(buildTicketMessageText(tkt));
      window.open(`https://wa.me/${waPhone}?text=${text}`, "_blank");
    }

    // ================= RECEPTION DESK (SECRETARY) =================
    function renderReception() {
      const filterSelect = document.getElementById("rec-doc-filter");
      const prevDocFilter = filterSelect.value || "all";
      filterSelect.innerHTML = `<option value="all">جميع الأطباء والمختبرات (${bookings.length})</option>` +
        doctors.map(d => `<option value="${d.id}">${d.name}</option>`).join("");
      filterSelect.value = (prevDocFilter === "all" || doctors.some(d => d.id === prevDocFilter)) ? prevDocFilter : "all";

      const selectedDocFilter = filterSelect.value;
      const visibleBookings = selectedDocFilter === "all"
        ? bookings
        : bookings.filter(b => b.doctorId === selectedDocFilter);

      const tbody = document.getElementById("reception-tbody");
      tbody.innerHTML = "";

      let waiting = 0, paidCount = 0, revenue = 0;

      visibleBookings.forEach(b => {
        if (b.status === "waiting") waiting++;
        if (b.paid) {
          paidCount++;
          revenue += (b.docFee + (b.serviceFee || 0));
        }

        const total = b.docFee + (b.serviceFee || 0);
        const tr = document.createElement("tr");
        tr.innerHTML = `
          <td>
            <strong style="color:var(--teal-dark); display:block;">#${b.ticketNo}</strong>
            <span class="badge-pill badge-green">تسلسل #${b.seq || 1}</span>
          </td>
          <td>
            <strong>${b.patientName}</strong>
            <div style="font-size:11.5px; color:var(--text-muted);" dir="ltr">${b.phone}</div>
          </td>
          <td>
            <strong>${b.doctorName}</strong>
            <div style="font-size:11px; color:var(--text-muted);">${b.govArea || ""}</div>
          </td>
          <td style="font-size:11.5px; font-weight:700;">${b.time}</td>
          <td>
            <strong>${total.toLocaleString()} د.ع</strong>
            <div><span class="badge-pill badge-indigo">${b.payMethod}</span></div>
            ${b.receiptImg ? `<button class="btn btn-amber btn-sm" style="margin-top:4px; padding:3px 8px; font-size:10.5px;" onclick="viewBookingReceipt('${b.id}')">📸 عرض صورة التحويل</button>` : ""}
          </td>
          <td>
            <button class="badge-pill ${b.paid ? "badge-green" : "badge-rose"}" style="cursor:pointer;" onclick="togglePaid('${b.id}')">
              ${b.paid ? "✅ مدفوع" : "⏳ كاش بالعيادة"}
            </button>
          </td>
          <td>
            <div style="display:flex; flex-wrap:wrap; gap:5px;">
              <button class="btn btn-dark btn-sm" onclick="admitToDoctor('${b.id}')">إدخال للفحص</button>
              <button class="btn btn-emerald btn-sm" onclick="resendRowToPatientWA('${b.id}')" title="إرسال الوصل لواتساب المريض">📲 واتساب</button>
            </div>
          </td>
        `;
        tbody.appendChild(tr);
      });

      document.getElementById("nav-sec-badge").textContent = bookings.filter(b => b.status === "waiting").length;
      document.getElementById("rec-total").textContent = visibleBookings.length;
      document.getElementById("rec-waiting").textContent = waiting;
      document.getElementById("rec-paid").textContent = paidCount;
      document.getElementById("rec-revenue").textContent = revenue.toLocaleString() + " د.ع";
    }

    function viewBookingReceipt(bookingId) {
      const b = bookings.find(x => x.id === bookingId);
      if (!b || !b.receiptImg) return;
      document.getElementById("rec-modal-caption").textContent =
        `إشعار تحويل المريض: ${b.patientName} (#${b.ticketNo}) — إلى الرقم ${b.transferTo || transferAccountNumber}`;
      document.getElementById("rec-modal-img").src = b.receiptImg;
      openModal("modal-receipt-view");
    }

    function resendRowToPatientWA(bookingId) {
      const b = bookings.find(x => x.id === bookingId);
      if (b) sendTicketToPatientWA(b);
    }

    function togglePaid(id) {
      const b = bookings.find(x => x.id === id);
      if (!b) return;
      b.paid = !b.paid;
      saveState();
      renderReception();
      showToast(b.paid ? "تم تأكيد استلام المبلغ لدى السكرتير" : "تم تغيير الحالة إلى غير مدفوع");
    }

    function admitToDoctor(id) {
      bookings.forEach(b => { if (b.status === "in_room") b.status = "completed"; });
      const target = bookings.find(b => b.id === id);
      if (target) {
        target.status = "in_room";
        activePatientId = target.id;
        saveState();
        renderReception();
        renderDoctorWorkspace();
        switchTab("doctor");
        showToast("تم إدخال " + target.patientName + " إلى غرفة الطبيب");
      }
    }

    function openWalkInModal() {
      document.getElementById("walkin-name").value = "";
      document.getElementById("walkin-doc-select").innerHTML = doctors.map(d =>
        `<option value="${d.id}">${d.name} (${d.gov || "بغداد"})</option>`
      ).join("");
      openModal("modal-walkin");
    }

    function addWalkInPatient() {
      const docId = document.getElementById("walkin-doc-select").value;
      const doc = doctors.find(d => d.id === docId) || doctors[0];
      const name = document.getElementById("walkin-name").value.trim();
      const phone = document.getElementById("walkin-phone").value.trim() || "0770 000 0000";
      const allergy = document.getElementById("walkin-allergy").value.trim() || "لا يوجد";
      if (!name) {
        showToast("يرجى كتابة اسم المراجع");
        return;
      }

      const finalDocFee = getFinalDoctorFee(doc);
      bookings.unshift({
        id: "P-" + Date.now(),
        ticketNo: "NB-" + Math.floor(4100 + Math.random() * 800),
        seq: bookings.filter(b => b.doctorId === doc.id).length + 1,
        patientName: name,
        phone,
        doctorId: doc.id,
        doctorName: doc.name,
        secPhone: doc.secPhone || "0770 111 2233",
        govArea: `${doc.gov || "بغداد"} - ${doc.area}`,
        time: "الآن (حضوري مباشر)",
        docFee: finalDocFee,
        serviceFee: serviceFee,
        payMethod: "كاش للسكرتير",
        paid: true,
        status: "waiting",
        age: 38,
        gender: "ذكر",
        blood: "A+",
        allergy,
        vitals: { bp: "120/80", hr: "75 bpm", temp: "37.0 °C", sugar: "102 mg/dL" },
        symptoms: "مراجعة حضورية في العيادة",
        rx: []
      });

      saveState();
      closeModal("modal-walkin");
      renderReception();
      renderDoctorWorkspace();
      showToast("تمت إضافة " + name + " إلى طابور السكرتير فوراً");
    }

    // ================= DOCTOR WORKSPACE & SMART RX =================
    function renderDoctorWorkspace() {
      const qList = document.getElementById("doctor-queue-list");
      qList.innerHTML = "";

      bookings.forEach((b, idx) => {
        const div = document.createElement("div");
        div.className = "queue-item" + (b.id === activePatientId ? " active" : "");
        div.onclick = () => { activePatientId = b.id; renderDoctorWorkspace(); };
        div.innerHTML = `
          <div style="display:flex; justify-content:space-between; align-items:center;">
            <strong>${idx + 1}. ${b.patientName}</strong>
            <span class="badge-pill ${b.status === "in_room" ? "badge-green" : b.status === "waiting" ? "badge-amber" : "badge-gray"}">
              ${b.status === "in_room" ? "بالداخل" : b.status === "waiting" ? "ينتظر" : "مكتمل"}
            </span>
          </div>
          <div style="font-size:11.5px; color:var(--text-muted); margin-top:4px;">#${b.ticketNo} • ${b.doctorName}</div>
        `;
        qList.appendChild(div);
      });

      const active = bookings.find(b => b.id === activePatientId) || bookings[0];
      if (!active) return;

      document.getElementById("emr-p-name").textContent = active.patientName;
      document.getElementById("emr-p-meta").textContent = `العمر: ${active.age} سنة • ${active.gender} • فصيلة الدم: ${active.blood} • تذكرة #${active.ticketNo}`;
      document.getElementById("emr-allergy-text").textContent = active.allergy;
      document.getElementById("v-bp").textContent = active.vitals.bp;
      document.getElementById("v-hr").textContent = active.vitals.hr;
      document.getElementById("v-temp").textContent = active.vitals.temp;
      document.getElementById("v-sugar").textContent = active.vitals.sugar;
      document.getElementById("emr-symptoms").value = active.symptoms;

      renderPrescriptionList(active);
    }

    function callNextPatient() {
      const next = bookings.find(b => b.status === "waiting");
      if (!next) {
        showToast("لا يوجد مرضى في قائمة الانتظار حالياً");
        return;
      }
      admitToDoctor(next.id);
    }

    function addDrugToPrescription() {
      const active = bookings.find(b => b.id === activePatientId);
      if (!active) return;

      const raw = document.getElementById("rx-drug-select").value;
      const [name, dose, days] = raw.split("|");

      if (active.allergy.includes("البنسلين") && name.includes("Penicillin")) {
        showToast("⛔ تحذير طبي خطير: المريض لديه حساسية من البنسلين! تم منع إضافة Augmentin");
        return;
      }

      active.rx.push({ name, dose, days });
      saveState();
      renderPrescriptionList(active);
      showToast("تمت إضافة الدواء للوصفة الإلكترونية");
    }

    function removeDrugFromRx(index) {
      const active = bookings.find(b => b.id === activePatientId);
      if (!active) return;
      active.rx.splice(index, 1);
      saveState();
      renderPrescriptionList(active);
    }

    function renderPrescriptionList(patient) {
      const wrap = document.getElementById("emr-rx-list");
      wrap.innerHTML = "";
      if (!patient.rx || patient.rx.length === 0) {
        wrap.innerHTML = `<p style="font-size:12px; color:var(--text-muted); text-align:center; padding:8px;">لم يتم إضافة أدوية للوصفة بعد</p>`;
        return;
      }

      patient.rx.forEach((d, i) => {
        const row = document.createElement("div");
        row.className = "rx-row";
        row.innerHTML = `
          <div>
            <strong style="font-size:13px; display:block;" dir="ltr">${d.name}</strong>
            <span style="font-size:11.5px; color:var(--text-muted);">${d.dose} • ${d.days}</span>
          </div>
          <button class="btn btn-rose btn-sm" onclick="removeDrugFromRx(${i})">حذف</button>
        `;
        wrap.appendChild(row);
      });
    }

    function previewPrescription() {
      const active = bookings.find(b => b.id === activePatientId);
      if (!active) return;
      document.getElementById("rx-prev-patient").textContent = `${active.patientName} (#${active.ticketNo})`;
      const drugsBox = document.getElementById("rx-prev-drugs");
      drugsBox.innerHTML = active.rx.length
        ? active.rx.map((d, i) => `<div style="padding:6px 0; border-bottom:1px solid #f1f5f9;"><strong>${i + 1}. ${d.name}</strong><div style="font-size:11.5px; color:#475569;">${d.dose} — ${d.days}</div></div>`).join("")
        : `<p style="font-size:12px; color:#64748b;">لا توجد أدوية مضافة</p>`;
      openModal("modal-rx-preview");
    }

    // ================= MODAL & TOAST HELPERS =================
    function openModal(id) {
      document.getElementById(id).classList.remove("hidden");
    }

    function closeModal(id) {
      document.getElementById(id).classList.add("hidden");
    }

    let toastTimer = null;
    function showToast(msg) {
      const t = document.getElementById("toast");
      t.textContent = msg;
      t.classList.remove("hidden");
      clearTimeout(toastTimer);
      toastTimer = setTimeout(() => { t.classList.add("hidden"); }, 3500);
    }
  </script>
</body>
</html>
