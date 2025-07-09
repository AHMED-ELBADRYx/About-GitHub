# 📜 الفهرس

1. [مقدمة](#مقدمة: Git و GitHub)
2. [مصطلحات مهمة](#مصطلحات-مهمة)
3. [إعدادات Git الأولية](#إعدادات-git-الأولية)
    - [عرض الإعدادات وتعديلها](#عرض-الإعدادات-وتعديلها)
    - [إعداد اسم المستخدم والبريد](#إعداد-اسم-المستخدم-والبريد)
    - [إعداد محرر النصوص الافتراضي](#إعداد-محرر-النصوص-الافتراضي)
    - [المفاتيح العامة والخاصة (SSH)](#المفاتيح-العامة-والخاصة-ssh)
4. [بدء مشروع جديد وربطه بـ GitHub](#بدء-مشروع-جديد-وربطه-ب-github)
    - [إنشاء مستودع جديد](#إنشاء-مستودع-جديد)
    - [تهيئة مجلد كمستودع Git](#تهيئة-مجلد-كمستودع-git)
    - [إضافة مستودع بعيد وربطه](#إضافة-مستودع-بعيد-وربطه)
    - [إرسال الملفات إلى المستودع البعيد](#إرسال-الملفات-إلى-المستودع-البعيد)
5. [التعامل مع الفروع (Branches)](#التعامل-مع-الفروع-branches)
    - [إنشاء الفروع وإدارتها](#إنشاء-الفروع-وإدارتها)
    - [دمج الفروع](#دمج-الفروع)
    - [إعادة تسمية الفروع](#إعادة-تسمية-الفروع)
6. [إدارة التغييرات (Staging / Commit / Reset)](#إدارة-التغييرات-staging--commit--reset)
    - [add / commit](#add--commit)
    - [إلغاء الملفات من staging](#إلغاء-الملفات-من-staging)
    - [أنواع reset](#أنواع-reset)
    - [git restore](#git-restore)
7. [التعامل مع Stash](#التعامل-مع-stash)
    - [حفظ التغييرات مؤقتًا](#حفظ-التغييرات-مؤقتًا)
    - [استرجاع التغييرات](#استرجاع-التغييرات)
    - [إدارة عناصر الـ Stash](#إدارة-عناصر-الـ-stash)
8. [تنظيف الملفات وإدارتها](#تنظيف-الملفات-وإدارتها)
    - [git clean](#git-clean)
    - [git checkout لإلغاء التغييرات](#git-checkout-لإلغاء-التغييرات)
    - [git rm](#git-rm)
9. [سجل المستودع (log / show / diff)](#سجل-المستودع-log--show--diff)
    - [git log](#git-log)
    - [git show](#git-show)
    - [git diff](#git-diff)
10. [الوسوم (Tags)](#الوسوم-tags)
    - [إنشاء الوسوم](#إنشاء-الوسوم)
    - [أنواع الوسوم](#أنواع-الوسوم)
    - [إدارة الوسوم](#إدارة-الوسوم)
11. [ملف .gitignore](#ملف-gitignore)
    - [إنشاء الملف وتحريره](#إنشاء-الملف-وتحريره)
    - [الأنماط والاستثناءات](#الأنماط-والاستثناءات)
12. [الاختصارات (Aliases)](#الاختصارات-aliases)
    - [إضافة اختصار](#إضافة-اختصار)
    - [عرض الاختصارات](#عرض-الاختصارات)
    - [حذف اختصار](#حذف-اختصار)
13. [حذف الملفات الكبيرة أو الحساسة من التاريخ](#حذف-الملفات-الكبيرة-أو-الحساسة-من-التاريخ)
    - [استخدام git rm --cached](#استخدام-git-rm--cached)
    - [تنظيف التاريخ باستخدام BFG](#تنظيف-التاريخ-باستخدام-bfg)
14. [ميزات متقدمة في Git](#ميزات-متقدمة-في-git)


---


# مقدمة: Git و GitHub

## المفاهيم الأساسية

### المستودع (Repository - Repo)
هو مساحة لتخزين الأكواد والمشاريع.  
قد يكون على جهازك (محلي Local) أو على الإنترنت (بعيد Remote مثل GitHub).

---

### الفرع (Branch)
فرع أو قسم من المستودع الرئيسي لتجربة تعديلات أو إصلاحات دون التأثير على النسخة الأساسية.

---

### المستودع المحلي (Local Repo)
هو نسخة المشروع الموجودة على جهازك الشخصي.

---

### المستودع البعيد (Remote Repo)
هو نسخة المشروع المخزنة على السيرفر (مثل GitHub).

---

### الالتزام (Commit)
نقطة تفتيش أو لقطة (Snapshot) تحفظ التعديلات في المستودع المحلي.

```sh
git commit -m "وصف التغييرات"
```


---

### الاستنساخ (Clone)
نسخ المشروع من مستودع محلي أو بعيد إلى جهازك.

```sh
git clone https://github.com/username/repo.git
```


---

### الدفع (Push)
إرسال التغييرات من جهازك إلى المستودع البعيد.

```sh
git push origin main
```


---

### السحب (Pull)
جلب التعديلات من المستودع البعيد إلى جهازك.

```sh
git pull origin main
```


---

### طلب السحب (Pull Request)
إعلام الفريق بالتغييرات التي أجريتها ليتم مراجعتها ودمجها في المشروع.

---

## خطوات تصدير مشروع إلى GitHub

### 1. إنشاء مستودع جديد من GitHub  
اختر اسمًا للمستودع، مثل: Codes، ثم انسخ رابط الـ .git.

---

### 2. إنشاء مجلد للعمل على جهازك:

```sh
mkdir My-GitHub
cd My-GitHub
```


---

### 3. استنساخ المستودع:

```sh
git clone https://github.com/username/Codes.git
cd Codes
```


---

### 4. إضافة ملفات المشروع إلى المجلد
يمكنك إضافة مجلدات مثل:

```sh
HTML/index.html
CSS/style.css
```


---

### 5. فحص حالة الملفات:

```sh
git status
```


---

### 6. تجهيز الملفات للنقل (Staging Area):

```sh
git add HTML/index.html CSS/style.css
```
# أو لإضافة جميع الملفات:
```sh
git add *
```


---

### 7. التراجع عن إضافة ملف بالخطأ:

```sh
git reset HEAD main.html
```


---

### 8. حفظ التغييرات محليًا (Commit):

```sh
git commit -m "إضافة ملفات HTML و CSS"
```


---

### 9. التأكد من الفرع الحالي:

```sh
git branch
```
# الناتج يكون مثل: main


---

### 10. التأكد من اسم المستودع البعيد:

```sh
git remote -v
```
# الناتج غالبًا: origin


---

### 11. رفع الملفات إلى GitHub:

```sh
git push origin main
```


---

### 12. ربط الفرع المحلي بالبعيد (أول مرة فقط):

```sh
git push -u origin main
```


---

### 13. في المشاريع التالية يمكنك الاكتفاء بـ:

```sh
git push
```


---

### 14. جلب الملفات الجديدة من GitHub (مثلاً إذا أنشأت README من الموقع):

```sh
git pull origin
```


هذا الأمر يقوم بـ:
- fetch: جلب الملفات.
- merge: دمجها بالمجلد المحلي.

---

# إعدادات Git

## الاستعلام عن إعدادات Git الحالية

```sh
git config --list
```
# أو
```sh
git config -l
```

---

## معرفة وظيفة أمر معين

```sh
git help config
```

---

## عرض البريد الإلكتروني المسجل عالميًا

```sh
git config --global user.email
```

---

## تعديل البريد الإلكتروني

```sh
git config --global user.email "email@gmail.com"
```

---

## تعديل اسم المستخدم

```sh
git config --global user.name "Your Name"
```

---

## مسح اسم المستخدم

```sh
git config --global user.name ""
```

---

## مسح أي عنصر (مثل الإيميل)

```sh
git config --global --unset user.email
```

---

## معرفة مصدر إعدادات Git

```sh
git config -l --show-origin
```

---

## عرض المحرر الافتراضي

```sh
git config --global core.editor
```

---

## تعيين محرر افتراضي (مثل VS Code)

```sh
git config --global core.editor "code --wait"
```

❗ `--wait` تعني أن Git ينتظر إغلاق المحرر قبل المتابعة.

---

## إزالة المحرر الافتراضي

```sh
git config --global --unset core.editor
```

---

## فتح إعدادات Git في المحرر

```sh
git config --global --edit
```

---

# مفاتيح SSH

## ما هو زوج المفاتيح؟

- **Public Key:** يُشارك مع الخدمات مثل GitHub للتحقق من هويتك.
- **Private Key:** سري، لفك تشفير الاتصالات.

---

## إنشاء مفتاح SSH جديد

```sh
ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
```

- يطلب منك تحديد مسار الحفظ وكلمة مرور اختيارية.

---

## عرض المفتاح العام لنسخه إلى GitHub

```sh
cat ~/.ssh/id_rsa.pub
```

- انسخه وضعه في إعدادات SSH Key على GitHub.

---

## اختبار الاتصال بـ GitHub عبر SSH

```sh
ssh -T git@github.com
```

---

# إعداد المستودع المحلي وربطه بالبعيد

## تهيئة مجلد Git جديد

```sh
git init
```

---

## التحقق من الفرع الحالي

```sh
git branch
```

- غالبًا يكون اسمه `master` أو `main`.

---

## إعادة تسمية الفرع من master إلى main

```sh
git branch -m master main
```

---

## جعل الفرع الافتراضي دائمًا باسم main

```sh
git config --global init.defaultBranch main
```

---

## إظهار المجلد المخفي .git في File Explorer

1. اذهب إلى View.
2. فعّل Show Hidden Items.

---

## ربط المستودع المحلي بمستودع GitHub عبر SSH

```sh
git remote add origin git@github.com:USERNAME/REPO.git
```

---

## التحقق من الربط

```sh
git remote -v
```

---

## تعديل رابط المستودع البعيد

```sh
git remote set-url origin git@github.com:USERNAME/REPO.git
```

---

## إزالة الربط تمامًا

```sh
git remote remove origin
```

---

## دفع الملفات وربط الفرع البعيد

```sh
git push -u origin main
```

- `-u` تربط الفرع المحلي بالبعيد لتسهيل push لاحقًا.

---

## معرفة الفروع المحلية المرتبطة بالسيرفر

```sh
git branch -vv
```

---

## تحديث التغييرات من السيرفر مع rebase

```sh
git pull origin main --rebase
```

- rebase: يضيف تغييراتك فوق تغييرات الفريق بشكل مرتب.

---

## فرض استبدال تغييرات السيرفر بتغييرات جهازك

```sh
git push -u origin main --force
```

---

# التعامل مع الفروع المحلية

## عرض جميع الفروع

```sh
git branch
```

---

## إنشاء فرع جديد اسمه br

```sh
git branch br
```

---

## الانتقال إلى فرع br

```sh
git checkout br
```

---

## إنشاء فرع جديد والانتقال إليه مباشرة

```sh
git checkout -b br
```

---

## إعادة تسمية الفرع الحالي

```sh
git branch -m new-name
```

---

## إعادة تسمية فرع آخر وأنت على فرع مختلف

```sh
git branch -m br new-name
```

---

## حذف فرع محلي (بعد الدمج أو بأمان)

```sh
git branch -d br
```

---

## حذف فرع محلي بالقوة (Force)

```sh
git branch -D br
```

---

## دمج فرع br في الفرع الرئيسي

1️⃣ انتقل إلى main:

```sh
git checkout main
```

2️⃣ نفذ الدمج:

```sh
git merge br
```

---

## حذف الفرع المدموج بعد الدمج

```sh
git branch -D br
```

---

## دفع فرع جديد إلى السيرفر

```sh
git push origin new-name
```

---

## حذف فرع من السيرفر

```sh
git push origin --delete old-name
```

---

## ربط الفرع الجديد بالسيرفر أول مرة

```sh
git push -u origin new-name
```

---

## دفع التغييرات لاحقًا بسهولة

```sh
git push
```

---

# الاختصارات (Aliases)

## إنشاء اختصار مثل pl لـ pull

```sh
git config --global alias.pl pull
```

---

## معرفة إلى ماذا يشير الاختصار

```sh
git config --global alias.pl
```

---

## حذف الاختصار

```sh
git config --global --unset alias.pl
```

---

## عرض كل الاختصارات

```sh
git config --get-regexp ^alias\.
```

---

## عرض جميع الإعدادات

```sh
git config --global --list
```

---

## فتح إعدادات Git في المحرر

```sh
git config --global --edit
```

---

## إنشاء اختصار لأمر مع مسافة

```sh
git config --global alias.cm "commit -m"
```

# منطقة التدريج (Staging Area)

## إضافة ملفات محددة إلى الـ Staging

```sh
git add HTML/index.html CSS/style.css
```

---

## إضافة كل الملفات

```sh
git add *
```

---

## إزالة ملف من الـ Staging (Unstage)

```sh
git reset HEAD myfile.html
```

---

## الطريقة الحديثة لإلغاء الـ Staging

```sh
git restore --staged myfile.html
```

---

## عرض حالة الملفات

```sh
git status
```

---

# Stash - إخفاء التعديلات مؤقتًا

## إخفاء الملفات المعدلة فقط

```sh
git stash
```

---

## إخفاء كل شيء معدّل + الملفات الجديدة (untracked)

```sh
git stash -u
```

---

## إخفاء كل شيء (بما فيها ignored)

```sh
git stash -a
```

---

## عرض قائمة الـ Stash

```sh
git stash list
```

---

## إضافة وصف أثناء التخزين

```sh
git stash save "وصف التغييرات"
```

---

## استعادة آخر Stash وإزالته من القائمة

```sh
git stash pop
```

---

## استعادة آخر Stash مع بقائه في القائمة

```sh
git stash apply
```

---

## استعادة Stash معين بالرقم

```sh
git stash pop stash@{2}
```

---

## حذف Stash معين

```sh
git stash drop stash@{1}
```

---

## حذف كل الـ Stash المخزنة

```sh
git stash clear
```

---

## إنشاء فرع جديد من Stash

```sh
git stash branch fork
```

---

## عرض التغييرات في Stash معين

```sh
git stash show stash@{1}
```

---

## عرض التغييرات بتفصيل

```sh
git stash show -p stash@{1}
```

---

# الفرق بين الملفات

✅ Untracked  
- ملفات جديدة لم تمر بـ git add أبداً.

✅ Tracked  
- ملفات يعرفها Git ولها حالتان:  
  - Staged: جاهزة للـ commit.  
  - Unstaged: تم تعديلها وتحتاج git add مجددًا.

---

# إزالة التعديلات

## إعادة الملفات المعدلة (unstaged) إلى آخر نسخة في HEAD

```sh
git checkout -- .
```

---

## حذف كل التغييرات (staged + unstaged)

```sh
git reset --hard
```

---

## إزالة التغييرات في ملف واحد معدّل

```sh
git checkout -- myfile.txt
```

---

## حذف الملفات الجديدة (untracked)

```sh
git clean -f
```

---

## عرض ما سيتم حذفه عند استخدام git clean

```sh
git clean -n
```

---

# ملف .gitignore

## إنشاء ملف .gitignore

```sh
touch .gitignore
```

---

## فتحه في VS Code

```sh
code .gitignore
```

---

## مثال: تجاهل كل ملفات .log

```
*.log
```

---

## استثناء ملف معين من التجاهل

```
!vip.log
```

---

## إضافة ملف متجاهَل بالقوة

```sh
git add -f text.txt
```

---

## قراءة قواعد التجاهل

```sh
git help ignore
```

# أنواع git reset

## الأنواع الثلاثة

✅ --soft  
- يحرك HEAD فقط.  
- التغييرات تبقى staged.

✅ --mixed  
- يحرك HEAD.  
- يلغي الـ staging.  
- التغييرات تبقى في working directory.  
- هو الوضع الافتراضي.

✅ --hard  
- يحرك HEAD.  
- يلغي staging.  
- يحذف التغييرات من working directory.

---

## أمثلة عملية

### إلغاء آخر commit وترك التغييرات staged

```sh
git reset --soft HEAD~1
```

---

### إلغاء آخر commit وجعل التغييرات un-staged

```sh
git reset --mixed HEAD~1
```

أو

```sh
git reset HEAD~1
```

---

### إلغاء آخر commit وحذف كل التغييرات

```sh
git reset --hard HEAD~1
```

---

# إزالة ملف من الـ Staging فقط

```sh
git reset HEAD myfile
```

أو بالطريقة الحديثة:

```sh
git restore --staged myfile
```

---

# إزالة ملف من التتبع (جعله untracked)

```sh
git rm --cached myfile
```

---

✅ بعد commit يصبح الملف:

- Tracked ✅
- Clean ✅

---

# عرض سجل المستودع

## عرض كل الـ commits

```sh
git log
```

- للخروج من عرض log في cmder اضغط:  
  **Q**

---

## عرض سجل ملف معين

```sh
git log -- myfile
```

---

## عرض التغييرات بتفصيل

```sh
git show --stat <hash>
```

---

## عرض الفروقات بين نسختين من ملف

```sh
git diff abc123:main.txt def456:main.txt
```

---

## استرجاع نسخة ملف من commit قديم

```sh
git checkout abc123 -- myfile
```

---

# حذف ملف من المستودع (بنسخته الأخيرة فقط)

✅ لتجعل الملف غير موجود في HEAD (آخر نسخة)، لكنه يبقى في التاريخ:

```sh
git rm --cached myfile.txt
git commit -m "Remove myfile.txt from repo"
git push
```

- النتيجة:
  - الملف يحذف من النسخة الحالية على GitHub.
  - يبقى موجودًا في التاريخ (الكوميتات القديمة).

---

# الحذف الكامل من كل التاريخ باستخدام BFG

✅ أداة BFG Repo-Cleaner

---

## ما الفرق؟

✅ git rm --cached  
- يحذف من HEAD فقط.  
- التاريخ القديم يحتفظ بالملف.

✅ BFG  
- يحذف الملف من كل الكوميتات في كل الفروع.  
- مثالي لحذف كلمات مرور أو أسرار أو ملفات ضخمة دفعت بالخطأ.

---

# الخطوات الكاملة لاستخدام BFG

✅ ① تجهيز نسخة mirror من الريبو

```sh
git clone --mirror <رابط-الريبو>
```

مثال:

```sh
git clone --mirror https://github.com/USERNAME/REPO.git
```

---

✅ ② تشغيل BFG

- انتقل إلى مكان ملف jar الخاص بـ BFG.
- الصيغة:

```sh
java -jar <مسار-bfg.jar> --delete-files <اسم-الملف> <مسار-النسخة>
```

مثال عملي:

```sh
java -jar C:\Users\hp\Downloads\bfg-1.15.0.jar --delete-files index.html D:\Git-Init\Git-Init.git
```

---

✅ ③ تنظيف الـ refs والأجسام القديمة

```sh
cd D:\Git-Init\Git-Init.git
git reflog expire --expire=now --all
git gc --prune=now --aggressive
```

---

✅ ④ دفع التغييرات بالقوة إلى GitHub

```sh
git push --force
```

---

✅ روابط التحميل

- BFG:
  - [https://rtyley.github.io/bfg-repo-cleaner/](https://rtyley.github.io/bfg-repo-cleaner/)

- Java:
  - [https://www.oracle.com/java/technologies/downloads/](https://www.oracle.com/java/technologies/downloads/)

---

# أوامر مساعدة إضافية

## معرفة محرر Git الحالي

```sh
git config --global core.editor
```

---

## تغيير المحرر الافتراضي إلى VS Code

```sh
git config --global core.editor "code --wait"
```

---

## إلغاء تعيين المحرر

```sh
git config --global --unset core.editor
```

---

## فتح إعدادات Git في محرر

```sh
git config --global --edit
```

# Taging (الوسوم والإصدارات)

## إنشاء وسم (Tag) بسيط

```sh
git tag v1.0
```

---

## إنشاء وسم Annotated رسمي

```sh
git tag -a v2.0 -m "Second version"
```

---

## عرض كل الوسوم

```sh
git tag
```

---

## رفع وسم معين إلى السيرفر

```sh
git push origin v1.0
```

---

## رفع كل الوسوم دفعة واحدة

```sh
git push origin --tags
```

---

## حذف وسم محلي

```sh
git tag -d tag_name
```

---

## حذف وسم من السيرفر

```sh
git push --delete origin tag_name
```

---

## إنشاء وسم على commit محدد

```sh
git tag v1.2.3 <commit-hash>
```

---

## البحث عن وسوم بإصدار معين

```sh
git tag -l "v1.*"
```

---

✅ ❗ ملاحظة:  
- الوسوم لا تُغيّر محتوى المشروع.  
- لو تم تعديل محتوى الفرع الذي عليه الوسم، سيتأثر الوسم إذا لم يتم تثبيته على commit محدد.

---

# Aliases (الاختصارات في Git)

## إنشاء اختصار مثل pl = pull

```sh
git config --global alias.pl pull
```

---

## التحقق من الاختصار

```sh
git config --global alias.pl
```

---

## حذف اختصار

```sh
git config --global --unset alias.pl
```

---

## عرض كل الاختصارات

```sh
git config --get-regexp ^alias\.
```

---

# إعدادات Git

## عرض جميع الإعدادات

```sh
git config --list
```

أو

```sh
git config -l
```

---

## عرض مصدر كل إعداد (ملف الإعداد)

```sh
git config -l --show-origin
```

---

## تعديل الإيميل

```sh
git config --global user.email "email@example.com"
```

---

## عرض الإيميل المسجل

```sh
git config --global user.email
```

---

## حذف الإيميل

```sh
git config --global --unset user.email
```

---

## حذف الاسم

```sh
git config --global user.name ""
```

---

# ميزات متقدمة في Git

## التحقق من إعدادات المفتاح الخاص SSH

### إنشاء زوج مفاتيح SSH

```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

---

### عرض المفتاح العام (لنسخه في GitHub)

```sh
cat ~/.ssh/id_rsa.pub
```

---

### اختبار الاتصال بـ GitHub عبر SSH

```sh
ssh -T git@github.com
```

---

## تغيير اسم الفرع الافتراضي في المستقبل إلى main

```sh
git config --global init.defaultBranch main
```

---

## تغيير اسم فرع محلي

```sh
git branch -m old-name new-name
```

---

## حذف فرع محلي بالقوة

```sh
git branch -D branch-name
```

---

## دمج فرع في الرئيسي

```sh
git checkout main
git merge feature-branch
```

---

## حذف اسم remote مرتبط

```sh
git remote remove origin
```

---

## إعادة تعيين عنوان URL الخاص بـ remote

```sh
git remote set-url origin git@github.com:USERNAME/REPO.git
```

---

## إنشاء remote جديد باسم origin

```sh
git remote add origin git@github.com:USERNAME/REPO.git
```

---

## عرض الفروع المرتبطة بـ Remote

```sh
git branch -vv
```

---

## دمج تغييرات السيرفر في تغييراتك

```sh
git pull origin main --rebase
```

---

## تجاهل تغييرات السيرفر بالقوة ورفع تعديلك

```sh
git push -u origin main --force
```

