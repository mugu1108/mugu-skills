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

# {{PRODUCT_NAME}}

<p style="font-size: 28px; opacity: 0.9; margin-top: 24px;">{{PRODUCT_TAGLINE}}</p>

<p style="font-size: 20px; opacity: 0.7; margin-top: 40px;">{{DATE}} ｜ {{PRESENTER}}</p>

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

# {{PRODUCT_NAME}}とは

<div style="background: #f0fdf9; border-radius: 16px; padding: 28px 32px; margin-top: 12px; border-left: 6px solid #028090;">
  <p style="font-size: 26px; color: #1f2937; line-height: 1.6;">{{PRODUCT_DEFINITION}}</p>
</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-top: 24px;">
  <div style="background: #f9fafb; border-radius: 12px; padding: 20px;">
    <p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 8px;">{{STRENGTH_LABEL}}</p>
    <p style="font-size: 20px; color: #1f2937; font-weight: 600;">{{STRENGTH_CONTENT}}</p>
    <p style="font-size: 17px; color: #6b7280; margin-top: 4px;">{{STRENGTH_DETAIL}}</p>
  </div>
  <div style="background: #f9fafb; border-radius: 12px; padding: 20px;">
    <p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 8px;">{{DIFFERENTIATOR_LABEL}}</p>
    <p style="font-size: 20px; color: #1f2937; font-weight: 600;">{{DIFFERENTIATOR_CONTENT}}</p>
    <p style="font-size: 17px; color: #6b7280; margin-top: 4px;">{{DIFFERENTIATOR_DETAIL}}</p>
  </div>
</div>

---

# {{COMPARISON_TITLE}}

<p style="font-size: 20px; color: #6b7280; margin-bottom: 12px;">{{COMPARISON_SUBTITLE}}</p>

<!-- SVG比較図を images/ に作成して埋め込む -->
<!-- <img src="images/{{COMPARISON_DIAGRAM}}.svg" style="width: 100%; max-height: 420px; object-fit: contain;"> -->

---

# 機能1 {{FEATURE_1_NAME}}

<p style="font-size: 20px; color: #6b7280; margin-bottom: 16px;">{{FEATURE_1_SUBTITLE}}</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
  <div>
    <p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px;">{{FEATURE_1_LEFT_LABEL}}</p>
    <div style="display: flex; flex-direction: column; gap: 10px;">
      <div style="background: #f9fafb; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{FEATURE_1_POINT_1}}</p>
      </div>
      <div style="background: #f9fafb; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{FEATURE_1_POINT_2}}</p>
      </div>
    </div>
  </div>
  <div style="background: #f0fdf9; border: 2px solid #028090; border-radius: 16px; padding: 24px;">
    <p style="font-size: 16px; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px; color: #028090;">{{FEATURE_1_RIGHT_LABEL}}</p>
    <p style="font-size: 18px; line-height: 1.8; color: #374151;">{{FEATURE_1_BENEFIT}}</p>
  </div>
</div>

---

# 機能2 {{FEATURE_2_NAME}}

<p style="font-size: 20px; color: #6b7280; margin-bottom: 16px;">{{FEATURE_2_SUBTITLE}}</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
  <div style="background: #f0fdf9; border: 2px solid #028090; border-radius: 16px; padding: 24px;">
    <p style="font-size: 16px; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px; color: #028090;">{{FEATURE_2_LEFT_LABEL}}</p>
    <p style="font-size: 18px; line-height: 1.8; color: #374151;">{{FEATURE_2_BENEFIT}}</p>
  </div>
  <div>
    <p style="font-size: 16px; color: #028090; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px;">{{FEATURE_2_RIGHT_LABEL}}</p>
    <div style="display: flex; flex-direction: column; gap: 10px;">
      <div style="background: #f9fafb; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{FEATURE_2_POINT_1}}</p>
      </div>
      <div style="background: #f9fafb; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{FEATURE_2_POINT_2}}</p>
      </div>
    </div>
  </div>
</div>

---

# {{USECASE_TITLE}}

<p style="font-size: 20px; color: #6b7280; margin-bottom: 12px;">{{USECASE_SUBTITLE}}</p>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
  <div>
    <p style="font-size: 16px; color: #991b1b; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px;">{{USECASE_BEFORE_LABEL}}</p>
    <div style="display: flex; flex-direction: column; gap: 8px;">
      <div style="background: #fef2f2; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{USECASE_BEFORE_1}}</p>
      </div>
      <div style="background: #fef2f2; border-radius: 10px; padding: 14px 18px;">
        <p style="font-size: 18px; color: #374151;">{{USECASE_BEFORE_2}}</p>
      </div>
    </div>
  </div>
  <div style="background: #f0fdf9; border: 2px solid #028090; border-radius: 16px; padding: 24px;">
    <p style="font-size: 16px; font-weight: 700; letter-spacing: 1px; margin-bottom: 12px; color: #028090;">{{USECASE_AFTER_LABEL}}</p>
    <div style="display: flex; flex-direction: column; gap: 10px;">
      <div style="background: white; border-radius: 10px; padding: 12px 16px;">
        <p style="font-size: 18px; font-weight: 600; color: #374151;">{{USECASE_AFTER_1}}</p>
      </div>
      <div style="background: white; border-radius: 10px; padding: 12px 16px;">
        <p style="font-size: 18px; font-weight: 600; color: #374151;">{{USECASE_AFTER_2}}</p>
      </div>
    </div>
  </div>
</div>

---

# まとめ

<div style="display: flex; flex-direction: column; gap: 14px;">
  <div style="display: grid; grid-template-columns: 56px 1fr; gap: 16px; align-items: center; background: #f0fdf9; border-radius: 14px; padding: 18px 20px; border-left: 4px solid #028090;">
    <div style="width: 48px; height: 48px; background: #028090; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="font-size: 22px; color: white; font-weight: 800;">1</span>
    </div>
    <div>
      <p style="font-size: 20px; color: #1f2937; font-weight: 700;">{{TAKEAWAY_1}}</p>
      <p style="font-size: 16px; color: #6b7280; margin-top: 4px;">{{TAKEAWAY_1_DETAIL}}</p>
    </div>
  </div>
  <div style="display: grid; grid-template-columns: 56px 1fr; gap: 16px; align-items: center; background: #f0fdf9; border-radius: 14px; padding: 18px 20px; border-left: 4px solid #00A896;">
    <div style="width: 48px; height: 48px; background: #00A896; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="font-size: 22px; color: white; font-weight: 800;">2</span>
    </div>
    <div>
      <p style="font-size: 20px; color: #1f2937; font-weight: 700;">{{TAKEAWAY_2}}</p>
      <p style="font-size: 16px; color: #6b7280; margin-top: 4px;">{{TAKEAWAY_2_DETAIL}}</p>
    </div>
  </div>
  <div style="display: grid; grid-template-columns: 56px 1fr; gap: 16px; align-items: center; background: #f0fdf9; border-radius: 14px; padding: 18px 20px; border-left: 4px solid #02C39A;">
    <div style="width: 48px; height: 48px; background: #02C39A; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
      <span style="font-size: 22px; color: white; font-weight: 800;">3</span>
    </div>
    <div>
      <p style="font-size: 20px; color: #1f2937; font-weight: 700;">{{TAKEAWAY_3}}</p>
      <p style="font-size: 16px; color: #6b7280; margin-top: 4px;">{{TAKEAWAY_3_DETAIL}}</p>
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

<p style="font-size: 24px; opacity: 0.9; margin-top: 24px;">{{CLOSING_CTA}}</p>

</div>
