# Hopper 2034 🇸🇦

تطبيق مساعد للزوار في كأس العالم ٢٠٣٤ في السعودية. مبني بـ **React Native + Expo**، ويشتغل على الجوال (Android و iOS) وعلى **الويب** كموقع.

## الشاشات

| الرابط | الملف | وش فيها |
|---|---|---|
| `/` | `app/index.tsx` | شاشة الترحيب: زر تسجيل دخول وزر حساب جديد |
| `/login` | `app/login.tsx` | تسجيل الدخول، يوديك لصفحة الترجمة |
| `/signup` | `app/signup.tsx` | إنشاء حساب جديد |
| `/translate` | `app/translate.tsx` | الترجمة بين ١٠ لغات (MyMemory API المجاني) |

## هيكل الملفات

```
hopper/
├── app/                    ← الشاشات (كل ملف = صفحة)
│   ├── _layout.tsx         ← الإطار العام والتنقل
│   ├── +html.tsx           ← قالب HTML لنسخة الويب
│   ├── +not-found.tsx      ← صفحة 404
│   ├── index.tsx
│   ├── login.tsx
│   ├── signup.tsx
│   └── translate.tsx
├── components/             ← مكونات قابلة لإعادة الاستخدام
│   ├── GoogleMap.tsx       ← خريطة Google (ويب فقط، تحتاج API key)
│   ├── ThemedText.tsx
│   └── ThemedView.tsx
├── assets/
│   ├── images/             ← الشعار والخلفيات والأيقونات
│   └── fonts/
├── constants/Colors.ts     ← ألوان الوضع الفاتح والداكن
├── hooks/                  ← useColorScheme و useThemeColor
├── app.json                ← إعدادات Expo (الاسم، الأيقونة، الويب)
├── vercel.json             ← إعدادات الرفع على Vercel
└── netlify.toml            ← إعدادات الرفع على Netlify
```

## التشغيل

```bash
npm install
npx expo start          # ثم اضغطي w للويب، أو امسحي QR بتطبيق Expo Go للجوال
```

## بناء نسخة الويب

```bash
npm run build:web       # يطلع مجلد dist/ جاهز للرفع
```

## الرفع كموقع

- **Vercel:** استوردي الريبو من vercel.com، واضغطي Deploy. الإعدادات موجودة في `vercel.json`.
- **Netlify:** استوردي الريبو، والإعدادات موجودة في `netlify.toml`.

## التقنيات

| التقنية | وين |
|---|---|
| **React Native** | كل الشاشات في `app/` |
| **Expo + Expo Router** | التنقل بالملفات: كل ملف في `app/` يصير صفحة |
| **TypeScript** | كل ملفات `.tsx` و `.ts` |
| **React Native Web** | يحوّل التطبيق لموقع |
| **MyMemory API** | الترجمة في `app/translate.tsx` |
