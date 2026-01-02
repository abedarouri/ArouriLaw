[arouri_law_website (1).py](https://github.com/user-attachments/files/24410814/arouri_law_website.1.py)
# سنقوم بإنشاء نسخة مضغوطة جاهزة للموقع
# سيتم حفظ الملفات ضمن مجلد 'ArouriLaw'

import os
import zipfile

# إنشاء المجلد الرئيسي
os.makedirs('/mnt/data/ArouriLaw/assets/css', exist_ok=True)
os.makedirs('/mnt/data/ArouriLaw/assets/js', exist_ok=True)

# إنشاء ملف CNAME
with open('/mnt/data/ArouriLaw/CNAME', 'w') as f:
    f.write('ArouriLaw.ps')

# إنشاء ملفات CSS وJS الأساسية
with open('/mnt/data/ArouriLaw/assets/css/style.css', 'w') as f:
    f.write('/* CSS الأساسي للموقع */\nbody { font-family: Arial, sans-serif; margin:0; padding:0; background:#f5f5f5; color:#0b1c2d; }\n.container { width:90%; max-width:1200px; margin:auto; }\n.header, .footer { background:#0b1c2d; color:#fff; padding:15px 0; text-align:center; }\n.btn { display:inline-block; padding:10px 20px; background:#0b1c2d; color:#fff; text-decoration:none; border-radius:4px; margin:5px 0; }\n.services-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(280px,1fr)); gap:20px; padding:40px 0; }\n.service-card { background:#fff; padding:20px; border-radius:6px; box-shadow:0 2px 6px rgba(0,0,0,0.08); }\n.contact { background:#fff; padding:40px 0; }\n.contact a { color:#0b1c2d; text-decoration:none; font-weight:bold; }')

with open('/mnt/data/ArouriLaw/assets/js/lang.js', 'w') as f:
    f.write('// JS لتبديل اللغة عربي/إنجليزي\nvar currentLang = "ar";\nfunction setLang(lang){ currentLang=lang; alert("تم تغيير اللغة"); }')

# إنشاء صفحات HTML أساسية (index.html كمثال)
with open('/mnt/data/ArouriLaw/index.html', 'w') as f:
    f.write('<!DOCTYPE html><html lang="ar" dir="rtl"><head><meta charset="UTF-8"><title>مكتب العاروري للمحاماة | محامي في رام الله</title></head><body><h1>مكتب العاروري للمحاماة</h1></body></html>')

# إنشاء ملف ZIP
zipf = zipfile.ZipFile('/mnt/data/ArouriLaw.zip', 'w', zipfile.ZIP_DEFLATED)
for root, dirs, files in os.walk('/mnt/data/ArouriLaw'):
    for file in files:
        zipf.write(os.path.join(root, file), os.path.relpath(os.path.join(root, file), '/mnt/data/ArouriLaw'))
zipf.close()

'/mnt/data/ArouriLaw.zip'
