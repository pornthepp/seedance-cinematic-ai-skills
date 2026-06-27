# Ref Over Text Rule

## หลักการ

Reference image เป็นตัวควบคุม physical details ทั้งหมด — prompt เขียนแค่สิ่งที่ ref ทำไม่ได้

## Ref ควบคุม (ห้าม prompt บรรยายซ้ำ)

- โครงสร้าง รูปทรง วัสดุ (หิน ไม้ ไม้ไผ่ หลังคา ผนัง)
- สภาพแวดล้อม (ป่า แม่น้ำ ภูเขา ท่าเรือ ต้นไม้)
- สี palette โทนรวม
- หน้า ผม ผิว สัดส่วนร่าง ชุด ของตัวละคร
- พื้นผิว texture (เกล็ด หนัง ผ้า เกราะ)

## Prompt ควบคุม (สิ่งที่ ref ทำไม่ได้)

- ท่าทาง pose / action / blocking
- มุมกล้อง shot size / height / angle
- ทิศทางแสง ทิศเงา
- ความคมของเงา (hard/soft shadow edge)
- สภาพอากาศ (ฝน หมอก ลม) ที่ไม่มีใน ref
- อารมณ์ expression / performance
- มือ — ตำแหน่ง จำนวนนิ้ว ท่า (กัน extra fingers)

## วิธีเขียน REFERENCE INPUTS

```
REFERENCE INPUTS:
filename.jpg = {placeholder}
References define all physical details. The prompt controls only pose, action, camera, lighting direction, and shadow.
```

- บรรทัดแรก: map ชื่อไฟล์กับ placeholder
- บรรทัดสอง: ประกาศขอบเขต — ref ควบคุมอะไร, prompt ควบคุมอะไร
- ถ้า ref หลายตัวทำหน้าที่ต่างกัน ระบุสั้นๆ เช่น `{ธีร์นักรบ} defines the battle robe being removed.`

## ห้าม

- ห้ามบรรยายวัสดุที่ ref แสดงอยู่แล้ว (เช่น เขียน "bamboo walls" ทั้งที่ ref เป็นกระท่อมหิน)
- ห้ามบรรยายสภาพแวดล้อมที่ ref แสดงอยู่แล้ว (เช่น เขียน "dark jungle" ทั้งที่ ref เป็นริมแม่น้ำ)
- ห้ามบรรยายหน้า/ผม/ชุด ซ้ำกับ ref — ยกเว้นสถานะที่เปลี่ยนจาก ref (เช่น "battle robe removed" ถ้า ref ยังใส่อยู่)

## ถ้าจำเป็นต้องพูดถึงสิ่งที่มีใน ref

ใช้คำสั้นแล้วอ้าง ref:
- "the hut as shown in {กระท่อม}" ไม่ใช่ "a small hut built into a massive tree covered in flowering vines with a stone arched doorway..."
- "Inside {กระท่อม}" ไม่ใช่ "Inside a dark bamboo hut with rough wooden walls and a dirt floor..."

## เหตุผล

GPT Image 2 เป็น autoregressive model — ถ้าข้อความขัดกับ ref จะเชื่อข้อความมากกว่า ทำให้ภาพไม่ตรง ref ทั้งที่ user แนบ ref ถูกแล้ว ยิ่งบรรยาย physical details มาก ยิ่งมีโอกาส override ref
