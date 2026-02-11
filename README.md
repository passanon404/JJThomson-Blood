เว็ปประชาสัมพันธ์ธนาคารเลือด<br>
นายกิตติศักดิ์ ภูมิยิ่ง รหัส 67021444 Front End<br>
นายจารุวัฒน์ ยะถา รหัส 67021488 Back End<br>
นายพรรษนนท์ สุยาละ รหัส 67021961 Front End<br>
นายระพีพงศ์ สุทา รหัส 67022131 Back End<br>
นายระพีพัชร จันต๊ะ รหัส 67022142 Fornt End<br>

## 🚀 วิธีรันโปรเจกต์ (Getting Started)

### 1. ติดตั้ง Dependencies

เปิด Terminal ใน VS Code แล้วรันคำสั่ง:

```bash
npm install

```

### 2. ตั้งค่า Environment Variables

เราต้องสร้างไฟล์ `.env` เพื่อเก็บความลับของโปรเจกต์

* **วิธีทำ:** ก๊อปปี้ไฟล์ `.env.example` แล้วเปลี่ยนชื่อเป็น `.env`
* **แก้ค่าข้างใน:**

```ini
# ตัวอย่างในไฟล์ .env
PORT=3000
SESSION_SECRET=ตั้งรหัสยาวๆมั่วๆตรงนี้เพื่อความปลอดภัย
# ถ้าจะใช้ MySQL ก็แก้ข้างล่างนี้ (ถ้าไม่ใช้ก็ปล่อยไว้)
DB_HOST=localhost
DB_USER=root
DB_PASS=password

```

### 3. เริ่มรัน Server!

```bash
npm run start

```

> ถ้ารันสำเร็จ จะขึ้นข้อความว่า Server running on `http://localhost:3000`

---

## 👤 บัญชีสำหรับทดสอบ (Test Accounts)

ใช้ล็อกอินเช็คระบบได้เลย รหัสผ่านทุกตัวคือ `123456`

| Role | Email | Password | Role ID | หมายเหตุ |
| --- | --- | --- | --- | --- |
| 👑 **Admin** | `admin@gmail.com`    | `123456` | `1` | สิทธิ์สูงสุด |
| 👤 **User**  | `kittisak@gmail.com` | `123456` | `2` | ผู้ใช้ทั่วไป |
| 👤 **User**  | `jaruwat@gmail.com`  | `123456` | `2` | ผู้ใช้ทั่วไป |

---

## 📡 API Endpoints (วิธีเทส)

ยิง Request ผ่าน **Postman** หรือ **Thunder Client** ใน VS Code ได้เลย

### 1. Login (เข้าสู่ระบบ)

* **URL:** `POST http://localhost:3000/api/login`
* **Body (JSON):**
```json
{
  "email": "admin@gmail.com",
  "password": "123456"
}

```


* **ผลลัพธ์:** จะได้ Cookie ชื่อ `connect.sid` กลับมา (HttpOnly)

### 2. Check Session (เช็คสถานะ)

* **URL:** `GET http://localhost:3000/api/health`
* **ผลลัพธ์:** ดูว่า Server ยังอยู่ดีไหม หรือ Session หมดอายุหรือยัง

### 3. Logout (ออกจากระบบ)

* **URL:** `POST http://localhost:3000/api/logout`

---

## 🛠️ สคริปต์ช่วยชีวิต (Helper Scripts)

ถ้า DB มีปัญหา หรืออยากรีเซ็ตข้อมูล รันคำสั่งพวกนี้ใน Terminal ได้เลย:

| คำสั่ง | รายละเอียด |
| --- | --- |
| `node server/scripts/inspect_users.js` | 👀 แอบดู User ทั้งหมดใน SQLite |
| `node server/scripts/inspect_mysql_users.js` | 👀 แอบดู User ทั้งหมดใน MySQL |
| `node server/scripts/set_admin_password.js` | 🔑 รีเซ็ตรหัส Admin กลับเป็น `123456` |
| `node server/scripts/migrate_passwords.js` | 🔐 แปลงรหัสธรรมดาให้เป็น Hash (Bcrypt) |

---

