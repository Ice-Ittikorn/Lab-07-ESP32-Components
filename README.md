1. เมื่อใดควรสร้าง component ใหม่ แทนที่จะเขียนโค้ดใน main application?
   - เมื่อโค้ดเริ่มเยอะ ดูแลยาก หรือมีส่วนที่ใช้งานซ้ำได้ เช่น driver, library, ฟังก์ชันเฉพาะ ควรแยกเป็น component เพื่อให้จัดการง่ายและ reuse ได้ในโปรเจกต์อื่น
2. ความแตกต่างระหว่าง REQUIRES และ PRIV_REQUIRES ส่งผลต่อการ compile อย่างไร?
   - REQUIRES คือ dependency แบบ public ให้ component อื่นเห็นได้ด้วย
   - PRIV_REQUIRES คือ dependency แบบ private ใช้แค่ภายใน component นั้น
   - ต่างกันที่ scope ของ include path และลำดับการ build
3. การเลือกใช้ local component vs managed component ขึ้นอยู่กับปัจจัยใดบ้าง?
   - Local component ใช้เมื่อโค้ดนั้นใช้เฉพาะในโปรเจกต์เดียว แก้ไขบ่อย ยังไม่ต้องแชร์ให้คนอื่น ใช้งานง่าย ไม่ต้องจัดการเวอร์ชัน
   - Managed component ใช้เมื่อโค้ดต้องแชร์ให้หลายโปรเจกต์หรือหลายทีม ใช้ซ้ำได้ ต้องการควบคุมเวอร์ชันและอัปเดตอัตโนมัติผ่าน component manager
4. ในทีมงานขนาดใหญ่ จะจัดการ component dependencies อย่างไรให้มีประสิทธิภาพ?
  - กำหนดขอบเขตแต่ละ component ให้ชัด
  - ใช้ REQUIRES / PRIV_REQUIRES ให้ถูก
  - หลีกเลี่ยงการพึ่งพาวนกัน
  - ใช้ version control กับ component ที่แชร์
  - ทำเอกสารและทดสอบอัตโนมัติไว้ทุกตัว
5. การทดสอบ component ที่มีการพึ่งพา hardware ทำได้อย่างไร?
  - ทำ mock หรือจำลอง hardwareแยก logic ออกจาก hardware layerใช้บอร์ดจริงเฉพาะตอน integration testบางกรณีใช้ hardware-in-loop หรือ test rig เพื่อทดสอบอัตโนมัติ

