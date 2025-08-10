# Shopify Custom Support Widget

A fully customizable floating support widget for Shopify stores that lets customers:
- Chat via WhatsApp
- Call directly
- Write via Contact Us form

This widget is controlled via the Shopify Theme Editor and is **completely theme snippets-based**.

---

## 🚀 Features
- Enable/disable widget globally
- Toggle **Chat Us**, **Call Us**, **Write Us** buttons individually
- Custom WhatsApp and Call numbers
- Fully customizable colors for background, text, and icons
- Responsive design for mobile and desktop
- Smooth open/close animation

---

## 📂 File Structure
You will create:
- /snippets/support-widget.liquid
- /assets/whatsapp.svg
- /assets/call.svg
- /assets/mail.svg
- /assets/chat-icon.svg

---

## 🛠 Installation

### 1. Create the Widget Snippet
1. In your Shopify admin, go to **Online Store > Themes > Edit Code**.
2. Inside the **Snippets** folder, create a new file:  
   `support-widget.liquid`
3. Paste the provided widget code into that file (HTML, CSS, JS).

---

### 2. Add SVG Assets
You will need to create the following files inside your **Assets** folder:

#### `/assets/whatsapp.svg`
```svg
<svg xmlns="http://www.w3.org/2000/svg" class="widget_icon__svg" width="25" height="25"
     viewBox="0 0 256 256" role="img" aria-hidden="false">
  <title>WhatsApp</title>
  <path fill="currentColor" d="M128 0C57.3 0 0 57.3 0 128
    c0 22.6 6 44.7 17.5 64.1L0 256l66.1-17.4
    C85 250.1 106.3 256 128 256
    c70.7 0 128-57.3 128-128S198.7 0 128 0zm0 234.7
    c-19.7 0-39-5.3-55.8-15.3l-3.9-2.3-39.2 10.3
    10.4-38.1-2.5-3.9c-10.5-16.5-16.1-35.6-16.1-55.4
    0-57.2 46.6-103.8 103.8-103.8 27.7 0 53.7 10.8 73.2 30.3
    19.5 19.5 30.3 45.5 30.3 73.2 0 57.2-46.6 103.8-103.8 103.8zm60.9-77
    c-3.3-1.7-19.6-9.7-22.6-10.8-3-.9-5.2-1.7-7.4 1.7
    -2.2 3.3-8.5 10.8-10.4 13s-3.7 2.5-6.9.8c-19.7-9.8-32.6-17.4-45.5-39
    -3.4-5.8 3.4-5.4 9.8-17.9 1.1-2.1.6-3.9-.3-5.6
    -.9-1.7-7.4-17.8-10.1-24.3-2.7-6.5-5.5-5.6-7.4-5.7
    -1.9-.1-4.1-.1-6.3-.1s-5.8.8-8.8 3.9c-3 3.3-11.5 11.2-11.5 27.3
    0 16.1 11.8 31.6 13.4 33.7 1.6 2.1 23.2 35.4 56.2 49.6
    7.9 3.4 14.1 5.5 18.9 7.1 7.9 2.5 15.1 2.2 20.8 1.3
    6.3-.9 19.6-8 22.4-15.7 2.8-7.7 2.8-14.3 1.9-15.7
    -.8-1.3-3-2.1-6.3-3.8z"/>
</svg>
```
#### `/assets/call.svg`
```svg
<!-- Outline call icon -->
<svg xmlns="http://www.w3.org/2000/svg" class="widget_icon__svg" width="25" height="25" fill="none"
     viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"
     stroke-linecap="round" stroke-linejoin="round" role="img" aria-hidden="false">
  <title>Call</title>
  <path d="M22 16.92v3a2 2 0 0 1-2.18 2
           19.79 19.79 0 0 1-8.63-3.07
           19.5 19.5 0 0 1-6-6
           19.79 19.79 0 0 1-3.07-8.63
           A2 2 0 0 1 4.11 2h3
           a2 2 0 0 1 2 1.72
           c.12.81.37 1.6.72 2.34
           a2 2 0 0 1-.45 2.11L8.09 9.91
           a16 16 0 0 0 6 6l1.74-1.31
           a2 2 0 0 1 2.11-.45
           c.74.35 1.53.6 2.34.72
           a2 2 0 0 1 1.72 2.03z"/>
</svg>
```
#### `/assets/mail.svg`
```svg
<!-- Mail outline icon -->
<svg xmlns="http://www.w3.org/2000/svg" class="widget_icon__svg" width="25" height="25" fill="none"
     viewBox="0 0 24 24" stroke="currentColor" stroke-width="2"
     stroke-linecap="round" stroke-linejoin="round" role="img" aria-hidden="false">
  <title>Mail</title>
  <path d="M4 4h16a2 2 0 0 1 2 2v12a2 2 0 0 1-2 2H4
           a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2z"/>
  <polyline points="22,6 12,13 2,6"/>
</svg>
```
#### `/assets/chat-icon.svg`
```svg
<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="false" role="img">
  <title>Chat</title>
  <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/>
  <circle cx="8" cy="10" r="1"/>
  <circle cx="12" cy="10" r="1"/>
  <circle cx="16" cy="10" r="1"/>
</svg>
```
---

### 3. Add Schema in `settings-schema.json`
The provided schema should be added at the bottom of the file
```json
,{
    "name": "Custom Support Widget",
    "settings": [
      {
        "type": "checkbox",
        "id": "enable_chat_widget",
        "label": "Enable Custom Chat Widget",
        "default": false
      },
      {
        "type": "text",
        "id": "support_title",
        "label": "Support Inbox Title",
        "default": "Support Inbox"
      },
      {
        "type": "checkbox",
        "id": "enable_chat_us",
        "label": "Enable Chat Us Option",
        "default": true
      },
      {
        "type": "text",
        "id": "chat_us_text",
        "label": "Chat Us Text",
        "default": "Chat Us"
      },
      {
        "type": "text",
        "id": "chat_number",
        "label": "WhatsApp Number",
        "placeholder": "919876543210",
        "info": "Use your Support Business number with Country Code without plus icon(Ex: 919876543210)"
      },
      {
        "type": "text",
        "id": "call_us_text",
        "label": "Call Us Text",
        "default": "Call Us"
      },
      {
        "type": "checkbox",
        "id": "enable_call_us",
        "label": "Enable Call Us",
        "default": true
      },
      {
        "type": "text",
        "id": "call_number",
        "label": "Phone Number",
        "placeholder": "+919876543210",
        "info": "Use your Support Business number with Country Code(Ex: +919876543210)"
      },
      {
        "type": "checkbox",
        "id": "enable_write_us",
        "label": "Enable Write Us",
        "default": true,
        "info": "When this is enabled, customers will be redirected to the Contact Us page when they click it."
      },
      {
        "type": "text",
        "id": "write_us_text",
        "label": "Write Text",
        "default": "Write Us"
      },
      {
        "type": "color",
        "id": "widget_color",
        "label": "Chat Widget color",
        "default": "#16c958"
      },
      {
        "type": "color",
        "id": "bg_color",
        "label": "Primary Background color",
        "default": "#16c958"
      },
      {
        "type": "color",
        "id": "heading_color",
        "label": "Heading Color",
        "default": "#ffffff"
      },
      {
        "type": "color",
        "id": "text_color",
        "label": "Text and Icon Color",
        "default": "#16c958"
      }
    ]
  }
```
---

### 4. Render in `theme.liquid`
You will need to create the following files inside your **Assets** folder:
To conditionally display the widget:
- Open layout/theme.liquid
- Before the closing </body> tag, add:

```liquid
{% if settings.enable_chat_widget %}
  {% section 'support-widget' %}
{% endif %}
```
---

### 🎨 Customization

- Change colors from the Shopify Theme Editor
- Update WhatsApp/Call numbers from Theme Editor
- Toggle which contact options are visible

---

### 🎨 Preview

<img width="1896" height="752" alt="image" src="https://github.com/user-attachments/assets/9599b8fe-e2ae-4d82-ab9e-2f4b1415d259" />

---

## 🐛 Found a Bug?

If you found any bugs in the code, feel free to:

- 📬 Reach out via email: [santhoshkumarb1309@gmail.com](mailto:santhoshkumarb1309@gmail.com)
- 🐙 Open an issue on GitHub: [GitHub Issues](https://github.com/iamsansk/Shopify-Custom-Freebie/issues)

Your feedback is always appreciated!

---

