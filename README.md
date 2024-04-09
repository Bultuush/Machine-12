# Machine-12 "POTATO (SUNCSR): 1"
**netdiscover**

![image](https://github.com/Bultuush/Machine-12/assets/129934501/59efe2ca-da02-41e5-bb9d-325a58b88f5e)

**nmap -p-**

![image](https://github.com/Bultuush/Machine-12/assets/129934501/a3f1cf2a-a166-43f6-a136-302379fcc114)

Бидэнд http болон tcp/7120 байгаа бөгөөд энэ нь ssh-ийн өөр порт бололтой. Энэ нь бид яагаад бүх tcp портуудыг (-p-) анх скан хийхдээ хийдэг болохыг харуулсан сайн жишээ юм.

website-д орж үзэв.

![image](https://github.com/Bultuush/Machine-12/assets/129934501/14b12a0e-0f60-4b93-adfe-1f3ecd379f96)

gobuster ашиглан нуугдсан file байгаа эсэхийг шалгаж үзэв.

![image](https://github.com/Bultuush/Machine-12/assets/129934501/d1c5c371-100b-4b2c-89d7-0b80e9481126)

Би олон үгийн жагсаалт болон далд хавтас эсвэл файл хайж буй арав гаруй өөр файлын өргөтгөлүүдийг туршиж үзсэн. Би бүрэн хоосон ирлээ. Гэсэн хэдий ч, би өмнө нь энэ бүтээгчийн хайрцгийг хийж байсан бөгөөд "Хэрэв та гацах юм бол лабораторийн нэрээр дахин оролдоно уу" гэсэн зөвлөмжтэй хослуулан би "төмс" хэрэглэгчийн нэр болон нууц үг ашиглан ssh нэвтрэхийг hydra ашиглан бүдүүлэг хүчээр хийхийг оролдсон. rockyou.txt жагсаалт.

![image](https://github.com/Bultuush/Machine-12/assets/129934501/f508ce70-f021-4b80-a82e-77148b7f937b)

Эндээс ssh port-ын **username:potato password:'letmein**

![image](https://github.com/Bultuush/Machine-12/assets/129934501/8ee75c74-ca95-497e-900d-670b03b7ebfb)

Эргээд харахад, бид нэвтрэх баннераас root escalation-ыг авахын тулд шаардлагатай бүх мэдээлэлтэй байгаа, гэхдээ тэр үед би өөрийн стандарт privesc шалгалтуудыг эхлүүлсэн. Linpeas.sh нэн даруй цөмийн 3.13.0–24-ерөнхий хувилбарыг хуучирсан гэж тэмдэглэсэн тул би privesc-д зориулсан цөмийн ашиглалтын талаар судлах ажилд орлоо.

Хайрцагыг дахин ачаалсны дараа би exploit-db.com дээр цөмийн эксплойт хайлтаа үргэлжлүүлэв. Сонирхолтой харагдаж байсан дараагийн мөлжлөг бол энэ байсан: https://www.exploit-db.com/exploits/37292 . Бид exploit-db-ийн оруулгаас харахад энэ нь манай цөмийн болон үйлдлийн системийн хувилбарт тохирсон локал privesc exploit гэдгийг харж байна.

![image](https://github.com/Bultuush/Machine-12/assets/129934501/e57c9b89-d54a-44e3-9af1-050d686e9f67)

Би энэ exploit-г Кали хайрцагтаа татаж аваад SimpleHTTPServer-ийг ажиллуулснаар Potato руу татаж авах боломжтой болсон.

![image](https://github.com/Bultuush/Machine-12/assets/129934501/b7cf90ff-4d86-48a9-88cd-e7ce5400574b)

Үүний дараа ашиглах зааварчилгааг дагаж хөрвүүлээд ашиглах хэрэгтэй.

![image](https://github.com/Bultuush/Machine-12/assets/129934501/59d86782-0ed6-416d-bc9f-ac0866aabb62)

![image](https://github.com/Bultuush/Machine-12/assets/129934501/9a5cff49-e003-4852-b7ea-c60de3ead9fb)
