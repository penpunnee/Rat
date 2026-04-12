# 🎰 Suda Lottery - Pro Analytics

แอปพลิเคชันจัดการและวิเคราะห์ข้อมูลหวยพร้อมระบบบิลอัตโนมัติ

## ✨ ฟีเจอร์หลัก

- **ออกบิล** - เพิ่มรายการเลขหวยกลุ่มละกรรม แบบบน/ล่าง/โต๊ด
- **สลับชุด** - สร้างการเรียงสับปะวนอัตโนมัติ
- **ตรวจรางวัล** - ตรวจสอบเลขที่ถูกรางวัลและคำนวณอัตโนมัติ
- **สรุปงวด** - แสดงยอดรวม ค่าคอม 27% กำไรสุทธิ
- **สรุปโพยเลข** - วิเคราะห์ยอดขายแยกตามประเภท (2 ตัว/3 ตัว)
- **ส่งออกบิล** - ดาวน์โหลดบิลเป็นรูป PNG
- **ค้นหาและแก้ไข** - ค้นหาบิล แก้ไข ลบข้อมูล
- **PWA Support** - ติดตั้งได้บนมือถือเหมือน Native App
- **Offline Support** - ใช้งานได้แม้ไม่มี Internet

## 🛠️ เทคโนโลยี

- HTML5 + JavaScript (Vanilla)
- Tailwind CSS + Font Awesome
- LocalStorage (เก็บข้อมูลในอุปกรณ์)
- html2canvas (ส่งออกบิลเป็นรูป)
- Service Worker (PWA + Offline)

## 📱 วิธีติดตั้งบนมือถือ

### iOS (iPhone)
1. เปิด Safari และไปที่ `https://[your-domain]`
2. แตะ **Share** → **Add to Home Screen**
3. ตั้งชื่อแล้ว **Add**
4. ได้แล้ว! แตะ icon บนหน้าแรก

### Android
1. เปิด Chrome และไปที่ `https://[your-domain]`
2. แตะ **⋮** (menu) → **Install app**
3. หรือ **Add to Home Screen**
4. ได้แล้ว! ใช้งาน full screen

## 💻 วิธีใช้

1. เปิดไฟล์ `index.html` ในเบราว์เซอร์
2. กรอกชื่อลูกค้า เลขหวย ประเภท และราคา
3. คลิก "เพิ่มรายการลงบิล"
4. บันทึกบิลเข้าหน้าสรุป
5. ตรวจรางวัลและดูการวิเคราะห์

## 📊 อัตราหวย

| ประเภท | อัตรา |
|--------|-------|
| บน (3 ตัว) | 500 บาท |
| บน (2 ตัว) | 60 บาท |
| ล่าง | 60 บาท |
| โต๊ด | 80 บาท |
| อั้น | 30 บาท |
| ชุด | 60 บาท |

## 💾 ข้อมูล

- ข้อมูลทั้งหมดเก็บในโครงสร้าง `suda_history` ของเบราว์เซอร์ (LocalStorage)
- ไม่ขึ้น Server - ข้อมูลจะเก็บได้ 50+ บิล
- สามารถ Export เป็น JSON (แนะนำ backup)

## 🔧 ไฟล์ที่สำคัญ

- `index.html` - หน้าหลักของแอป
- `manifest.json` - ตั้งค่า PWA
- `sw.js` - Service Worker (offline support)

## 📦 Deploy ไป Vercel

```bash
git clone <your-repo>
cd app-suda
# Upload ไป Vercel ผ่าน GitHub
```

## ⚡ Performance Tips

1. ลบข้อมูล 30+ บิลที่เก่า - ใช้ปุ่ม **Clear All Data**
2. Export ข้อมูลเพื่อ backup
3. ใช้ Chrome ที่ up-to-date สำหรับ PWA ที่ดีที่สุด

## 🐛 ปัญหาที่รู้จัก

- ถ้า LocalStorage เต็ม → แจ้ง "LocalStorage เต็ม" ให้ Clear Data
- html2canvas อาจ slow บน device เก่า
- iPhone อาจต้อง Settings > Safari > Block Pop-ups = OFF

---
**สร้างด้วย ❤️ สำหรับการจัดการหวยอย่างมืออาชีพ**

**ติดตั้ง PWA ได้ที่:** 📲 **Add to Home Screen**
