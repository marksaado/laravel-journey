# مرجع أوامر Git

> يحدّثه المعلم كلما تعلّمنا أمراً جديداً. آخر تحديث: 2026-11-09

## الإعداد (مرة واحدة على الجهاز)
| الأمر | ماذا يفعل |
|---|---|
| `git config --global user.name "Mark Saado"` | يحدد الاسم الذي يُسجَّل على كل commit |
| `git config --global user.email "you@example.com"` | يحدد الإيميل (نفس إيميل GitHub) |
| `git config --global init.defaultBranch main` | يجعل اسم الفرع الرئيسي `main` في كل repo جديد |
| `git config --global --list` | يعرض كل الإعدادات الحالية |

## بداية مشروع
| الأمر | ماذا يفعل |
|---|---|
| `git init` | يجعل المجلد الحالي repo (ينشئ `.git/` المخفي) |

## العمل اليومي
| الأمر | ماذا يفعل |
|---|---|
| `git status` | يعرض حالة الملفات: جديدة (Untracked)، معدّلة (modified)، جاهزة للحفظ (staged) |
| `git diff` | يعرض التغييرات التي لم تُضف بعد (`-` قديم، `+` جديد، الخروج بـ `q`) |
| `git diff ملف` | التغييرات في ملف واحد فقط |
| `git add ملف` | يضع ملفاً في الـ staging area |
| `git add .` | يضع كل التغييرات في المجلد الحالي في الـ staging area |
| `git commit -m "رسالة"` | يحفظ لقطة لكل ما في الـ staging area |
| `git log --oneline` | يعرض الـ commits، كل واحد في سطر (الأحدث في الأعلى) |

## GitHub
| الأمر | ماذا يفعل |
|---|---|
| `git remote add origin URL` | يربط الـ repo المحلي بمستودع على GitHub باسم `origin` |
| `git remote -v` | يعرض الـ remotes المربوطة |
| `git push -u origin main` | أول رفع: يرفع `main` ويحفظ الربط |
| `git push` | كل رفع بعد الأول |
| `git push --set-upstream origin main` | الصيغة الطويلة لـ `git push -u origin main` (يقترحها Git في رسالة الخطأ) |

**خطأ شائع:** `fatal: The current branch main has no upstream branch` ← نسيت `-u origin main` في أول push لمستودع جديد.

## الدورة اليومية
```bash
git status                 # ماذا تغيّر؟
git diff                   # ما التغييرات بالضبط؟
git add ملف                # جهّز ما تريد حفظه
git commit -m "Add ..."    # احفظ لقطة
git push                   # ارفع إلى GitHub
```

## رسائل الـ commit
- تبدأ بفعل إنجليزي بحرف كبير: `Add`، `Fix`، `Update`، `Remove`.
- محددة: `Add contact form to about page` لا `update`.
- ملفات التقدم: `Update progress: <الدرس>`.
