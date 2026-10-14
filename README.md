# claude-skills

Skills ส่วนตัวสำหรับ Claude Code

| Skill | ใช้ทำอะไร | เรียกใช้ |
|---|---|---|
| [`handoff`](handoff/SKILL.md) | สรุปสถานะงานเป็น `HANDOFF.md` (ทำอะไรไปแล้ว เหลืออะไร ทำต่อยังไง) เพื่อไปทำต่อเครื่องอื่น | พิมพ์ `/handoff` หรือบอกว่า "สรุปงานทั้งหมด" |
| [`html`](html/SKILL.md) | แปลงไฟล์ `.md` (หรือสรุปในแชท) เป็นไฟล์ `.html` ไฟล์เดียว สวย อ่านง่าย มีสารบัญ ปุ่ม Copy โค้ด dark mode พิมพ์ได้ | พิมพ์ `/html` หรือ `/html HANDOFF.md` |

## ติดตั้งบนเครื่องใหม่

Claude Code อ่าน personal skills จาก `~/.claude/skills/<ชื่อ skill>/SKILL.md`

**macOS / Linux / Git Bash**
```bash
git clone https://github.com/<your-user>/claude-skills.git
mkdir -p ~/.claude/skills
cp -r claude-skills/handoff claude-skills/html ~/.claude/skills/
```

**Windows PowerShell**
```powershell
git clone https://github.com/<your-user>/claude-skills.git
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills" | Out-Null
Copy-Item -Recurse claude-skills\handoff, claude-skills\html "$env:USERPROFILE\.claude\skills\"
```

เปิด Claude Code ใหม่ แล้วพิมพ์ `/handoff` หรือ `/html`

ทิปใช้คู่กัน: `/handoff` แล้วตามด้วย `/html` → ได้ทั้ง `HANDOFF.md` และ `HANDOFF.html`

## โครงสร้าง
```
claude-skills/
├── README.md            ← ไฟล์นี้
├── handoff/
│   ├── SKILL.md         ← คำสั่งที่ Claude อ่าน (frontmatter name/description + ขั้นตอน)
│   └── template.md      ← โครงหัวข้อของ HANDOFF.md
└── html/
    ├── SKILL.md         ← วิธีแปลง Markdown → HTML + กฎ
    └── template.html    ← หน้าตา/CSS/สคริปต์ (สารบัญ, ปุ่ม Copy, dark mode, print)
```
