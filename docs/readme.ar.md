# Skill Router

Skill Router هي meta-skill صغيرة تختار أفضل skill أو قاعدة أو سير عمل مثبت قبل بدء العمل.

هدفها تقليل استهلاك السياق: تختار skill أساسية واحدة، وتضيف مهارات مساعدة فقط عندما تكون مفيدة فعلا.

## التثبيت في Codex

```powershell
Copy-Item -Recurse .\codex\skill-router $env:USERPROFILE\.codex\skills\skill-router
```

أعد تشغيل Codex ثم استخدم:

```text
$skill-router ساعدني في تنفيذ هذه الميزة...
```

## التثبيت في Claude

```powershell
Copy-Item -Recurse .\claude\.claude\skills\skill-router .\.claude\skills\skill-router
```

## التثبيت في Cursor

```powershell
New-Item -ItemType Directory -Force .\.cursor\rules
Copy-Item .\cursor\skill-router.mdc .\.cursor\rules\skill-router.mdc
```

## التوجيه الافتراضي

- البرمجة وإعادة الهيكلة: `using-superpowers`
- التطوير بالاختبارات أولا: `test-driven-development`
- الأخطاء والسلوك المعطل: `systematic-debugging`
- UI/UX والتحسين البصري: `ui-ux-pro-max`
- نماذج HTML عالية الدقة: `huashu-design`
- الحكم الهندسي: `karpathy-guidelines`
- التحقق النهائي: `verification-before-completion`

