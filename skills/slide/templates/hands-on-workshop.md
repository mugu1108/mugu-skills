---
marp: true
theme: default
paginate: true
header: ''
footer: ''
style: |
  section {
    font-family: 'Hiragino Sans', 'Noto Sans JP', sans-serif;
    background-color: #ffffff;
    padding: 50px 60px;
  }
  header { display: none; }
  h1 { font-size: 44px; color: #1f2937; font-weight: 800; margin-bottom: 16px; line-height: 1.3; }
  h2 { font-size: 32px; color: #374151; font-weight: 700; margin-bottom: 16px; }
  h3 { font-size: 26px; color: #4b5563; font-weight: 600; margin-bottom: 12px; }
  p, li { font-size: 22px; line-height: 1.7; color: #374151; }
  ul, ol { margin-left: 24px; }
  li { margin-bottom: 8px; }
  strong { color: #1f2937; font-weight: 700; }
  blockquote { border-left: 4px solid #028090; padding-left: 16px; margin: 16px 0; color: #4b5563; font-size: 22px; }
---

<script src="../../theme/js/tailwindcss-3.0.16.js"></script>
<script src="../../theme/js/tailwind.config.js"></script>

<!-- _class: lead -->
<!-- _paginate: false -->
<!--
_backgroundImage: "linear-gradient(135deg, #028090 0%, #00A896 50%, #02C39A 100%)"
_color: #fff
-->

<div style="text-align: center;">

# {{WORKSHOP_TITLE}}

<p style="font-size: 28px; opacity: 0.9; margin-top: 24px;">{{WORKSHOP_SUBTITLE}}</p>

<p style="font-size: 20px; opacity: 0.7; margin-top: 40px;">{{DATE}} ｜ {{EVENT_NAME}}</p>

</div>

---

# {{HOOK_QUESTION}}

<div style="display: flex; flex-direction: column; gap: 14px; margin-top: 20px;">
  <div style="background: #f9fafb; border-radius: 12px; padding: 18px 24px; border-left: 4px solid #d1d5db;">
    <p style="font-size: 21px; color: #374151;">{{PAIN_POINT_1}}</p>
  </div>
  <div style="background: #f9fafb; border-radius: 12px; padding: 18px 24px; border-left: 4px solid #d1d5db;">
    <p style="font-size: 21px; color: #374151;">{{PAIN_POINT_2}}</p>
  </div>
  <div style="background: #f9fafb; border-radius: 12px; padding: 18px 24px; border-left: 4px solid #d1d5db;">
    <p style="font-size: 21px; color: #374151;">{{PAIN_POINT_3}}</p>
  </div>
</div>

<div style="background: #f0fdf9; border-radius: 12px; padding: 18px 24px; margin-top: 24px; text-align: center;">
  <p style="font-size: 22px; color: #028090; font-weight: 700;">{{BRIDGE_MESSAGE}}</p>
</div>

---

# {{CONCEPT_TITLE}}

<div style="background: #f0fdf9; border-radius: 16px; padding: 28px 32px; margin-top: 12px; border-left: 6px solid #028090;">
  <p style="font-size: 26px; color: #1f2937; line-height: 1.6;">{{CONCEPT_DEFINITION}}</p>
</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 24px;">
  <div style="background: #f9fafb; border-radius: 12px; padding: 20px;">
    <p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 8px;">{{CONCEPT_LEFT_LABEL}}</p>
    <p style="font-size: 20px; color: #1f2937; font-weight: 600;">{{CONCEPT_LEFT_CONTENT}}</p>
  </div>
  <div style="background: #f9fafb; border-radius: 12px; padding: 20px;">
    <p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 8px;">{{CONCEPT_RIGHT_LABEL}}</p>
    <p style="font-size: 20px; color: #1f2937; font-weight: 600;">{{CONCEPT_RIGHT_CONTENT}}</p>
  </div>
</div>

---

# {{OVERVIEW_TITLE}}

<p style="font-size: 20px; color: #6b7280; margin-bottom: 8px;">{{OVERVIEW_SUBTITLE}}</p>

<!-- SVGフロー図を images/ に作成して埋め込む -->
<!-- <img src="images/{{FLOW_DIAGRAM}}.svg" style="width: 100%; max-height: 360px; object-fit: contain;"> -->

<div style="background: #f0fdf9; border-radius: 12px; padding: 14px 20px; margin-top: 12px; text-align: center;">
  <p style="font-size: 19px; color: #028090; font-weight: 600;">{{OVERVIEW_FOOTER}}</p>
</div>

---

# {{CASE_STUDY_TITLE}}

<p style="font-size: 20px; color: #6b7280; margin-bottom: 12px;">{{CASE_STUDY_SUBTITLE}}</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
  <div>
    <p style="font-size: 16px; color: #991b1b; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px;">{{CASE_PROBLEM_LABEL}}</p>
    <div style="display: flex; flex-direction: column; gap: 8px;">
      <div style="background: #fef2f2; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{CASE_PROBLEM_1}}</p>
      </div>
      <div style="background: #fef2f2; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{CASE_PROBLEM_2}}</p>
      </div>
      <div style="background: #fef2f2; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{CASE_PROBLEM_3}}</p>
      </div>
    </div>
  </div>
  <div style="background: #f0fdf9; border: 2px solid #028090; border-radius: 16px; padding: 24px;">
    <p style="font-size: 16px; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px; color: #028090;">{{CASE_SOLUTION_LABEL}}</p>
    <div style="display: flex; flex-direction: column; gap: 10px;">
      <div style="background: white; border-radius: 10px; padding: 12px 16px;">
        <p style="font-size: 18px; font-weight: 600; color: #374151;">{{CASE_SOLUTION_1}}</p>
      </div>
      <div style="background: white; border-radius: 10px; padding: 12px 16px;">
        <p style="font-size: 18px; font-weight: 600; color: #374151;">{{CASE_SOLUTION_2}}</p>
      </div>
      <div style="background: white; border-radius: 10px; padding: 12px 16px;">
        <p style="font-size: 18px; font-weight: 600; color: #374151;">{{CASE_SOLUTION_3}}</p>
      </div>
    </div>
  </div>
</div>

---

# Step 1 {{STEP_1_TITLE}}

<p style="font-size: 20px; color: #6b7280; margin-bottom: 16px;">{{STEP_1_SUBTITLE}}</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
  <div>
    <p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px;">{{STEP_1_LEFT_LABEL}}</p>
    <div style="display: flex; flex-direction: column; gap: 10px;">
      <div style="background: #f9fafb; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{STEP_1_ITEM_1}}</p>
      </div>
      <div style="background: #f9fafb; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{STEP_1_ITEM_2}}</p>
      </div>
    </div>
  </div>
  <div style="background: #f0fdf9; border: 2px solid #028090; border-radius: 16px; padding: 24px;">
    <p style="font-size: 22px; font-weight: 700; margin-bottom: 12px; color: #028090;">{{STEP_1_TIP_TITLE}}</p>
    <p style="font-size: 18px; line-height: 1.8; color: #374151;">{{STEP_1_TIP_CONTENT}}</p>
  </div>
</div>

---

# Step 2 {{STEP_2_TITLE}}

<p style="font-size: 20px; color: #6b7280; margin-bottom: 12px;">{{STEP_2_SUBTITLE}}</p>

<!-- 会話UIパターン: AIとの対話を示す場合に使用 -->
<div style="background: #f9fafb; border-radius: 16px; padding: 24px 28px;">
  <p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 16px;">{{STEP_2_CONVERSATION_LABEL}}</p>
  <div style="display: flex; flex-direction: column; gap: 10px;">
    <div style="display: flex; align-items: center; gap: 12px;">
      <span style="background: #e5e7eb; border-radius: 8px; padding: 4px 10px; font-size: 13px; font-weight: 700; color: #6b7280; white-space: nowrap;">{{USER_LABEL}}</span>
      <div style="background: white; border-radius: 12px; padding: 12px 16px; box-shadow: 0 1px 3px rgba(0,0,0,0.08); flex: 1;">
        <p style="font-size: 18px; color: #374151;">{{STEP_2_USER_1}}</p>
      </div>
    </div>
    <div style="display: flex; align-items: center; gap: 12px;">
      <span style="background: #028090; border-radius: 8px; padding: 4px 10px; font-size: 13px; font-weight: 700; color: white; white-space: nowrap;">AI</span>
      <div style="background: #f0fdf9; border-radius: 12px; padding: 12px 16px; flex: 1;">
        <p style="font-size: 18px; color: #374151;">{{STEP_2_AI_1}}</p>
      </div>
    </div>
  </div>
</div>

---

# Step 3 {{STEP_3_TITLE}}

<p style="font-size: 20px; color: #6b7280; margin-bottom: 16px;">{{STEP_3_SUBTITLE}}</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
  <div>
    <p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px;">{{STEP_3_LEFT_LABEL}}</p>
    <!-- ここにモックアップやコード例を配置 -->
  </div>
  <div>
    <p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px;">{{STEP_3_RIGHT_LABEL}}</p>
    <div style="display: flex; flex-direction: column; gap: 12px;">
      <div style="background: #f9fafb; border-radius: 10px; padding: 16px;">
        <p style="font-size: 20px; color: #1f2937; font-weight: 600;">{{STEP_3_ACTION_1}}</p>
      </div>
      <div style="background: #f9fafb; border-radius: 10px; padding: 16px;">
        <p style="font-size: 20px; color: #1f2937; font-weight: 600;">{{STEP_3_ACTION_2}}</p>
      </div>
      <div style="background: #f9fafb; border-radius: 10px; padding: 16px;">
        <p style="font-size: 20px; color: #1f2937; font-weight: 600;">{{STEP_3_ACTION_3}}</p>
      </div>
    </div>
  </div>
</div>

---

# {{TIPS_TITLE}}

<p style="font-size: 20px; color: #6b7280; margin-bottom: 16px;">{{TIPS_SUBTITLE}}</p>

<div style="display: flex; flex-direction: column; gap: 14px;">
  <div style="display: grid; grid-template-columns: 56px 1fr; gap: 16px; align-items: center; background: #f0fdf9; border-radius: 14px; padding: 18px 20px; border-left: 4px solid #028090;">
    <div style="width: 48px; height: 48px; background: #028090; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="font-size: 22px; color: white; font-weight: 800;">1</span>
    </div>
    <div>
      <p style="font-size: 20px; color: #1f2937; font-weight: 700;">{{TIP_1_TITLE}}</p>
      <p style="font-size: 16px; color: #6b7280; margin-top: 4px;">{{TIP_1_DETAIL}}</p>
    </div>
  </div>
  <div style="display: grid; grid-template-columns: 56px 1fr; gap: 16px; align-items: center; background: #f0fdf9; border-radius: 14px; padding: 18px 20px; border-left: 4px solid #00A896;">
    <div style="width: 48px; height: 48px; background: #00A896; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="font-size: 22px; color: white; font-weight: 800;">2</span>
    </div>
    <div>
      <p style="font-size: 20px; color: #1f2937; font-weight: 700;">{{TIP_2_TITLE}}</p>
      <p style="font-size: 16px; color: #6b7280; margin-top: 4px;">{{TIP_2_DETAIL}}</p>
    </div>
  </div>
  <div style="display: grid; grid-template-columns: 56px 1fr; gap: 16px; align-items: center; background: #f0fdf9; border-radius: 14px; padding: 18px 20px; border-left: 4px solid #02C39A;">
    <div style="width: 48px; height: 48px; background: #02C39A; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="font-size: 22px; color: white; font-weight: 800;">3</span>
    </div>
    <div>
      <p style="font-size: 20px; color: #1f2937; font-weight: 700;">{{TIP_3_TITLE}}</p>
      <p style="font-size: 16px; color: #6b7280; margin-top: 4px;">{{TIP_3_DETAIL}}</p>
    </div>
  </div>
</div>

---

<!-- _class: lead -->
<!-- _paginate: false -->
<!--
_backgroundImage: "linear-gradient(135deg, #028090 0%, #00A896 50%, #02C39A 100%)"
_color: #fff
-->

<div style="text-align: center;">

# {{CLOSING_MESSAGE}}

<p style="font-size: 24px; opacity: 0.9; margin-top: 24px;">{{CLOSING_SUBTITLE}}</p>

<p style="font-size: 20px; opacity: 0.7; margin-top: 32px;">{{CLOSING_CTA}}</p>

</div>
