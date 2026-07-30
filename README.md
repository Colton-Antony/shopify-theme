# 🛍️ Hallmark UK — Shopify OS 2.0 Performance & AOV Audit

A technical performance audit and native component implementation designed to improve conversion rates, boost Average Order Value (AOV), and reduce reliance on third-party app bloat for Shopify OS 2.0 themes.

---

## 🚀 Key Optimization: Native Cart Drawer Upsell

### **Problem Statement**
Many Shopify stores rely on heavy third-party upsell apps that inject render-blocking JavaScript, introduce external API dependencies, and bloat the DOM. This hurts Core Web Vitals (specifically INP and LCP) and negatively impacts conversion rates.

### **Engineering Solution**
Replaced third-party app reliance with a native, zero-dependency Liquid and JavaScript upsell component embedded directly inside the theme's Ajax cart drawer.

* **Performance First:** 0 external HTTP requests, native theme styling, and minimal DOM footprint.
* **Merchant UX (No-Code Control):** Integrated custom settings into `config/settings_schema.json` so non-technical merchandising teams can select and change upsell products directly via the Shopify Theme Customizer.
* **Dynamic Inventory Logic:** Automatically checks cart state to prevent suggesting items already present in the user's cart.

---

## 🛠️ Tech Stack & Architecture

* **Platform:** Shopify OS 2.0 (Liquid Engine)
* **Frontend:** Vanilla JS (Fetch API), Native CSS, HTML5
* **Version Control:** Git / GitHub Flow

### Key Project Structure
```text
├── config/
│   └── settings_schema.json     # Schema additions for Theme Customizer product selector
├── sections/
│   └── cart-drawer.liquid       # Injection point for cart upsell render tag
└── snippets/
    └── cart-drawer-upsell.liquid # Isolated upsell logic, conditional checks, & markup
