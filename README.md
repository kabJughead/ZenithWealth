# Zenith Wealth

เว็บไซต์ Landing Page สำหรับทีม **Zenith Wealth** (สำนักงานตัวแทน Samsung Life Insurance สาขาเดอะแจ๊ส รามอินทรา) ใช้แนะนำอาชีพตัวแทนประกันชีวิต โครงสร้างผลตอบแทน คลิปสอน/ติวสอบ และช่องทางติดต่อ สำหรับผู้สนใจสมัครเข้าร่วมทีม

**Live Demo:** https://my-web-test-newv.onrender.com/

![Hero](images/%E0%B8%A3%E0%B8%B9%E0%B8%9B%E0%B8%AA%E0%B9%88%E0%B8%A7%E0%B8%99Hero.png)

> **Disclaimer:** เว็บไซต์นี้จัดทำขึ้นเพื่อใช้ภายในทีม Zenith Wealth เท่านั้น และไม่ใช่เว็บไซต์ของบริษัท ซัมซุง ประกันชีวิต (ประเทศไทย) จำกัด (มหาชน) โดยตรง

---

## Key Features

- **Hero Section** พร้อมปุ่มโทร และปุ่มแอดไลน์ในคลิกเดียว
- **ตัวเลขสรุปและโครงสร้างตัวแทน** แสดงด้วยการ์ดสถิติและภาพอินโฟกราฟิก
- **10 จุดเด่นของอาชีพ** เช่น รายได้ต่อเนื่อง ทำงานออนไลน์ ไม่ต้องลงทุน มีระบบสนับสนุน
- **คลังสื่อการสอน**
  - ติวสอบตัวแทนฟรี (ออนไลน์ผ่าน Zoom) พร้อมคลิปตัวอย่างจาก YouTube
  - วิธีลงทะเบียน E-licensing และเอกสารที่ใช้สมัคร
  - วิดีโอ KASH ที่เปิดดูในหน้าต่าง Modal โดยกำหนดช่วงเวลาเริ่ม–จบของคลิปได้
  - Playlist แบบประกันต่าง ๆ
- **แนะนำพี่เลี้ยง/ทีมผู้บริหาร** พร้อมวุฒิการศึกษาและรางวัล
- **ช่องทางติดต่อ** โทร อีเมล LINE ที่อยู่ และแผนที่ Google Maps แบบฝัง
- **Responsive** รองรับทั้งมือถือ แท็บเล็ต และเดสก์ท็อป พร้อมเมนูมือถือ

### UX Details

- แถบแสดงความคืบหน้าการเลื่อนหน้า (Scroll Progress Bar)
- ปุ่มกลับขึ้นด้านบน (Back to Top) และปุ่มลอยสำหรับ LINE / โทร / Facebook
- Smooth scroll และการไฮไลต์เมนูตามส่วนที่กำลังดูอยู่
- แอนิเมชัน Fade-in เมื่อเลื่อนมาถึงแต่ละส่วน (Intersection Observer)
- Video Modal ปิดได้ด้วยการคลิกพื้นหลังหรือกดปุ่ม `Esc`

## Tech Stack

| Area | Technology |
|------|-----------|
| โครงสร้าง | HTML5 |
| สไตล์ | [Tailwind CSS](https://tailwindcss.com/) (CDN) + Custom CSS |
| ไอคอน | [Font Awesome 6](https://fontawesome.com/) |
| ฟอนต์ | Google Fonts — Prompt, Inter |
| สคริปต์ | Vanilla JavaScript (ไม่ใช้ Framework / ไม่ต้อง Build) |
| โฮสต์ | [Render](https://render.com/) |

## Project Structure

```
ZenithWealth/
├── index.html        # หน้าเว็บหลัก (Single Page)
├── css/
│   └── style.css     # สี ธีม แอนิเมชัน และคอมโพเนนต์เสริม
├── js/
│   └── script.js     # Video Modal, เมนูมือถือ, Scroll effects
├── images/           # รูปภาพประกอบทั้งหมด
└── video/            # (ไม่ได้อยู่ใน Repo) ไฟล์วิดีโอ video1.mp4 สำหรับ Video Modal
```

## Getting Started

โปรเจกต์เป็น Static Site ไม่ต้องติดตั้ง dependency

```bash
# 1. โคลนโปรเจกต์
git clone https://github.com/kabJughead/ZenithWealth.git
cd ZenithWealth

# 2. เปิด index.html ในเบราว์เซอร์ได้เลย หรือรันเซิร์ฟเวอร์จำลอง
python3 -m http.server 8000
# แล้วเปิด http://localhost:8000
```

## Video Modal Setup

ส่วน "KASH" เรียกไฟล์ `video/video1.mp4` และตัดเล่นเฉพาะช่วงเวลาที่กำหนดใน `index.html`:

```html
<div onclick="openVideoModal('video/video1.mp4', 467, 1105)">
```

พารามิเตอร์คือ `(ที่อยู่ไฟล์, วินาทีเริ่มต้น, วินาทีสิ้นสุด)` หากต้องการให้ส่วนนี้ใช้งานได้ ให้วางไฟล์วิดีโอไว้ที่โฟลเดอร์ `video/` ตามชื่อข้างต้น

## Deployment (Render)

1. สร้าง **Static Site** ใหม่บน Render แล้วเชื่อมกับ Repository นี้
2. ตั้งค่า **Build Command**: เว้นว่างไว้
3. ตั้งค่า **Publish Directory**: `.`
4. กด Deploy — Render จะอัปเดตเว็บอัตโนมัติทุกครั้งที่ Push ขึ้น branch `main`

## Color Theme

| Name | Color |
|------|----|
| Primary | `#034ea2` |
| Zenith Orange | `#f6951f` |
| Wealth Blue | `#152a5c` |
| Accent | `#00a8ff` |
