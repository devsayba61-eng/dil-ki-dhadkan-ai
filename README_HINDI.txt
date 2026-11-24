DIL KI DHADKAN AI — REAL AI PHOTO V3
====================================

इस वर्जन में क्या मिलेगा?
- असली AI फोटो बनाना (Cloudflare Workers AI + FLUX.2 klein 4B)
- अपनी Gallery फोटो देकर AI से उसका नया रूप बनवाना
- Cinematic, Portrait, Nature, Vintage, Fantasy, Anime और Realistic Style
- बनी हुई फोटो मोबाइल में Download करना
- फोटो को My Work में सेव करना
- AI सेवा की चाबी (API Token) ऐप में नहीं रखनी; वह सर्वर पर सुरक्षित रहती है

बहुत जरूरी:
यह ZIP तैयार कोड है, अभी लाइव सर्वर नहीं है। केवल RAR में index.html खोलने से AI फोटो नहीं बनेगी। पहले नीचे दिए गए तरीके से Cloudflare Worker चालू करना होगा। उसके बाद Cloudflare का https://...workers.dev लिंक खोलना है।

ANDROID मोबाइल से सेटअप
----------------------
1. Chrome में https://dash.cloudflare.com/ खोलें और Cloudflare अकाउंट बनाएं या Sign in करें।
2. Workers & Pages खोलें। Create application / Create Worker चुनें। Hello World वाला नया Worker बनाकर Deploy करें।
3. बने हुए Worker को खोलें और Edit code दबाएँ। ZIP के अंदर worker.js फाइल खोलकर उसका पूरा कोड कॉपी करें। Cloudflare के editor में पुराना कोड हटाकर पूरा worker.js पेस्ट करें और Deploy दबाएँ।
4. Worker के Settings में Bindings खोलें। Add binding चुनें, Workers AI चुनें और Variable name में ठीक-ठीक AI लिखें। Save/Deploy करें।
5. Settings में Variables and Secrets खोलें। नया Secret बनाएँ। Name में ठीक-ठीक APP_ACCESS_CODE लिखें। Value में अपना निजी नया कोड रखें (Gmail का पासवर्ड बिल्कुल नहीं)। Save/Deploy करें।
6. Worker का https://...workers.dev लिंक खोलें। Dil Ki Dhadkan AI खुलना चाहिए।
7. AI Photo Maker में Access Code वाले बॉक्स में वही निजी कोड डालें। Prompt लिखें, चाहें तो फोटो चुनें, फिर Generate Photo दबाएँ। फोटो बन जाने पर Download बटन दबाएँ।

फ्री उपयोग की सीमा
------------------
Cloudflare Workers AI के Free Workers प्लान में फिलहाल रोज 10,000 Neurons तक मुफ्त allowance है। यह Unlimited नहीं है। रोज की सीमा पूरी होने पर AI generation रुक सकती है और अगली daily reset तक इंतजार करना पड़ सकता है। सीमा से ऊपर उपयोग के लिए paid plan/billing लग सकती है। कोई paid plan चालू करने से पहले मौजूदा कीमत जरूर जाँचें।

सुरक्षा
------
- Cloudflare API Token या Global API Key को ऐप, चैट या किसी कोड में पेस्ट न करें।
- अपना APP_ACCESS_CODE किसी के साथ साझा न करें।
- ऐप केवल आपका Prompt और (यदि चुनी हो) आपकी फोटो आपके Worker को भेजता है ताकि AI फोटो बन सके।
- निजी/संवेदनशील फोटो अपलोड करने से पहले सोचें; चुनी हुई फोटो AI सेवा को भेजी जाती है।

तकनीकी जानकारी
---------------
- AI Model: @cf/black-forest-labs/flux-2-klein-4b
- Worker में Workers AI binding का नाम AI होना चाहिए।
- Worker Secret का नाम APP_ACCESS_CODE होना चाहिए।
- Reference photo मोबाइल में 512px तक resize होकर भेजी जाती है।
- यह मॉडल prompt से नई फोटो बना सकता है और reference photo के आधार पर image editing भी कर सकता है।
