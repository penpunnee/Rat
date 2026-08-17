# CLAUDE.md — `app suda/` Lottery Analytics PWA (Vanilla JS)

## 🗺️ ทางเข้า / จดที่ไหน (มาตรฐานเดียวกันทุกโปรเจกต์ · ตั้ง 2026-08-17)

- **เปิดงานด้วย `cc suda`** — ต้องเปิด `claude` จาก**ในโฟลเดอร์นี้** ไฟล์นี้กับถังความจำของ
  โปรเจกต์ถึงจะโหลด · เปิดจาก `~` แล้วมาทำงานที่นี่ = **ไม่ได้ทั้งสองอย่าง**
- **ถังความจำ:** `~/.claude/projects/-Users-pawin-app-suda/memory/`
  · `MEMORY.md` ในถัง = หน้าแรกของโปรเจกต์นี้ (ตัวชี้ + ข้อห้าม + งานค้าง)
  · โน้ตข้างเคียงเป็น **symlink ไปถังกลาง** = ไฟล์เดียวกัน **ห้ามแทนที่ด้วยสำเนา**
- **จบเซสชัน → จดที่ commit message + `README.md`**
  **ห้ามจดเนื้อหาลง memory** (memory ไม่มี diff ตรวจย้อนไม่ได้ · git ตรวจได้ · remote `penpunnee/Rat`)
- กฎข้ามโปรเจกต์ (Iron Laws · "เครื่องมือวัดโกหก" · ทางเข้า NAS/Pi · วิธีทำงานกับ user)
  อยู่ `~/.claude/CLAUDE.md` ซึ่งโหลดทุกที่อยู่แล้ว — **ห้ามก๊อปมาซ้ำที่นี่**


(ย้ายมาจาก `~/CLAUDE.md` หัวข้อ "3. app suda/" ตอนแยกโปรเจกต์ 2026-08-18)

A PWA for lottery bill management: create bills, check results, export PNG, offline support.

**Stack:** Vanilla HTML5 + JavaScript, Tailwind CSS, `html2canvas`, Service Worker
**Storage:** LocalStorage only (no backend)
**Deploy:** Vercel (`vercel.json`)

No build step — edit `index.html` directly and deploy.

## การรัน

```bash
cd ~/"app suda"
open index.html          # ไม่มี build step — แก้ index.html ตรงๆ แล้วเปิดดูได้เลย
vercel --prod            # deploy (ตั้งค่าใน vercel.json)
```
