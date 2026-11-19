# YMS Logistics — Android App + Admin Website

इस प्रोजेक्ट में ग्राहक Android ऐप, Admin Website और Supabase SQL शामिल हैं।

## Supabase सेटअप
1. Supabase → SQL Editor खोलकर `supabase/schema.sql` चलाएँ।
2. Authentication → Users में Admin ईमेल/पासवर्ड यूज़र बनाएँ।
3. उस यूज़र की UUID लेकर SQL Editor में चलाएँ:
   `insert into public.admin_users (user_id) values ('YOUR-ADMIN-USER-UUID');`

## Keys
`apps/customer/.env` बनाएँ:
```
EXPO_PUBLIC_SUPABASE_URL=https://YOUR-PROJECT.supabase.co
EXPO_PUBLIC_SUPABASE_ANON_KEY=YOUR_PUBLISHABLE_OR_ANON_KEY
```
`apps/admin/.env.local` बनाएँ:
```
NEXT_PUBLIC_SUPABASE_URL=https://YOUR-PROJECT.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=YOUR_PUBLISHABLE_OR_ANON_KEY
```
Supabase Project Settings → API से URL और Publishable/anon key लें। Secret/service_role key कभी इस्तेमाल न करें।

## Android ऐप
```
cd apps/customer
npm install
npx expo start
```
Expo Go से QR scan करें। APK/AAB बनाने के लिए बाद में EAS Build करना होगा।

## Admin Website
```
cd apps/admin
npm install
npm run dev
```
ब्राउज़र में http://localhost:3000 खोलें।

यह पूरा source project है, अभी प्रकाशित APK या hosted website नहीं। इंटरनेट पर चलाने और Play Store पर डालने के लिए deployment/build और आपकी Supabase configuration जरूरी है।
