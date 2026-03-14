# 🎓 Bac DZ AI

منصة تعليمية متكاملة لتلاميذ البكالوريا الجزائرية مدعومة بالذكاء الاصطناعي

## 🚀 النشر على Vercel

### الطريقة الأولى — Vercel CLI

```bash
# تثبيت Vercel CLI
npm i -g vercel

# تسجيل الدخول
vercel login

# النشر
vercel --prod
```

### الطريقة الثانية — GitHub + Vercel Dashboard

1. ارفع المشروع على GitHub
2. اذهب إلى [vercel.com](https://vercel.com)
3. اضغط **"New Project"**
4. اختر الـ repository
5. الإعدادات تلقائية (Vite يُكتشف تلقائياً)
6. اضغط **"Deploy"** ✅

### إعدادات Vercel (تلقائية من vercel.json)

| الإعداد | القيمة |
|---------|--------|
| Build Command | `npm run build` |
| Output Directory | `dist` |
| Framework | `Vite` |
| Node.js Version | `18.x` |

## ⚙️ متغيرات البيئة في Vercel

في لوحة تحكم Vercel → Settings → Environment Variables أضف:

```
VITE_GEMINI_API_KEY=AIzaSyBey6R_bFCswa5C7NiuZgmSQVtVM8AyS5E
VITE_YOUTUBE_API_KEY=your_key_here
VITE_OPENROUTER_API_KEY=sk-or-v1-...
```

## 🔥 Firebase Setup

1. اذهب إلى [Firebase Console](https://console.firebase.google.com)
2. مشروع: `not-b25f1`
3. فعّل: Authentication + Firestore + Realtime Database

### Realtime Database Rules

```json
{
  "rules": {
    ".read": "auth != null",
    ".write": "auth != null"
  }
}
```

### Firestore Rules

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```

## 🛠️ تشغيل محلي

```bash
# تثبيت الحزم
npm install

# تشغيل dev server
npm run dev

# بناء للإنتاج
npm run build

# معاينة البناء
npm run preview
```

## 📚 الصفحات

| الصفحة | الوصف |
|--------|-------|
| 🏠 Home | الصفحة الرئيسية |
| 🔐 Auth | تسجيل الدخول والتسجيل |
| 💬 Chat | الدردشة العامة |
| 📚 Posts | المنشورات والدروس |
| 🧠 AI Teacher | الأستاذ الافتراضي |
| 📝 Analyzer | تحليل الدروس |
| 🎬 YouTube | تحليل فيديوهات يوتيوب |
| 🔍 Search | البحث |
| 🖥️ Zoom | غرف الدراسة المباشرة |
| 👑 Admin | لوحة التحكم |

## 🔐 حساب Admin

```
Email: nacero123@gmail.com
Password: adminadmin
```

## 🤖 تقنيات مستخدمة

- **React 19** + TypeScript
- **Vite** + Tailwind CSS
- **Firebase** (Auth + Firestore + RTDB)
- **Gemini 3 Flash** (Google AI)
- **WebRTC** (Zoom Live)
- **Web Speech API** (صوت)
