# Suda Lottery 🎯

แอปจัดการลอตเตอรี่ — ออกบิล / สรุปงวด / สรุปโพย / รายบุคคล / เทียบงวด

## โครงสร้างโปรเจกต์

```
suda-lottery/
├── index.html          ← หน้าเว็บหลัก (ทั้งแอปอยู่ในไฟล์เดียว)
├── output.css          ← Tailwind CSS ที่ build แล้ว (generate อัตโนมัติ, ไม่ต้องแก้มือ)
├── src/input.css       ← ต้นทาง Tailwind (แก้ตรงนี้ถ้าจะปรับ base style)
├── tailwind.config.js  ← ตั้งค่า Tailwind ให้ scan index.html หา class
├── package.json        ← คำสั่ง build
└── vercel.json         ← ตั้งค่าให้ Vercel build อัตโนมัติตอน deploy
```

## รันทดสอบในเครื่อง (ก่อน deploy)

```bash
npm install
npm run build:css     # build Tailwind CSS เป็น output.css
```

จากนั้นเปิด `index.html` ด้วย Live Server (VS Code extension) หรือ:

```bash
python3 -m http.server 8000
# เปิด http://localhost:8000
```

## ขั้นตอน Deploy ขึ้น GitHub

```bash
git init
git add .
git commit -m "Initial commit - Suda Lottery"
git branch -M main
git remote add origin https://github.com/<username>/suda-lottery.git
git push -u origin main
```

> **หมายเหตุ:** `node_modules/` และ `output.css` ที่ build แล้วจะไม่ถูก push ขึ้น GitHub (อยู่ใน `.gitignore`) — Vercel จะ build ให้เองตอน deploy

## ขั้นตอน Deploy ขึ้น Vercel

1. เข้า [vercel.com](https://vercel.com) → Sign in ด้วย GitHub
2. กด **Add New → Project**
3. เลือก repo `suda-lottery` ที่เพิ่ง push ขึ้นไป
4. **Framework Preset:** เลือก **Other** (เพราะไม่ใช่ React/Next.js)
5. ปล่อยค่า Build Command / Output Directory ตามที่ตั้งไว้ใน `vercel.json` (ไม่ต้องแก้)
6. กด **Deploy**

รอ 30 วินาที — ได้ลิงก์ `https://suda-lottery-xxxx.vercel.app` ใช้งานได้ทันที

## ถ้าแก้ index.html แล้วอยากเพิ่ม Tailwind class ใหม่

แค่แก้ `index.html` ตามปกติ (เพิ่ม class ใน `class="..."` หรือใน JS string) แล้ว push ขึ้น GitHub — Vercel จะรัน `npm run build:css` ใหม่ให้อัตโนมัติทุกครั้งที่ deploy ไม่ต้อง build เองในเครื่อง

ถ้าอยากดูผลลัพธ์ในเครื่องก่อน push:
```bash
npm run build:css
```

## ข้อมูลเก็บที่ไหน

ข้อมูลบิล/ลูกค้า/งวด/เลขรางวัล เก็บใน **localStorage ของเบราว์เซอร์** (ไม่มี backend/database) — ข้อมูลจะอยู่เฉพาะเบราว์เซอร์/อุปกรณ์ที่ใช้งาน ถ้าเปลี่ยนเครื่องหรือล้าง cache ข้อมูลจะหาย แนะนำให้ export Excel เก็บสำรองเป็นระยะ
