<!doctype html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>学期任务可视化日历（2026）</title>
  <style>
    :root {
      --bg: #f6f8fb;
      --card: #ffffff;
      --text: #1f2937;
      --muted: #6b7280;
      --border: #e5e7eb;
      --red: #e11d48;
      --green: #059669;
      --amber: #d97706;
      --blue: #2563eb;
      --shadow: 0 10px 24px rgba(2, 6, 23, 0.08);
    }
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "PingFang SC", "Noto Sans CJK SC", "Microsoft YaHei", sans-serif;
      background: var(--bg);
      color: var(--text);
    }
    .wrap { max-width: 1220px; margin: 0 auto; padding: 16px 20px 32px; }
    .title {
      background: linear-gradient(135deg, #0f172a 0%, #1d4ed8 100%);
      color: #fff;
      border-radius: 16px;
      padding: 18px 20px;
      box-shadow: var(--shadow);
    }
    .title h1 { margin: 0 0 8px 0; font-size: 22px; }
    .title p { margin: 0; opacity: 0.92; font-size: 14px; line-height: 1.5; }
    .panel {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 14px;
      box-shadow: var(--shadow);
      padding: 14px;
    }
    /* —— 心流：筛选 → 优先 → 清单 | 月历+详情 —— */
    .toolbar {
      margin-top: 14px;
      padding: 12px 14px;
    }
    .toolbar-row { margin-top: 8px; }
    .toolbar-row:first-of-type { margin-top: 0; }
    .toolbar-label {
      display: block; font-size: 11px; font-weight: 700; color: var(--muted);
      text-transform: uppercase; letter-spacing: 0.04em; margin-bottom: 6px;
    }
    .priority-panel {
      margin-top: 14px;
      padding: 14px 16px;
      border-left: 4px solid #2563eb;
    }
    .priority-next {
      cursor: pointer;
      padding: 12px 14px;
      border-radius: 12px;
      background: linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%);
      border: 1px solid #93c5fd;
      transition: transform 0.12s ease, box-shadow 0.12s ease;
    }
    .priority-next:hover { transform: translateY(-1px); box-shadow: 0 6px 16px rgba(37, 99, 235, 0.12); }
    .priority-next .pn-title { font-size: 16px; font-weight: 800; margin: 0 0 6px; color: #0f172a; }
    .priority-week-heading { font-size: 13px; color: var(--muted); margin: 0 0 8px; font-weight: 700; }
    .priority-next .pn-meta { font-size: 13px; color: #374151; margin: 0; line-height: 1.45; }
    .priority-week { margin-top: 14px; }
    .pw-list { list-style: none; margin: 0; padding: 0; }
    .pw-item {
      display: flex; align-items: flex-start; gap: 10px;
      padding: 8px 10px; border-radius: 10px; border: 1px solid var(--border);
      margin-bottom: 6px; cursor: pointer; background: #fafafa;
      font-size: 13px; line-height: 1.4;
    }
    .pw-item:hover { background: #f3f4f6; border-color: #d1d5db; }
    .pw-item .pw-date { flex: 0 0 118px; font-weight: 700; color: #1e40af; font-size: 12px; }
    .pw-item .pw-body { flex: 1; min-width: 0; }
    .pw-item.pw-item-past {
      opacity: 0.68;
      background: #eef0f3;
      border-color: #e2e5ea;
    }
    .pw-item .pw-course { font-weight: 700; color: #111827; }
    .pw-item .pw-line-title { display: block; }
    .pw-status-row {
      display: flex;
      flex-wrap: wrap;
      gap: 6px 12px;
      margin-top: 6px;
      align-items: center;
      font-size: 11px;
      color: #4b5563;
    }
    .pw-loc {
      display: inline-flex;
      align-items: center;
      gap: 5px;
      font-weight: 700;
      color: #374151;
    }
    .pw-loc .pw-dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      flex-shrink: 0;
    }
    .pw-loc-onsite .pw-dot { background: var(--red); }
    .pw-loc-remote .pw-dot { background: var(--green); }
    .pw-flag-graded { font-weight: 700; color: #92400e; }
    .pw-pre-mini {
      font-size: 10px;
      padding: 2px 7px;
      border-radius: 999px;
      font-weight: 700;
      border: 1px solid #ddd6fe;
      background: #f5f3ff;
      color: #5b21b6;
    }
    .pw-pre-mini.soft {
      border-color: #e5e7eb;
      background: #f9fafb;
      color: #6b7280;
    }
    .pw-online-tag { font-size: 10px; padding: 1px 6px; border-radius: 999px; background: #dcfce7; color: #166534; margin-left: 6px; vertical-align: middle; }
    .layout-split {
      display: grid;
      grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
      gap: 16px;
      margin-top: 16px;
      align-items: start;
    }
    .stream-panel { min-width: 0; }
    .section-title {
      margin: 0 0 10px; font-size: 16px; font-weight: 800; color: #0f172a;
      display: flex; flex-wrap: wrap; align-items: baseline; gap: 8px;
    }
    .side-rail {
      position: sticky;
      top: 12px;
      max-height: calc(100vh - 24px);
      overflow: auto;
      min-width: 0;
    }
    .panel-cal { flex: 0 0 auto; width: 100%; }
    .priority-panel-title {
      margin: 0 0 12px;
      font-size: 17px;
      font-weight: 800;
      color: #0f172a;
    }
    .filter-toggles {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      align-items: center;
    }
    .filter-toggles .quick-btn { margin: 0; }
    .event.cal-focus {
      outline: 2px solid #818cf8;
      outline-offset: 1px;
      background: #f5f7ff;
    }
    .event.is-expanded { border-color: #a5b4fc; }
    .event-detail-inline {
      display: none;
      margin-top: 10px;
      padding-top: 10px;
      border-top: 1px dashed var(--border);
      font-size: 13px;
      color: #374151;
    }
    .event.is-expanded .event-detail-inline { display: block; }
    .legend { display: flex; flex-wrap: wrap; gap: 10px; margin-top: 8px; }
    .chip {
      display: inline-flex; align-items: center; gap: 6px;
      border: 1px solid var(--border); border-radius: 999px;
      padding: 4px 10px; font-size: 13px; background: #fff;
      color: #111827; font-weight: 600;
    }
    .dot { width: 10px; height: 10px; border-radius: 50%; display: inline-block; }
    .dot.red { background: var(--red); }
    .dot.green { background: var(--green); }
    .dot.star { background: var(--amber); clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%); }

    .filters { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 10px; }
    .filters label {
      background: #f9fafb; border: 1px solid var(--border);
      border-radius: 10px; padding: 6px 10px; font-size: 13px; cursor: pointer;
    }
    .filters input { vertical-align: middle; margin-right: 6px; }
    .row { display: flex; gap: 8px; align-items: center; margin-top: 10px; }
    .row input[type="text"] {
      flex: 1; border: 1px solid var(--border); border-radius: 10px; padding: 8px 10px;
      font-size: 14px;
    }
    .row button {
      border: 1px solid var(--border); background: #fff; border-radius: 10px;
      padding: 8px 12px; cursor: pointer;
    }
    .quick-row { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 10px; }
    .quick-btn {
      border: 1px solid #bfdbfe; background: #eff6ff; color: #1e3a8a;
      border-radius: 999px; padding: 6px 12px; font-size: 13px; cursor: pointer;
    }
    .quick-btn.active { background: #1d4ed8; color: #fff; border-color: #1d4ed8; }

    .calendar-head {
      display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px;
    }
    .calendar-head h3 { margin: 0; font-size: 18px; }
    .month-nav button {
      border: 1px solid var(--border); background: #fff; border-radius: 8px;
      padding: 4px 10px; cursor: pointer;
    }
    .weekdays, .cells {
      display: grid; grid-template-columns: repeat(7, minmax(0, 1fr)); gap: 6px;
    }
    .weekdays div {
      text-align: center; color: var(--muted); font-size: 12px; padding: 4px 0;
    }
    .cell {
      min-width: 0;
      min-height: 100px;
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 5px 4px 6px;
      background: #fff;
      position: relative;
      overflow: visible;
      cursor: pointer;
      display: flex;
      flex-direction: column;
      align-items: stretch;
    }
    .cell:hover { border-color: #93c5fd; background: #f8fbff; }
    .cell.out { background: #f9fafb; color: #9ca3af; }
    .cell.today { outline: 2px solid var(--blue); }
    .cell.selected { outline: 2px solid #6366f1; background: #eef2ff; box-shadow: inset 0 0 0 1px #c7d2fe; }
    .cell.today.selected { outline: 2px solid #4f46e5; }
    .cell.cell-past {
      opacity: 0.58;
      background: #eceef2;
      border-color: #e2e5ea;
      min-height: 78px;
    }
    .cell.cell-past:hover { background: #e5e8ed; }
    .cell.cell-past .day { color: #9ca3af; }
    .cell.cell-past .tag-list { max-height: 52px; }
    .cell.cell-past .tag { filter: saturate(0.85); }
    .day { font-size: 12px; font-weight: 700; flex-shrink: 0; }
    .tag-list {
      margin-top: 4px;
      flex: 1 1 auto;
      min-height: 0;
      max-height: 110px;
      display: flex;
      flex-direction: column;
      gap: 3px;
      overflow-y: auto;
      -webkit-overflow-scrolling: touch;
    }
    .tag {
      font-size: 10px;
      padding: 3px 5px;
      border-radius: 8px;
      display: block;
      width: 100%;
      max-width: 100%;
      box-sizing: border-box;
      line-height: 1.25;
      word-break: break-word;
      overflow-wrap: anywhere;
      hyphens: auto;
    }
    .tag.red { background: #ffe4e6; color: #9f1239; border: 1px solid #fecdd3; }
    .tag.green { background: #dcfce7; color: #065f46; border: 1px solid #86efac; }
    .tag.holiday { background: #e0e7ff; color: #3730a3; border: 1px solid #c7d2fe; }
    .tag.pretag { background: #ede9fe; color: #5b21b6; border: 1px solid #c4b5fd; font-weight: 700; font-size: 10px; }
    .tag.pretag-soft { background: #f5f3ff; color: #6b7280; border: 1px solid #e9d5ff; font-weight: 600; font-size: 10px; }
    .tag.star { background: #fef3c7; color: #92400e; border: 1px solid #fcd34d; }
    .cal-star {
      display: inline;
      margin-left: 3px;
      font-weight: 800;
      vertical-align: middle;
    }

    .timeline-panel .section-title { margin-top: 0; }
    .event {
      border: 1px solid var(--border); border-radius: 12px; padding: 10px;
      margin-bottom: 10px; cursor: pointer; background: #fff;
    }
    .event:hover { border-color: #cbd5e1; }
    .event.done { opacity: 0.66; }
    .event.event-past {
      opacity: 0.68;
      background: #f3f4f6;
      border-color: #e5e7eb;
    }
    .event.event-past:hover { border-color: #d1d5db; }
    .timeline-upcoming { margin-bottom: 4px; }
    .past-fold {
      margin-top: 8px;
      border: 1px solid var(--border);
      border-radius: 12px;
      background: #f9fafb;
    }
    .past-fold-summary {
      padding: 10px 14px;
      cursor: pointer;
      font-weight: 700;
      font-size: 13px;
      color: #6b7280;
      list-style: none;
      display: flex;
      align-items: center;
      gap: 8px;
      user-select: none;
    }
    .past-fold-summary::-webkit-details-marker { display: none; }
    .past-fold-summary::before {
      content: "▸";
      font-size: 11px;
      color: #9ca3af;
      width: 1em;
    }
    .past-fold[open] > .past-fold-summary::before { content: "▾"; }
    .past-fold[open] > .past-fold-summary {
      border-bottom: 1px solid var(--border);
      background: #f3f4f6;
      color: #4b5563;
    }
    .past-fold-inner { padding: 10px 10px 4px; background: #fafafa; }
    .past-fold-inner .event:last-child { margin-bottom: 8px; }
    .priority-past-fold { margin-top: 12px; }
    .event-head { display: flex; justify-content: space-between; gap: 8px; }
    .event-title { font-weight: 700; font-size: 14px; }
    .event-meta { color: var(--muted); font-size: 12px; margin-top: 4px; }
    .badges { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 6px; }
    .badge {
      font-size: 11px; border-radius: 999px; padding: 2px 8px;
      border: 1px solid var(--border); background: #f9fafb;
    }
    .badge.red { color: #9f1239; border-color: #fecdd3; background: #fff1f2; }
    .badge.green { color: #065f46; border-color: #86efac; background: #f0fdf4; }
    .badge.star { color: #92400e; border-color: #fcd34d; background: #fffbeb; }
    .badge.pre { color: #6d28d9; border-color: #ddd6fe; background: #f5f3ff; }
    .badge.pre-soft { color: #6b7280; border-color: #e5e7eb; background: #f9fafb; }
    .detail h3 { margin-top: 0; }
    .detail ul { margin: 8px 0 0 18px; padding: 0; }
    .detail li { margin-bottom: 6px; }
    .empty { color: var(--muted); padding: 8px 0; }
    @media (max-width: 960px) {
      .layout-split {
        display: flex;
        flex-direction: column;
        gap: 16px;
      }
      .side-rail {
        order: -1;
        position: static;
        max-height: none;
        width: 100%;
      }
      .stream-panel {
        order: 1;
        width: 100%;
      }
      .cell { min-height: 108px; }
      .cell.cell-past { min-height: 80px; }
    }
  </style>
</head>
<body>
  <div class="wrap">
    <div class="title">
      <h1>2026 学期任务可视化</h1>
      <div class="legend">
        <span class="chip"><span class="dot red"></span> 需线下到堂</span>
        <span class="chip"><span class="dot green"></span> 无需到堂</span>
        <span class="chip"><span class="dot star"></span> 成绩相关</span>
      </div>
    </div>

    <section class="panel toolbar" aria-label="筛选">
      <span class="toolbar-label">课程</span>
      <div class="filters toolbar-row" id="courseFilters"></div>
      <div class="row toolbar-row">
        <input id="searchInput" type="search" placeholder="搜索课程代码或关键词（presentation / essay / quiz）" autocomplete="off" />
        <button type="button" id="resetBtn">重置筛选</button>
      </div>
      <div class="filter-toggles toolbar-row">
        <button type="button" id="filterOnsiteBtn" class="quick-btn">仅看需到堂</button>
        <button type="button" id="quickOnlineDDL" class="quick-btn">仅线上提交</button>
        <button type="button" id="filterPreFocusBtn" class="quick-btn">我组 PRE 焦点</button>
      </div>
    </section>

    <section class="panel priority-panel" id="prioritySection" aria-labelledby="priorityHeading"></section>

    <div class="layout-split">
      <main class="panel stream-panel timeline-panel">
        <h2 class="section-title">学期清单</h2>
        <div id="eventList"></div>
      </main>
      <aside class="side-rail" aria-label="月历">
        <div class="panel panel-cal">
          <div class="calendar-head">
            <h3 id="monthLabel" style="margin:0;font-size:16px;"></h3>
            <div class="month-nav">
              <button type="button" id="prevMonth">上月</button>
              <button type="button" id="nextMonth">下月</button>
            </div>
          </div>
          <div class="weekdays">
            <div>一</div><div>二</div><div>三</div><div>四</div><div>五</div><div>六</div><div>日</div>
          </div>
          <div id="cells" class="cells"></div>
        </div>
      </aside>
    </div>
  </div>

  <script>
    const STORAGE_KEY = "semester_planner_done_v1";
    const PAST_FOLD_OPEN_KEY = "semester_planner_past_fold_open_v1";
    const PRIORITY_PAST_FOLD_KEY = "semester_planner_priority_past_fold_v1";
    const doneMap = JSON.parse(localStorage.getItem(STORAGE_KEY) || "{}");

    /** PIA6505 / PIA6065 — Group Project 原文摘自 Introduction_Update.pdf */
    const REF_6505_GROUP_PROJECT_ORIGINAL = [
      "Group Project = Presentation + Final paper",
      "Form your own group.",
      "The number of students in each group should be 5-6 (subject to change according to class size by the end of dropping periods).",
      "Select a topic related to lecture 1-10.",
      "Discuss your proposal with the lecturer in week 10 or earlier.",
      "Group presentation (week 11&12).",
      "Present your proposal.",
      "Who would do the presentation is at your own discretion.",
      "Collect feedbacks and turn the presentation into a term paper.",
      "Final paper (due 11:59pm, 2026-04-28).",
      "A 2000 word original article.",
      "Grade according to its insight, clarity, solidity.",
      "Members within the same group receive the same grade for both group presentation and final paper.",
      "Peer evaluation",
      "If there is free riders in your group, you can request for peer evaluation.",
      "Once peer evaluation is activated, group members would be invited to evaluate each other.",
      "The final score for group presentation and term paper would be adjusted.",
      "Suppose the initial score for the group presentation and term paper is 63",
      "The average peer evaluation score for a group is 7/10",
      "Member A receives an average peer evaluation score of 6/10, his/her final score would be 63*6/7 = 54. → Those performing below the average are punished.",
      "Member B receives an average peer evaluation score of 8/10, his/her final score would be 63*8/7 = 70. → Those performing above the average are rewarded.",
      "The maximum score cannot exceed 70"
    ];
    const REF_6505_GROUP_PROJECT_ZH = [
      "小组项目 = 课堂展示 + 期末论文",
      "自行组队。",
      "每组约 5–6 人（退课期结束后人数可能随班级规模调整）。",
      "选题须与第 1–10 讲相关。",
      "请在第 10 周或更早与任课教师讨论提案。",
      "小组展示安排在第 11–12 周。",
      "展示内容为你们的提案（proposal）。",
      "由谁上台展示由组内自行决定。",
      "收集反馈后，将展示内容发展为期末论文。",
      "期末论文截止时间：2026-04-28 23:59。",
      "约 2000 词的原创文章。",
      "按 insight、clarity、solidity 评分。",
      "同一小组在「小组展示」与「期末论文」上获得相同成绩。",
      "同伴互评（Peer evaluation）",
      "若组内有搭便车成员，可申请启动同伴互评。",
      "一旦启动，组员将互相评分。",
      "展示与期末论文的最终分数会据此调整。",
      "假设展示+论文初始总分为 63。",
      "小组同伴互评平均分为 7/10。",
      "若成员 A 的平均互评分为 6/10，则最终分约为 63×6/7 = 54（低于组平均会被下调）。",
      "若成员 B 的平均互评分为 8/10，则最终分约为 63×8/7 = 70（高于组平均会被上调）。",
      "调整后分数上限为 70。"
    ];

    /** PIA5057 — Group presentation & Term paper 原文摘自 Course Outline (2025-26 B) */
    const REF_5057_GROUP_PRESENTATION_ORIGINAL = [
      "Formal presentation for the group term project.",
      "For the group project, Students (with 5-6 people in each group) are required to give a 20 minute (max.) presentation under the general theme of governance for sustainability in mainland China, Hong Kong and the globe.",
      "The presentations will follow with 3-5-minute Q&A.",
      "The goal of the presentation is to examine how the case relates to and illustrates key course themes and readings.",
      "Slides are required to upload in Canvas in advance by due course."
    ];
    const REF_5057_GROUP_PRESENTATION_ZH = [
      "小组期末项目的正式课堂展示。",
      "小组项目：每组约 5–6 人，须就「中国大陆、香港及全球范围内的可持续治理」这一总主题进行展示，最长 20 分钟。",
      "展示结束后设有约 3–5 分钟问答（Q&A）。",
      "展示旨在审视案例如何与课程核心主题及阅读材料相关联并加以说明。",
      "须在课前截止时间前将幻灯片上传至 Canvas（by due course，以课堂/大纲要求为准）。"
    ];
    const REF_5057_TERM_PAPER_ORIGINAL = [
      "Term paper (Individual Essay)",
      "Students are required to submit an individual term paper (around 3,500 words; not include references and notes). Submit completed papers in soft copies. Please upload your essay on Canvas.",
      "Make sure your essay has a cover page and please include the following information; your full name (underline your surname), and student ID.",
      "Please submit it on or before 11:59 PM, 3 May 2026. All answers to the questions should be supported by arguments, facts and scholarly work. References and citations should be made clearly"
    ];
    const REF_5057_TERM_PAPER_ZH = [
      "期末论文（个人论文，Individual Essay）",
      "学生须提交个人期末论文（约 3500 词；不含参考文献与注释）。提交电子版定稿，并通过 Canvas 上传。",
      "论文须含封面，并写明：全名（姓氏请加下划线）、学号。",
      "请于 2026 年 5 月 3 日 23:59 或之前提交。各题作答须有论点、事实与学术文献支撑；参考文献与引用须清晰标明。"
    ];

    /** PIA5058 — Group presentation & project report / Individual Essay 原文摘自 Course Outline (25-26 B) */
    const REF_5058_GROUP_PRESENTATION_REPORT_ORIGINAL = [
      "Group presentation and project report",
      "Students (with 5-6 people in each group) are required to give an approximate 20-minute (max.) presentation on sustainability issues.",
      "The goal of the presentation and the Q & A is to examine how the case relates to and illustrates key course themes and readings.",
      "Please submit your ppt file on Canvas by due time.",
      "Presentation will be arranged on week-12 and 13 (8 April and 15 April, 2026), the presentation batch will be determined by lucky draw.",
      "The same presenting groups are required to submit the group project report (around 3000 words excluding reference) within ONE week after your presentation.",
      "The topic should be the same as your presentation with enrichment of extended analysis & discussion & argument."
    ];
    const REF_5058_GROUP_PRESENTATION_REPORT_ZH = [
      "小组展示与小组项目报告（Group presentation and project report）",
      "每组约 5–6 人，须就可持续议题进行约 20 分钟（最长）的课堂展示。",
      "展示与问答旨在审视案例如何与课程核心主题及阅读材料相关联并加以说明。",
      "请在截止时间前将 PPT 提交至 Canvas。",
      "展示安排在第 12–13 周（2026 年 4 月 8 日与 4 月 15 日），具体批次由抽签决定。",
      "同一展示小组须在展示后一周内提交小组项目报告（约 3000 词，不含参考文献）。",
      "报告主题须与展示一致，并在此基础上加强延伸分析、讨论与论证。"
    ];
    const REF_5058_INDIVIDUAL_ESSAY_ORIGINAL = [
      "Individual Essay",
      "Students are required to submit an individual paper (around 3,000 words; not include references and notes). Submit completed papers in soft copies. Please upload your essay on Canvas.",
      "Make sure your essay has a cover page and please include the following information; your full name (underline your surname), and student ID.",
      "Please submit it on or before 11:59 PM, 3 May 2026. All answers to the questions should be supported by arguments, facts and scholarly work. References and citations should be made clearly",
      "Citing and Acknowledging Sources",
      "In accordance with the University policy, all work must follow the scholarly procedures of full documentation, acknowledging all references and sources consulted. Written work that does not meet minimum standards of documentation will fail automatically."
    ];
    const REF_5058_INDIVIDUAL_ESSAY_ZH = [
      "个人论文（Individual Essay）",
      "学生须提交个人论文（约 3000 词；不含参考文献与注释）。提交电子版定稿，并通过 Canvas 上传。",
      "论文须含封面，并写明：全名（姓氏请加下划线）、学号。",
      "请于 2026 年 5 月 3 日 23:59 或之前提交。各题作答须有论点、事实与学术文献支撑；参考文献与引用须清晰标明。",
      "引用与致谢来源（Citing and Acknowledging Sources）",
      "依据大学政策，所有作业须完整遵循学术规范，充分注明所参考的文献与来源。未达到最低文献注明标准的书面作业将直接评为不及格。"
    ];

    /** PIA5059 — Final food project 原文摘自 Course Outline 2026 */
    const REF_5059_FINAL_FOOD_PROJECT_ORIGINAL = [
      "Final food project (40%) (due on 8 May)",
      "Each student group should conduct a food research. This research should be related to: food system, food governance, practices of food production/distribution/consumption.",
      "Explain why this is an important issue, what problems you have identified, to what extent these problems have impacted on human wellbeing and sustainability, and what the better solutions are in order to handle the problems.",
      "Research report should be 4500-6000 words (not including references)."
    ];
    const REF_5059_FINAL_FOOD_PROJECT_ZH = [
      "期末食物研究项目（Final food project，占 40%），截止：5 月 8 日。",
      "每组须开展一项食物相关研究；选题须与以下方面相关：食物体系、食物治理，以及食物生产、流通与消费的实践。",
      "须说明：为何这是重要议题；你识别出哪些问题；这些问题在多大程度上影响人类福祉与可持续；以及为应对问题可采取哪些更优方案。",
      "研究报告正文为 4500–6000 词（不含参考文献）。"
    ];

    const events = [
      { date: "2026-03-03", course: "PIA5057", title: "Lecture 7 + In-class group seminar-4", topic: "The role of NGOs", onsite: true, graded: false, type: "class",
        how: ["上课前10分钟到 LI-2510。", "带上本周 reading 标注，准备1个讨论点。", "若被抽到 seminar，控制在 3-5 分钟清晰表达。"] },
      { date: "2026-03-04", course: "PIA5058", title: "Lecture 7", topic: "Incorporating sustainability into national development strategy", onsite: true, graded: false, type: "class",
        how: ["复习上周讲义关键词。", "记下 project 题目可用文献来源。"] },
      { date: "2026-03-05", course: "PIA5059", title: "Field Studies", onsite: true, graded: false, type: "class",
        how: ["小组分工：拍照、访谈、记录。", "按 field report 结构采集材料（观察-问题-反思）。"] },
      { date: "2026-03-06", course: "PIA6505", title: "Week 7: Blended Finance", topic: "The Anatomy of Blended Finance", onsite: true, graded: false, type: "class",
        how: ["课前看 1 篇 blended finance 案例。", "课上记 3 个关键词：risk, leverage, guarantee。"] },
      { date: "2026-03-10", course: "PIA5057", title: "Lecture 8 + seminar-5", topic: "The role of the industry (illustrated by building sector)", onsite: true, graded: false, type: "class",
        how: ["准备 1 页小组发言要点。", "关注与后续 presentation 相关的证据。"] },
      { date: "2026-03-11", course: "PIA5058", title: "Lecture 8", topic: "Pro-environmental behavior and sustainable fashion", onsite: true, graded: false, type: "class",
        how: ["把 group presentation 的框架初稿定下来。"] },
      { date: "2026-03-12", course: "PIA5059", title: "Group presentation（field experiences）", onsite: true, graded: true, type: "presentation",
        how: ["20分钟结构：背景-发现-问题-建议。", "每位组员至少承担1段。", "当晚整理反馈，准备月底 field report。"],
        spec: {
          studentFocus: [
            "小组展示 field experiences 与可持续发展；时长约 20 分钟级（以课堂为准）。",
            "组员分工明确；会后整理反馈，服务 3/31 的 individual field report。",
            "Field report：800–1000 词、3 月底前 Canvas（见 3/31 条目）。"
          ],
          original: [
            "Group presentation on field experiences in relation to sustainable development (per course schedule)."
          ],
          translation: ["按课表进行：小组就田野经历与可持续发展的关系进行课堂展示。"]
        } },
      { date: "2026-03-13", course: "PIA6505", title: "Week 8: MDBs and Guarantees", topic: "Multilateral Development Banks and Guarantees", onsite: true, graded: false, type: "class",
        how: ["预习 guarantee 和 PPP 逻辑。", "课后补1个世界银行案例笔记。"] },
      { date: "2026-03-17", course: "PIA5057", title: "Lecture 9 + seminar-6", topic: "The role of the industry", onsite: true, graded: false, type: "class",
        how: ["结合你组主题，记录可用于 presentation 的证据。"] },
      { date: "2026-03-18", course: "PIA5058", title: "Lecture 9", topic: "Sustainable built environment and green building management", onsite: true, graded: false, type: "class",
        how: ["完成 presentation PPT 的 70% 版本。"] },
      { date: "2026-03-20", course: "PIA6505", title: "Week 9: Innovation in Sustainable Finance", topic: "Innovation in Sustainable Financing", onsite: true, graded: false, type: "class",
        how: ["准备 1 个创新金融工具案例（如 cat bond）。"] },
      { date: "2026-03-21", course: "PIA5059", title: "Group presentation – field experiences", onsite: true, graded: true, type: "presentation",
        how: ["如你组在此批次，确保 PPT 最终版和分工表完成。"],
        spec: {
          studentFocus: [
            "若你组在本批次：完成终版 PPT 与分工；展示后跟进 field report。",
            "同 3/12 批次要求：field experiences × sustainability，约 20 分钟。",
            "3/31 前 individual field report 截止。"
          ],
          original: [
            "Group presentation on field experiences in relation to sustainable development (per course schedule)."
          ],
          translation: ["按课表进行：小组就田野经历与可持续发展的关系进行课堂展示。"]
        } },
      { date: "2026-03-24", course: "PIA5057", title: "Lecture 10", topic: "Discussion with industry experts, part-1", onsite: true, graded: false, type: "class",
        how: ["整理 5057 展示讲稿首版。"] },
      { date: "2026-03-25", course: "PIA5058", title: "Lecture 10", topic: "Inclusive city and sustainable urban mobility", onsite: true, graded: false, type: "class",
        how: ["锁定 4/8 presentation 的故事线和图表。"] },
      { date: "2026-03-26", course: "PIA5059", title: "Food activism 1", onsite: true, graded: false, type: "class",
        how: ["提炼 2 个 food activism 课堂观点，后续可写进 project。"] },
      { date: "2026-03-27", course: "PIA6505", title: "Group presentations（非你组展示日）", onsite: true, graded: true, type: "presentation",
        how: ["你已确认个人 PRE 在 4/10，本场通常非你组上台。", "若到场可记录老师评分偏好，反哺你组展示与 final paper。"],
        spec: {
          studentFocus: [
            "PIA6505：小组项目 = 展示（约第11–12周）+ 期末论文（2026-04-28 23:59，约2000词，组内同分）。",
            "课表上本日为展示窗口之一；你已确认上台在 4/10，今天多为旁听，可记评分点。",
            "选题与第1–10讲相关；建议第10周或更早与老师讨论提案。",
            "可申请同伴互评；开启后展示与论文成绩按细则调整（见下方完整原文）。"
          ],
          original: REF_6505_GROUP_PROJECT_ORIGINAL.concat([
            "",
            "[Syllabus calendar] Tentative schedule: Week 10 (2026-03-27) — Group Presentations."
          ]),
          translation: REF_6505_GROUP_PROJECT_ZH.concat([
            "",
            "[课表说明] 暂定进度：第10周（2026-03-27）— 小组展示。"
          ])
        } },
      { date: "2026-03-31", course: "PIA5057", title: "Lecture 11", topic: "Discussion with industry experts, part-2", onsite: true, graded: false, type: "class",
        how: ["线下到堂参加 Lecture 11。", "课后把展示稿与 term paper 论证结构对齐。"] },
      { date: "2026-03-31", course: "PIA5059", title: "Field report 截止（end of March）", onsite: false, graded: true, type: "submission",
        how: ["提交到 Canvas。", "结构建议：观察->问题->可持续意义->个人反思。", "字数 800-1000；检查引用格式。"],
        spec: {
          studentFocus: [
            "截止：3月底前（end of March），Canvas 提交。",
            "Individual field report，约 800–1000 词。",
            "写清田野事实、与食物/环境议题的联系、个人反思；引用课堂概念会更稳。"
          ],
          original: ["Submit an individual field report on Canvas by end of March (800-1000 words)."],
          translation: ["请于3月底前在 Canvas 提交个人田野报告（800-1000词）。"]
        } },
      { date: "2026-04-01", course: "PIA5058", title: "Lecture 11", topic: "Sustainability and International Environmental Cooperation", onsite: true, graded: false, type: "class",
        how: ["4/8 前最后一次课堂前确认分工与时间控制。"] },
      { date: "2026-04-02", course: "PIA5059", title: "Food activism 2 + In-class writing quiz", topic: "Food activism 2: Food sovereignty and food justice", onsite: true, graded: true, type: "quiz",
        how: ["本节有随堂书面测验：2道 short-essay（个人完成）。", "务必携带黑色圆珠笔（black ball pen）。", "课前完成指定阅读并准备关键论点。"],
        spec: {
          studentFocus: [
            "随堂笔试，个人独立完成；两道 short-essay。",
            "自备黑色圆珠笔（black ball pen）。",
            "课前读完三篇指定 PDF（文件名见本卡 readings）。"
          ],
          original: ["You will answer questions (in writing) individually.", "There will be two short-essay questions.", "Pls prepare a black ball pen."],
          translation: ["你将以书面形式独立作答。", "测验包含两道简答题（short-essay）。", "请准备一支黑色圆珠笔。"]
        },
        readings: [
          "EBSCO-FullText-03_24_2026.pdf",
          "Relational proximity: The search for local food in China.pdf",
          "Characterizing_alternative_foo.pdf"
        ] },
      { date: "2026-04-03", course: "PIA6505", title: "Good Friday（no class）", onsite: false, graded: false, type: "holiday",
        how: ["可用于补作业：优先推进 5058 展示与 5057 展示稿。"] },
      { date: "2026-04-07", course: "PIA5057", title: "Holiday（no lecture）", onsite: false, graded: false, type: "holiday",
        how: ["集中彩排 5057 group presentation。"] },
      { date: "2026-04-08", course: "PIA5058", title: "Group Presentation（已确认你在这天）", onsite: true, graded: true, type: "presentation",
        how: ["提前 30 分钟到教室并检查投屏。", "严格控制总时长（20分钟左右）。", "展示后当天开始写 group report。"],
        spec: {
          studentFocus: [
            "你已确认本日上台：小组 PRE，总时长约 20 分钟级（以课堂为准）。",
            "展示后一周内交 group project report（约3000词不含参考文献，见 4/15）。",
            "当场记反馈，直接映射到报告修改清单。"
          ],
          original: REF_5058_GROUP_PRESENTATION_REPORT_ORIGINAL.concat([
            "",
            "[Course schedule] Your presentation batch: 8 April 2026 (Week 12)."
          ]),
          translation: REF_5058_GROUP_PRESENTATION_REPORT_ZH.concat([
            "",
            "[课表说明] 你所在批次：2026-04-08（第 12 周）。"
          ])
        } },
      { date: "2026-04-09", course: "PIA5059", title: "Conclusion: Sustainable development and food futures", onsite: true, graded: false, type: "class",
        how: ["整理 final project 核心问题和研究路径。"] },
      { date: "2026-04-10", course: "PIA6505", title: "Group presentations（已确认你在这天）", onsite: true, graded: true, type: "presentation",
        how: ["你已确认 6505 PRE 在今天。", "提前 30 分钟到场，完成设备与时长检查。", "准备 3 个高频问答并明确组员分工。"],
        spec: {
          studentFocus: [
            "你已确认：本日为你组展示（Week 12 批次）。",
            "展示小组 proposal；谁上台组内自定。",
            "收集反馈，用于 4/28 final paper（约2000词）；展示与论文小组同分。",
            "同伴互评规则与计分调整见下方完整原文（Introduction_Update.pdf）。"
          ],
          original: REF_6505_GROUP_PROJECT_ORIGINAL.concat([
            "",
            "[Syllabus calendar] Tentative schedule: Week 12 (2026-04-10) — Group Presentations."
          ]),
          translation: REF_6505_GROUP_PROJECT_ZH.concat([
            "",
            "[课表说明] 暂定进度：第12周（2026-04-10）— 小组展示。"
          ])
        } },
      { date: "2026-04-14", course: "PIA5057", title: "Group Presentation Batch 1", onsite: true, graded: true, type: "presentation",
        how: ["若你组在 Batch 1：至少演练2次，准备Q&A。"],
        spec: {
          studentFocus: [
            "若你组在 Batch 1：正式小组项目展示，最长 20 分钟，随后约 3–5 分钟 Q&A。",
            "总主题：中国大陆、香港与全球语境下的可持续治理；须体现案例与课程主题、阅读的关系。",
            "Slides 须在课前截止日前上传 Canvas；个人 term paper 见 5/3 条目。"
          ],
          original: REF_5057_GROUP_PRESENTATION_ORIGINAL.concat([
            "",
            "[Course schedule] Group Presentation — Batch 1."
          ]),
          translation: REF_5057_GROUP_PRESENTATION_ZH.concat(["", "[课表说明] 第一批小组展示。"])
        } },
      { date: "2026-04-15", course: "PIA5058", title: "Class Presentation Batch 2（非你组展示日）", onsite: true, graded: true, type: "presentation",
        how: ["这是 5058 课程的 Batch 2 展示日。", "你已确认在 4/8 展示，今天通常不是你上台。", "是否必须到场以老师课堂要求为准；若不强制，可优先完成报告终稿。"],
        spec: {
          studentFocus: [
            "5058 第二批展示日；你已确认在 4/8 展示，今天通常不是你组。",
            "是否必须到场以老师通知为准；不到场可用来推进 4/15 报告终稿。"
          ],
          original: REF_5058_GROUP_PRESENTATION_REPORT_ORIGINAL.concat([
            "",
            "[Course schedule] Presentation Batch 2: 15 April 2026 (Week 13). You are confirmed on 8 April — today is typically not your group’s slot."
          ]),
          translation: REF_5058_GROUP_PRESENTATION_REPORT_ZH.concat([
            "",
            "[课表说明] 第二批展示：2026-04-15（第 13 周）。你已确认在 4/8 展示，本日一般非你组场次。"
          ])
        } },
      { date: "2026-04-15", course: "PIA5058", title: "Group Project Report 截止（展示后一周）", onsite: false, graded: true, type: "submission",
        how: ["根据 4/8 反馈补强论证。", "约3000词（不含参考文献），按 Canvas 要求提交。"],
        spec: {
          studentFocus: [
            "截止：展示后一周内（你组 4/8 展示 → 本日）。",
            "Group project report，约 3000 词（不含参考文献），Canvas 小组提交。",
            "主题须与 presentation 一致；把课堂质疑与反馈写进论证。"
          ],
          original: REF_5058_GROUP_PRESENTATION_REPORT_ORIGINAL,
          translation: REF_5058_GROUP_PRESENTATION_REPORT_ZH
        } },
      { date: "2026-04-16", course: "PIA5059", title: "Group projects consultation", onsite: true, graded: false, type: "class",
        how: ["带 final project 提纲请老师给意见。"] },
      { date: "2026-04-17", course: "PIA6505", title: "Wrap-up + In-class Quiz", onsite: true, graded: true, type: "exam",
        how: ["带电脑，提前复习 Lecture 1-9。", "按 MCQ 复习法准备错题清单。"] },
      { date: "2026-04-21", course: "PIA5057", title: "Revision week + Group Presentation Batch 2", onsite: true, graded: true, type: "presentation",
        how: ["若你组在 Batch 2：沿用 4/14 评分点做强化。"],
        spec: {
          studentFocus: [
            "若你组在 Batch 2：与 4/14 同一套大纲要求（20 分钟上限、3–5 分钟 Q&A、Canvas 提前交 slides）。",
            "Revision week 场次，留足彩排与 Q&A 分工。",
            "个人 term paper 仍 5/3 截止。"
          ],
          original: REF_5057_GROUP_PRESENTATION_ORIGINAL.concat([
            "",
            "[Course schedule] Group Presentation — Batch 2 (Revision week)."
          ]),
          translation: REF_5057_GROUP_PRESENTATION_ZH.concat(["", "[课表说明] 第二批小组展示（复习周场次）。"])
        } },
      { date: "2026-04-28", course: "PIA6505", title: "Final group paper 截止 23:59", onsite: false, graded: true, type: "submission",
        how: ["2000词；确保引用与图表标注完整。", "至少提前 12 小时提交，避免系统拥堵。"],
        spec: {
          studentFocus: [
            "截止：2026-04-28 23:59。",
            "约 2000 词原创文章；与同组展示同分；评分看 insight、clarity、solidity。",
            "若启用同伴互评，分数按课程说明调整；细则见下方完整原文。"
          ],
          original: REF_6505_GROUP_PROJECT_ORIGINAL,
          translation: REF_6505_GROUP_PROJECT_ZH
        } },
      { date: "2026-05-03", course: "PIA5057", title: "Term paper 截止 23:59", onsite: false, graded: true, type: "submission",
        how: ["约3500词。", "提前一天完成查重与格式检查。"],
        spec: {
          studentFocus: [
            "截止：2026-05-03 23:59，Canvas 上传电子版。",
            "约 3500 词（大纲原文：not include references and notes）；封面须含全名（姓氏下划线）、学号。",
            "论证须有论点、事实与学术文献支撑；引用须写清楚。"
          ],
          original: REF_5057_TERM_PAPER_ORIGINAL,
          translation: REF_5057_TERM_PAPER_ZH
        } },
      { date: "2026-05-03", course: "PIA5058", title: "Individual essay 截止 23:59", onsite: false, graded: true, type: "submission",
        how: ["约3000词。", "和 5057 错峰推进：先定提纲再填内容。"],
        spec: {
          studentFocus: [
            "Individual essay，占课程 40%。",
            "约 3000 词（不含参考文献与注释），Canvas；可持续城市相关议题。",
            "须满足引用与文献注明要求，否则可能直接不及格（见原文 Citing 段）。"
          ],
          original: REF_5058_INDIVIDUAL_ESSAY_ORIGINAL,
          translation: REF_5058_INDIVIDUAL_ESSAY_ZH
        } },
      { date: "2026-05-08", course: "PIA5059", title: "Final food project 截止", onsite: false, graded: true, type: "submission",
        how: ["4500-6000词。", "按大纲写清：重要性、问题、对福祉与可持续的影响、更优方案。", "可融合 field study 与课堂阅读。"],
        spec: {
          studentFocus: [
            "Group final food project，占课程 40%；截止 2026-05-08。",
            "正文 4500–6000 词（不含参考文献）；须扣食物体系/治理/生产—流通—消费。",
            "须回应：为何重要、识别哪些问题、如何影响人类福祉与可持续、更优解决方案。"
          ],
          original: REF_5059_FINAL_FOOD_PROJECT_ORIGINAL,
          translation: REF_5059_FINAL_FOOD_PROJECT_ZH
        } }
    ].sort((a, b) => a.date.localeCompare(b.date));

    const courses = [...new Set(events.map(e => e.course))];
    const courseColors = {
      PIA5057: "#1d4ed8",
      PIA5058: "#7c3aed",
      PIA5059: "#0f766e",
      PIA6505: "#b45309"
    };

    const state = {
      month: 2, // 2026-03
      year: 2026,
      selectedCourses: new Set(courses),
      onlyOnsite: false,
      quickOnlineDDL: false,
      /** 隐藏「非你组展示日」PRE；保留我组已确认 PRE + 未写明末组别的 PRE（如 5057 批次） */
      hideOtherGroupPre: false,
      selectedDate: "",
      currentByDate: {},
      expandedIds: new Set(),
      q: ""
    };

    const todayStr = toDateStr(new Date());

    function toDateStr(d) {
      const y = d.getFullYear();
      const m = String(d.getMonth() + 1).padStart(2, "0");
      const day = String(d.getDate()).padStart(2, "0");
      return `${y}-${m}-${day}`;
    }
    function addDaysStr(dateStr, deltaDays) {
      const [y, m, d] = dateStr.split("-").map(Number);
      const dt = new Date(y, m - 1, d);
      dt.setDate(dt.getDate() + deltaDays);
      return toDateStr(dt);
    }
    function dayOfWeekCn(dateStr) {
      const n = new Date(dateStr + "T00:00:00").getDay();
      return ["周日","周一","周二","周三","周四","周五","周六"][n];
    }
    function dateFmt(dateStr) {
      const [y,m,d] = dateStr.split("-");
      return `${y}-${m}-${d} ${dayOfWeekCn(dateStr)}`;
    }
    function isDone(id) { return !!doneMap[id]; }
    function saveDone() { localStorage.setItem(STORAGE_KEY, JSON.stringify(doneMap)); }

    function eventId(e) { return `${e.date}__${e.course}__${e.title}`; }
    function isOnlineSubmission(e) { return e.type === "submission" && !e.onsite; }
    function isNonGroupPre(e) { return e.type === "presentation" && String(e.title || "").includes("非你组展示日"); }
    function isMyGroupPre(e) { return e.type === "presentation" && String(e.title || "").includes("已确认你在这天"); }
    function renderSpecHtml(spec) {
      if (!spec) return "";
      const ul = arr =>
        arr && arr.length
          ? `<ul style="margin:4px 0 0 18px;line-height:1.45;">${arr.map(x => `<li>${x}</li>`).join("")}</ul>`
          : "";
      const detailsLines = (title, arr) => {
        if (!arr || !arr.length) return "";
        const inner = arr.map(line => `<div style="margin-bottom:6px;">${line}</div>`).join("");
        return `<details style="margin-top:8px;"><summary style="cursor:pointer;font-weight:600;color:#111827;">${title}</summary><div style="margin-top:8px;font-size:12px;line-height:1.55;color:#1f2937;">${inner}</div></details>`;
      };
      const focus =
        spec.studentFocus && spec.studentFocus.length
          ? spec.studentFocus
          : [...(spec.deliverable || []).slice(0, 3), ...(spec.checklist || []).slice(0, 2)].filter(Boolean);
      return `
        <div style="margin-top:10px;border:1px dashed #cbd5e1;background:#f8fafc;border-radius:8px;padding:8px;">
          <div style="font-weight:700;font-size:13px;color:#1e3a8a;">学生要点（占分 · 截止 · 提交物）</div>
          ${ul(focus)}
          ${detailsLines("查看原文要求（老师原文 · 完整）", spec.original)}
          ${detailsLines("查看中文翻译（完整）", spec.translation)}
        </div>
      `;
    }

    function buildEventDetailInner(e) {
      return `
        <h4 style="margin:0 0 6px; font-size:13px;">怎么做（行动清单）</h4>
        <ul style="margin:6px 0 0 18px;">${e.how.map(x => `<li>${x}</li>`).join("")}</ul>
        ${Array.isArray(e.readings) && e.readings.length ? `<div style="margin-top:8px; font-size:12px; color:#6b7280;">指定阅读：${e.readings.join("；")}</div>` : ""}
        ${renderSpecHtml(e.spec)}
      `;
    }

    function filterEvents(all = events) {
      return all.filter(e => {
        if (!state.selectedCourses.has(e.course)) return false;
        if (state.onlyOnsite && !e.onsite) return false;
        if (state.quickOnlineDDL && !isOnlineSubmission(e)) return false;
        if (state.hideOtherGroupPre && isNonGroupPre(e)) return false;
        if (state.q) {
          const hay = `${e.course} ${e.title} ${e.type} ${e.topic || ""}`.toLowerCase();
          if (!hay.includes(state.q.toLowerCase())) return false;
        }
        return true;
      });
    }

    function renderCourseFilters() {
      const el = document.getElementById("courseFilters");
      el.innerHTML = courses.map(c => {
        const checked = state.selectedCourses.has(c) ? "checked" : "";
        return `<label style="border-color:${courseColors[c] || "#ddd"}"><input type="checkbox" data-course="${c}" ${checked}/> ${c}</label>`;
      }).join("");
      el.querySelectorAll("input[data-course]").forEach(input => {
        input.addEventListener("change", () => {
          const c = input.getAttribute("data-course");
          if (input.checked) state.selectedCourses.add(c);
          else state.selectedCourses.delete(c);
          renderAll();
        });
      });
    }

    function jumpMonthIfNeeded(dateStr) {
      const [y, m] = dateStr.split("-").map(Number);
      if (state.year !== y || state.month !== m - 1) {
        state.year = y;
        state.month = m - 1;
        return true;
      }
      return false;
    }

    function scrollToEventRow(id) {
      requestAnimationFrame(() => {
        const row = [...document.querySelectorAll("#eventList .event")].find(
          n => decodeURIComponent(n.getAttribute("data-id")) === id
        );
        row?.scrollIntoView({ behavior: "smooth", block: "nearest" });
      });
    }

    function renderPrioritySection() {
      const el = document.getElementById("prioritySection");
      const pending = filterEvents(events)
        .filter(e => !isDone(eventId(e)))
        .sort((a, b) => a.date.localeCompare(b.date));
      const weekEnd = addDaysStr(todayStr, 7);

      const buildPwItemLi = (e, liExtra) => {
        const id = encodeURIComponent(eventId(e));
        const online = isOnlineSubmission(e) ? `<span class="pw-online-tag">线上DDL</span>` : "";
        const locClass = e.onsite ? "pw-loc-onsite" : "pw-loc-remote";
        const locText = e.onsite ? "需线下到堂" : "无需到堂";
        const graded = e.graded ? `<span class="pw-flag-graded">⭐成绩相关</span>` : "";
        const preMini =
          e.type === "presentation"
            ? isNonGroupPre(e)
              ? `<span class="pw-pre-mini soft">PRE（非你组）</span>`
              : isMyGroupPre(e)
                ? `<span class="pw-pre-mini">我组PRE</span>`
                : `<span class="pw-pre-mini">PRE</span>`
            : "";
        return `<li class="pw-item ${liExtra}" data-pick="${id}" role="button" tabindex="0">
            <span class="pw-date">${e.date.slice(5)}</span>
            <span class="pw-body">
              <span class="pw-line-title"><span class="pw-course">${e.course}</span> · ${e.title}${online}</span>
              <span class="pw-status-row">
                <span class="pw-loc ${locClass}"><span class="pw-dot" aria-hidden="true"></span>${locText}</span>
                ${graded}
                ${preMini}
              </span>
            </span>
          </li>`;
      };

      let html = `<h2 class="priority-panel-title" id="priorityHeading">近期焦点</h2>`;

      if (!pending.length) {
        html += `<p class="empty" style="margin:0;">当前筛选下没有未完成项。可调整课程勾选或快捷筛选。</p>`;
        el.innerHTML = html;
        return;
      }

      const pendingUpcoming = pending.filter(e => e.date >= todayStr);
      const pendingPast = pending.filter(e => e.date < todayStr);

      if (pendingUpcoming.length) {
        const next = pendingUpcoming[0];
        const nid = encodeURIComponent(eventId(next));
        html += `<div class="priority-next" data-pick="${nid}" role="button" tabindex="0">
        <p class="pn-title">${next.graded ? "⭐ " : ""}${next.title}</p>
        <p class="pn-meta">${dateFmt(next.date)} · ${next.course}
          · ${next.onsite ? "🔴 需到堂" : "🟢 无需到堂"}
          ${next.graded ? " · 成绩相关" : ""}
          ${isOnlineSubmission(next) ? " · 📤 线上提交" : ""}</p>
      </div>`;

        const nextId = eventId(next);
        const weekRows = pendingUpcoming.filter(
          e => e.date >= todayStr && e.date <= weekEnd && eventId(e) !== nextId
        );

        html += `<div class="priority-week"><h3 class="priority-week-heading">七日内 · 其它未完成</h3>`;
        if (!weekRows.length) {
          html += `<p class="empty" style="margin:0;">七日内暂无其它未完成，可在下方清单浏览全学期。</p>`;
        } else {
          html += `<ul class="pw-list">${weekRows.map(e => buildPwItemLi(e, "")).join("")}</ul>`;
        }
        html += `</div>`;
      } else {
        html += `<p class="empty" style="margin:0;">暂无未到来待办。</p>`;
      }

      if (pendingPast.length) {
        const priPastOpen = localStorage.getItem(PRIORITY_PAST_FOLD_KEY) === "1";
        html += `<details class="past-fold priority-past-fold" ${priPastOpen ? "open" : ""}>
          <summary class="past-fold-summary">已过去 · ${pendingPast.length} 项（点击展开）</summary>
          <div class="past-fold-inner"><ul class="pw-list">${pendingPast.map(e => buildPwItemLi(e, "pw-item-past")).join("")}</ul></div>
        </details>`;
      }

      el.innerHTML = html;

      const priPastFold = el.querySelector(".priority-past-fold");
      if (priPastFold) {
        priPastFold.addEventListener("toggle", () => {
          localStorage.setItem(PRIORITY_PAST_FOLD_KEY, priPastFold.open ? "1" : "0");
        });
      }

      el.querySelectorAll("[data-pick]").forEach(node => {
        const go = () => {
          const id = decodeURIComponent(node.getAttribute("data-pick"));
          const wasOpen = state.expandedIds.has(id);
          if (wasOpen) state.expandedIds.delete(id);
          else state.expandedIds.add(id);
          const ev = events.find(x => eventId(x) === id);
          if (ev) {
            state.selectedDate = ev.date;
            jumpMonthIfNeeded(ev.date);
            if (ev.date < todayStr) {
              localStorage.setItem(PAST_FOLD_OPEN_KEY, "1");
              localStorage.setItem(PRIORITY_PAST_FOLD_KEY, "1");
            }
          }
          renderAll();
          if (!wasOpen) scrollToEventRow(id);
        };
        node.addEventListener("click", go);
        node.addEventListener("keydown", ev => {
          if (ev.key === "Enter" || ev.key === " ") {
            ev.preventDefault();
            go();
          }
        });
      });
    }

    function syncQuickButtons() {
      document.getElementById("filterOnsiteBtn")?.classList.toggle("active", state.onlyOnsite);
      document.getElementById("quickOnlineDDL")?.classList.toggle("active", state.quickOnlineDDL);
      document.getElementById("filterPreFocusBtn")?.classList.toggle("active", state.hideOtherGroupPre);
    }

    function renderCalendar() {
      const monthNames = ["1月","2月","3月","4月","5月","6月","7月","8月","9月","10月","11月","12月"];
      document.getElementById("monthLabel").textContent = `${state.year}年 ${monthNames[state.month]}`;
      const cells = document.getElementById("cells");
      cells.innerHTML = "";

      const first = new Date(state.year, state.month, 1);
      const last = new Date(state.year, state.month + 1, 0);
      const startPad = (first.getDay() + 6) % 7; // Monday first
      const total = startPad + last.getDate();
      const weeks = Math.ceil(total / 7);
      const count = weeks * 7;

      const visibleEvents = filterEvents(events);
      const byDate = visibleEvents.reduce((m, e) => {
        (m[e.date] ||= []).push(e);
        return m;
      }, {});
      state.currentByDate = byDate;

      for (let i = 0; i < count; i++) {
        const day = i - startPad + 1;
        const cur = new Date(state.year, state.month, day);
        const inMonth = day >= 1 && day <= last.getDate();
        const dStr = toDateStr(cur);
        const item = document.createElement("div");
        item.className =
          "cell" +
          (!inMonth ? " out" : "") +
          (dStr === todayStr ? " today" : "") +
          (inMonth && dStr === state.selectedDate ? " selected" : "") +
          (inMonth && dStr < todayStr ? " cell-past" : "");
        if (inMonth) {
          item.dataset.date = dStr;
          const evs = byDate[dStr] || [];
          const isPastDay = dStr < todayStr;
          const maxTags = isPastDay ? 1 : 3;
          const tags = evs.slice(0, maxTags).map(e => {
            if (e.type === "holiday") {
              return `<div class="tag holiday" title="${e.title}">🟢 放假无课</div>`;
            }
            if (e.type === "presentation") {
              const star = e.graded ? " ⭐" : "";
              const preClass = isNonGroupPre(e) ? "pretag-soft" : "pretag";
              const preText = isNonGroupPre(e) ? "🎤 非你组" : isMyGroupPre(e) ? "🎤 我组PRE" : "🎤 PRE";
              return `<div class="tag ${preClass}" title="${e.course} ${e.title}">${preText}${star}</div>`;
            }
            const cls = e.onsite ? "red" : "green";
            const star = e.graded ? `<span class="cal-star" aria-hidden="true">⭐</span>` : "";
            return `<div class="tag ${cls}" title="${e.course} ${e.title}">${e.course}${star}</div>`;
          }).join("");
          const more =
            evs.length > maxTags ? `<div class="tag" title="另有 ${evs.length - maxTags} 项">+${evs.length - maxTags}项</div>` : "";
          item.innerHTML = `<div class="day">${day}</div><div class="tag-list">${tags}${more}</div>`;
        }
        cells.appendChild(item);
      }
    }

    function renderTimeline() {
      const list = document.getElementById("eventList");
      const evs = filterEvents(events).sort((a, b) => a.date.localeCompare(b.date));
      if (!evs.length) {
        list.innerHTML = `<div class="empty">当前筛选条件下没有事件。</div>`;
        return;
      }

      for (const id of [...state.expandedIds]) {
        const ev = events.find(x => eventId(x) === id);
        if (ev && ev.date < todayStr) state.expandedIds.delete(id);
      }

      const renderEventCard = (e, isPastSlot) => {
        const id = eventId(e);
        const done = isDone(id);
        const expanded = state.expandedIds.has(id);
        const calFocus = !!state.selectedDate && e.date === state.selectedDate;
        const preBadge = !e.type || e.type !== "presentation"
          ? ""
          : isNonGroupPre(e)
            ? `<span class="badge pre-soft">🎤 PRE（非你组）</span>`
            : isMyGroupPre(e)
              ? `<span class="badge pre">🎤 我组 PRE</span>`
              : `<span class="badge pre">🎤 PRE</span>`;
        return `
          <div class="event ${done ? "done" : ""} ${expanded ? "is-expanded" : ""} ${calFocus ? "cal-focus" : ""} ${isPastSlot ? "event-past" : ""}" data-id="${encodeURIComponent(id)}">
            <div class="event-head">
              <div>
                <div class="event-title">${e.title}</div>
                <div class="event-meta">${dateFmt(e.date)} · ${e.course}</div>
                ${e.topic ? `<div class="event-meta" style="color:#4338ca;">主题：${e.topic}</div>` : ""}
              </div>
              <label><input type="checkbox" data-done="${encodeURIComponent(id)}" ${done ? "checked" : ""}/> 完成</label>
            </div>
            <div class="badges">
              <span class="badge ${e.onsite ? "red" : "green"}">${e.onsite ? "🔴需到堂" : "🟢无需到堂"}</span>
              ${e.graded ? `<span class="badge star">⭐成绩相关</span>` : ""}
              ${preBadge}
              <span class="badge">${e.type}</span>
            </div>
            <div class="event-detail-inline">${buildEventDetailInner(e)}</div>
          </div>
        `;
      };

      const upcoming = evs.filter(e => e.date >= todayStr);
      const past = evs.filter(e => e.date < todayStr);
      const pastFoldOpen = localStorage.getItem(PAST_FOLD_OPEN_KEY) === "1";

      let html = "";
      html += `<div class="timeline-upcoming">`;
      if (upcoming.length) {
        html += upcoming.map(e => renderEventCard(e, false)).join("");
      } else {
        html += `<div class="empty">暂无未到来事项（筛选结果可能全部为过去日期）。</div>`;
      }
      html += `</div>`;

      if (past.length) {
        html += `<details class="past-fold" ${pastFoldOpen ? "open" : ""}>
          <summary class="past-fold-summary">已过去 · ${past.length} 项（点击展开）</summary>
          <div class="past-fold-inner">${past.map(e => renderEventCard(e, true)).join("")}</div>
        </details>`;
      }

      list.innerHTML = html;

      const pastFold = list.querySelector(".past-fold");
      if (pastFold) {
        pastFold.addEventListener("toggle", () => {
          localStorage.setItem(PAST_FOLD_OPEN_KEY, pastFold.open ? "1" : "0");
        });
      }

      list.querySelectorAll(".event-detail-inline").forEach(el => {
        el.addEventListener("click", ev => ev.stopPropagation());
      });

      list.querySelectorAll("[data-done]").forEach(cb => {
        cb.addEventListener("click", ev => ev.stopPropagation());
        cb.addEventListener("change", () => {
          const id = decodeURIComponent(cb.getAttribute("data-done"));
          doneMap[id] = cb.checked;
          saveDone();
          renderAll();
        });
      });

      list.querySelectorAll(".event").forEach(card => {
        card.addEventListener("click", ev => {
          if (ev.target.closest("input[type=checkbox]") || ev.target.closest("label")) return;
          const id = decodeURIComponent(card.getAttribute("data-id"));
          const wasOpen = state.expandedIds.has(id);
          if (wasOpen) state.expandedIds.delete(id);
          else state.expandedIds.add(id);
          const evo = events.find(x => eventId(x) === id);
          if (evo) {
            state.selectedDate = evo.date;
            jumpMonthIfNeeded(evo.date);
          }
          renderCalendar();
          renderTimeline();
        });
      });
    }

    function renderAll() {
      renderPrioritySection();
      syncQuickButtons();
      renderCalendar();
      renderTimeline();
    }

    function bindActions() {
      const cells = document.getElementById("cells");
      cells.addEventListener("click", (ev) => {
        const cell = ev.target.closest(".cell[data-date]");
        if (!cell) return;
        const dStr = cell.dataset.date;
        const dayEvs = state.currentByDate[dStr] || [];
        const ids = dayEvs.map(eventId);
        state.selectedDate = dStr;
        if (!ids.length) {
          renderCalendar();
          renderTimeline();
          return;
        }
        if (dStr < todayStr) localStorage.setItem(PAST_FOLD_OPEN_KEY, "1");
        const allOpen = ids.every(id => state.expandedIds.has(id));
        if (allOpen) ids.forEach(id => state.expandedIds.delete(id));
        else ids.forEach(id => state.expandedIds.add(id));
        renderCalendar();
        renderTimeline();
        if (!allOpen && ids[0]) scrollToEventRow(ids[0]);
      });

      document.getElementById("prevMonth").addEventListener("click", () => {
        if (state.month === 0) { state.month = 11; state.year--; }
        else state.month--;
        renderAll();
      });
      document.getElementById("nextMonth").addEventListener("click", () => {
        if (state.month === 11) { state.month = 0; state.year++; }
        else state.month++;
        renderAll();
      });
      document.getElementById("filterOnsiteBtn").addEventListener("click", () => {
        state.onlyOnsite = !state.onlyOnsite;
        renderAll();
      });
      document.getElementById("filterPreFocusBtn").addEventListener("click", () => {
        state.hideOtherGroupPre = !state.hideOtherGroupPre;
        renderAll();
      });
      document.getElementById("searchInput").addEventListener("input", (e) => { state.q = e.target.value.trim(); renderAll(); });
      document.getElementById("quickOnlineDDL").addEventListener("click", () => {
        state.quickOnlineDDL = !state.quickOnlineDDL;
        renderAll();
      });
      document.getElementById("resetBtn").addEventListener("click", () => {
        state.selectedCourses = new Set(courses);
        state.onlyOnsite = false;
        state.quickOnlineDDL = false;
        state.hideOtherGroupPre = false;
        state.selectedDate = "";
        state.expandedIds.clear();
        state.q = "";
        document.getElementById("searchInput").value = "";
        renderCourseFilters();
        renderAll();
      });
    }

    renderCourseFilters();
    bindActions();
    renderAll();
  </script>
</body>
</html>
