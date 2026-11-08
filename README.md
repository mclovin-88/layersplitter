# Layer Splitter

**แยก layer จากไฟล์ Photoshop เป็น PNG ทีละไฟล์ ในเบราว์เซอร์ ฟรี ไม่ต้องมี Photoshop**

👉 **ใช้งานได้ที่ [mclovin-88.github.io/layersplitter](https://mclovin-88.github.io/layersplitter/)**

ลากไฟล์ `.psd` หรือ `.psb` มาวาง ติ๊กเลือก layer ที่ต้องการ แล้วกดปุ่มเดียว ได้ไฟล์ ZIP ที่มี PNG ของทุก layer เรียงชื่อไว้ให้พร้อมใช้ ไม่ต้องเปิด Photoshop และไม่ต้อง Export ทีละ layer

> 🔒 **ไฟล์ของคุณไม่ออกจากเครื่อง** ทุกอย่างประมวลผลในเบราว์เซอร์ ไม่มีการอัปโหลดไปที่ไหน

---

## ใช้งานใน 3 ขั้น

| ขั้น | ทำอะไร |
|---|---|
| **01 เลือกไฟล์** | ลากไฟล์ .psd / .psb มาวาง ไฟล์ใหญ่หลาย GB ก็เปิดได้ (อ่านเบื้องหลัง หน้าเว็บไม่ค้าง กดยกเลิกได้) |
| **02 เลือก Layer** | ติ๊ก layer ที่ต้องการ ดูผลใน Preview ได้ทันที กด **รวม** ข้างชื่อกรุ๊ปถ้าอยากได้ทั้งกรุ๊ปเป็นไฟล์เดียว |
| **03 ตั้งค่าแล้ว Export** | เลือกขนาดภาพและพื้นหลัง กด **Split Layers → ZIP** ได้ไฟล์ชื่อ `01_ชื่อlayer.png`, `02_…` เรียงจากบนลงล่าง |

## ทำอะไรได้บ้าง

- **ขนาดภาพ 2 แบบ:** *ตาม canvas* ทุกไฟล์ขนาดเท่ากัน วางซ้อนแล้วตรงตำแหน่ง หรือ *ตามต้นฉบับ* ตัดขอบใสออก และดึง Smart Object ที่ความละเอียดเต็ม
- **ภาพเหมือนใน Photoshop:**
  - Layer mask และ mask ของกรุ๊ป
  - Clipping mask
  - Blend mode ครบทุกแบบ รวม Lighter Color และ Dissolve
  - Adjustment layer 13 แบบ: Curves, Levels, Hue/Saturation, Black & White, Gradient Map ฯลฯ
- **Layer Style:** Drop Shadow, Inner Shadow, Stroke, Outer Glow, Color Overlay, Bevel & Emboss (เลือกเปิดหรือปิดได้)
- **รองรับ CMYK:** แปลงเป็น RGB ให้อัตโนมัติ
- **ไฟล์ใหญ่มาก:** ถ้าเกินที่เบราว์เซอร์รับได้ จะย่อให้อัตโนมัติพร้อมบอกขนาดที่ใช้ทำงาน
- **พื้นหลังโปร่งใส หรือเลือกสีพื้นหลังเองได้**
- **ดูตัวอย่างไฟล์ที่จะได้ก่อน Export** พร้อมขนาดและสัดส่วนของทุกไฟล์
- **แจ้งเตือนสีส้มทุกจุดที่แอปทำได้ไม่เหมือน Photoshop** จะได้รู้ก่อนว่าต้องเช็กตรงไหน

## ข้อจำกัด

| เรื่อง | รายละเอียด |
|---|---|
| ชนิดไฟล์ | รองรับเฉพาะ .psd และ .psb ยังไม่รองรับ .ai (ให้ Export จาก Illustrator เป็น PSD ก่อน) |
| ไฟล์ใหญ่มาก | เบราว์เซอร์ใช้หน่วยความจำได้ราว 4 GB และภาพกว้างได้ไม่เกิน 16384 px ไฟล์ที่เกินจะถูกย่อลง |
| สี | CMYK แปลงแบบประมาณ สีอาจต่างจาก Photoshop เล็กน้อย, CMYK 16-bit ยังเปิดไม่ได้, ไฟล์ 16/32-bit ส่งออกเป็น 8-bit |
| Layer Style ที่ยังไม่รองรับ | Inner Glow, Satin, Gradient/Pattern Overlay, Bevel แบบ Texture/Chisel |
| อื่นๆ | Vector mask, Smart Filter (ใช้ภาพที่ Photoshop บันทึกไว้แทน), Smart Object แบบ Linked หรือ vector ดึงความละเอียดเต็มไม่ได้ |
| เบราว์เซอร์ | แนะนำ Chrome หรือ Edge (Safari ใช้หน่วยความจำได้น้อยกว่า) |

💡 **เคล็ดลับ:** บันทึกไฟล์จาก Photoshop โดยเปิด *Maximize Compatibility* จะได้ภาพ Preview ตรงที่สุดและเปิดเร็วขึ้น

## เบื้องหลัง

เป็นไฟล์ HTML ไฟล์เดียว ไม่มีเซิร์ฟเวอร์ ไม่ต้องติดตั้ง

| ส่วน | ใช้ทำอะไร |
|---|---|
| [ag-psd](https://github.com/Agamnentzar/ag-psd) | อ่านโครงสร้างและพิกเซลของ PSD/PSB |
| Canvas | วาด mask, blend mode, Adjustment และ Layer Style ขึ้นมาใหม่ในเบราว์เซอร์ |
| Web Worker | อ่านและย่อไฟล์ใหญ่เบื้องหลัง หน้าเว็บจึงไม่ค้าง |
| [JSZip](https://stuk.github.io/jszip/) | รวม PNG เป็นไฟล์ ZIP |

## แผนต่อไป

- [ ] อ่านไฟล์ .ai ที่มี layer ติดมา
- [ ] แปลงสีด้วย color profile ให้ CMYK และ Adobe RGB ตรงขึ้น
- [ ] Inner Glow, Gradient Overlay และ Vector mask
- [ ] ส่งออกเป็น WebP/JPG และขนาด @2x

---

## English

**Split Photoshop layers into individual PNGs, right in your browser. Free, no Photoshop needed.**

👉 **[mclovin-88.github.io/layersplitter](https://mclovin-88.github.io/layersplitter/)**

Drop a `.psd` or `.psb`, tick the layers you want, and get a ZIP of numbered PNGs (`01_LayerName.png`, …). Your file never leaves your computer: everything runs locally in the browser.

**Highlights**
- Canvas-size or trimmed exports, with full-resolution Smart Objects
- Merge any group into a single PNG
- Faithful rendering:
  - Layer and group masks, clipping masks
  - All blend modes
  - 13 adjustment layer types
  - Layer Styles: Drop/Inner Shadow, Stroke, Outer Glow, Color Overlay, Bevel & Emboss
- CMYK files are converted to RGB
- Very large files are shrunk automatically to fit browser limits
- Files are read in a Web Worker so the page stays responsive, and every task can be cancelled
- Orange warnings point out anything that will not match Photoshop

**Limitations:**
- `.ai` files are not supported
- Very large files are worked on at reduced size (browser memory and canvas limits)
- Approximate CMYK colours, and no CMYK 16-bit
- Not yet rendered: Inner Glow, Satin, Gradient/Pattern Overlay and vector masks

Works best in Chrome or Edge.

Built with [ag-psd](https://github.com/Agamnentzar/ag-psd) and [JSZip](https://stuk.github.io/jszip/).
