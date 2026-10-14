# claude-skills

Skills ส่วนตัวสำหรับ Claude Code

| Skill | ใช้ทำอะไร | เรียกใช้ |
|---|---|---|
| [`handoff`](handoff/SKILL.md) | สรุปสถานะงานเป็น `HANDOFF.md` (ทำอะไรไปแล้ว เหลืออะไร ทำต่อยังไง) เพื่อไปทำต่อเครื่องอื่น | พิมพ์ `/handoff` หรือบอกว่า "สรุปงานทั้งหมด" |

## ติดตั้งบนเครื่องใหม่

Claude Code อ่าน personal skills จาก `~/.claude/skills/<ชื่อ skill>/SKILL.md`

**macOS / Linux / Git Bash**
```bash
git clone https://github.com/<your-user>/claude-skills.git
mkdir -p ~/.claude/skills
cp -r claude-skills/handoff ~/.claude/skills/
```

**Windows PowerShell**
```powershell
git clone https://github.com/<your-user>/claude-skills.git
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills" | Out-Null
Copy-Item -Recurse claude-skills\handoff "$env:USERPROFILE\.claude\skills\"
```

เปิด Claude Code ใหม่ แล้วพิมพ์ `/handoff`

## โครงสร้าง
```
claude-skills/
├── README.md            ← ไฟล์นี้
└── handoff/
    ├── SKILL.md         ← คำสั่งที่ Claude อ่าน (frontmatter name/description + ขั้นตอน)
    └── template.md      ← โครงหัวข้อของ HANDOFF.md
```
