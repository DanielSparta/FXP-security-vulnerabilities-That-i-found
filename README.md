# FXP-security-vulnerabilities-That-i-found
FXP-Security-vulnerabilities-That-I-found-and-reported-a-year-ago-and-they-are-still-open-due-to-developers-ignorance


---------------------------------------------------------------------------------------

1. one click Stored XSS at Private messages.
   
We need to get TRUE into "if(is_img_link)":
![image](https://github.com/DanielSparta/FXP-security-vulnerabilities-That-i-found/assets/111179755/3b6ac6fd-6d9f-4824-8340-79977197365f)


Therefore, to make that happen we need to PASS the another if which will make is_img_link true.

****************************************************
The another if conditions:
![image](https://github.com/DanielSparta/FXP-security-vulnerabilities-That-i-found/assets/111179755/cfcea6f9-bd41-4705-a529-e494c5f84710)
![image](https://github.com/DanielSparta/FXP-security-vulnerabilities-That-i-found/assets/111179755/02c60bd6-35d2-4320-b22b-edb11b8f2010)

1. the message must have img element
2. the img element should be a specific link
3. the text must be: "".

   AS YOU CAN SEE THE IF IS A "INCLUDE" THEN I CAN JUST ADD MY XSS
****************************************************

Real time picture:
![image](https://github.com/DanielSparta/FXP-security-vulnerabilities-That-i-found/assets/111179755/c7f79750-8c42-4770-ad30-5fcaa9d55a87)


Thats a cool security vulnerability, And also reported before alot of time.. but is still open.

*NOTE - https://profile.fcdn.co.il/ links are changing automaticly  to https://i.imagesup.co/, that says, that the another side MUST be on the chat AT THE SAME time. because, when reloading the page, or
when entering the page AFTER the attacker already sent the payload, it will not work. TRY TO WRITE A https://profile.fcdn.co.il/ MESSAGE, SEND, THEN RELOAD THE PAGE. IT WILL BE CHANGED.*

---------------------------------------------------------------------------------------

















2. Stored xss at Private messages

   When your writing a Html/JS code, you can simple send this message, then QUOTE it, and it will be triggered.
   ![image](https://github.com/DanielSparta/FXP-security-vulnerabilities-That-i-found/assets/111179755/8fad0e13-1259-47ac-9da8-2afa383193a2)


---------------------------------------------------------------------------------------


















3. Self xss at site search

   The site has a search engine, it has 3 search options, content, forum, and user. The code refers to each of them as a certain name, to the "content" option it is referred to as "data".
   picture: 
   ![image](https://github.com/DanielSparta/FXP-security-vulnerabilities-That-i-found/assets/111179755/e68dacc3-2023-45ff-8be6-66c264b8b130)

   The search is performed inside a form:
   ![image](https://github.com/DanielSparta/FXP-security-vulnerabilities-That-i-found/assets/111179755/52c3683f-ab1f-4578-a327-d222b8ea64fa)


THEN, if we will try to search at CONTENT payload as: "</ form><script>alert()</script>, it will trigger a alert.
I tried to make that a reflected XSS, i failed.

---------------------------------------------------------------------------------------

SQLI (? right now its just a bug) - bug that i found at FXP Search engine. !CTF!
If you search for the following: "asdasdasdcccasasasdva or 1=1" (a long beginning, then or, and then x=x)
Then error will be occurred:
![image](https://github.com/DanielSparta/FXP-security-vulnerabilities-That-i-found/assets/111179755/f05df3af-7100-4bc7-9ac2-6565bda97844)


---------------------------------------------------------------------------------------























4. Stored XSS at Private messages
![image](https://github.com/DanielSparta/FXP-security-vulnerabilities-That-i-found/assets/111179755/8588d228-7fa1-4331-b473-6a6511cc2811)
Creating a payload: "https://profile.fcdn.co.il/images' onerror=alert() title="

So, when you will send this message, QUOTE it, and THEN SENDING IT... then when you will send it, XSS will be trigger for you.
![image](https://github.com/DanielSparta/FXP-security-vulnerabilities-That-i-found/assets/111179755/3b9644a8-cb61-4170-b872-efc06bd0d68f)









הערות אישיות בנוגע ליחס של פורום FXP כלפי האבטחה שלהם וחשיבות הפרטיות של המשתמשים שלהם:

אני מאמין שקיימים עוד חולשות אבטחה למינהם באתר הזה, ורובם בצאט הפרטי של FXP.
מה דעתכם על החולשות הנ"ל, ומה אתם חושבים על FXP שמתעלם מהדיווחים כבר שנה שלמה? האם אבטחת המידע של המשתמשים לא חשובה? אני הייתי מנהל בפורום אבטחת מידע, בעבר, לפני שנה. באותה תקופה, לאחר שאני שלחתי למנכל הודעה שאני רוצה לדווח על חולשות שמצאתי באתר - הדיחו אותי מהצוות בלי לחשוב פעמיים, אחר כך דיווחתי בכל זאת למתכנת, התעלם למשך תקופה, ואז רשמתי לו שאני אפיץ את זה בעוד חודש אם לא יתוקן, שזה הרבה מאוד זמן ובמיוחד בשביל חולשות שלא מסכנות את השרת אלא נטו את המשתמשים... ואכן פרסמתי, והחולשות נשארו פתוחות - וככה בעצם זכיתי לצוות אישי, זאת אומרת, צוות שהתפקיד שלו הוא לאתר אותי ולתת לי באן כל פעם מחדש באתר.
