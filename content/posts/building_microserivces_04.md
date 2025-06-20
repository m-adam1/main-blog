---
title: "كتاب Building Microservices الجزء 04"
date: 2024-10-03
tags: ["architecture", "microservices"]
pinned: true
cover: "images/cover_part04.png"
---

من كتاب Building Microservices (رقم ٤)

نستكمل مفاهيم الـ Microservices بعد أن تكلمنا في الأجزاء السابقة عن المفاهيم:   
1- *Independent Deployability*   
2- *Modeled Around a Business Domain*   
3- *Owning Their Own State*     
4- *Size*   
5- *Flexibility*    

وبإذن الله نستكمل آخر مفهوم.

— الله ينصر أهلنا في فلسطين والسودان ويحفظ دمائهم وكل بلاد المسلمين 🇵🇸 —

## المفاهيم الرئيسية في ال Microservices (استكمال)

### 6- اتساق المعمارية مع الشركة Alignment of Architecture and Organization

يذكر الكاتب إحدى المعماريات المشهورة Three-tiered Architecture. والذي تتكون فيها الفِرَق من فريق Frontend وفريق للـ Backend وآخر للـ Database Admins.
وأحد أسباب شهرة هذه المعمارية هو أنها واضحة وبسيطة، وبالتالي يسهل تقبلها. ولكن الكاتب يرى أن سبب هذه الشهرة هو اتساق تنظيم المعمارية مع تنظيم الشركات للفِرَق.

وما علاقة كيفية تنظيم الشركة للفرق بالمعمارية المستخدمة؟

ولكي تفهم، يذكر لنا الكاتب ما يعرف بـ Conway's law*
"Organizations which design systems...are constrained to produce designs which are
copies of the communication structures of these organizations."

والذي يفيد بأن الأنظمة المصممة بواسطة شركات تعكس طرق التواصل في هذه الشركات.

ففي الشركات التقنية في الماضي تجد تقسيم الفرق مبني على التخصص عادةً، فكل متخصصي الـ Frontend في فريق الـ Frontend وهكذا للـ Backend و Database Admins. ويكمل بأن هذا التقسيم ليس سيء ولكنه يعزز الفائدة من جمع الأفراد ذوي تخصص معين معًا.

ويوضح أنه مع التغييرات المستمرة في عالمنا، وحاجتنا النهمة إلى سرعة تطوير أنظمة، فإنه حاليًا تتكون الفِرَق من فِرَق أصغر أو أفراد متعددي المواهب لتقليل تناقلات العمل والانقطاعات فيه. وأنه ينبغي أن ينعكس تقسيم النظام على تقسيم الفرق التي تعمل عليه.

ويذكر الكاتب نقطة مهمة وربما تبدو بديهية، وهي أن كل المعماريات ينتهي بها الأمر بتعزيز أهداف ما.
ودعني أصيغها بطريقة أخرى، وهي أن كل معمارية لها اختيارات، وهذه الاختيارات هي ما تعزز مميزات هذه المعمارية، وهي التي تضع التقييدات عليها أيضًا.

تعقيب:فمثلًا الـ Three-tiered architecture تعزز الفائدة من جمع فريق من أهل التخصص الواحد وتسهيل التواصل بينهم، فيسهل استخراج الحل الأفضل من جهة التخصص Technical Functionality.
وبعض المعماريات الأخرى تعزز الفائدة من جمع فريق تحت Business Domain معين، وبالطبع يتكون من تخصصات مختلفة وخبرات متعددة ولكن يجمعهم Business Domain واحد، فيسهل التغيير في Business Functionality.

دعنا نأخذ مثال، في الصورة 1 مثال ذكره الكاتب وهو عبارة عن تطبيق صوتيات، ومطلوب عمل إضافة له، وهي إضافة تصنيف مفضل لكل مستخدم، وهذا الذي تطلب المهام المذكورة، وتم تقسيمها في طبقات بإسم كل فريق.

![image 1](/images/building_microservice_04_1.png)

وفي الصورة يظهر أن نطاق التغيير Scope of change تفرق دمه بين الفِرَق.

ولو قمنا بعمل نفس التغيير المطلوب على معمارية تتمحور على Business Functionality، فسنجد التصور الآتي الذي يجعل scope of change في فريق واحد، فيسهل العمل عليه.

في الصورة 2*: نجد تقسيم الـ Profile Functionality كخاصية مستقلة والتي هي من مسؤولية الـ Customer Microservice

![image 2](building_microservice_04_2.png)

وفي النهاية فإن الـ Microservices تعزز النوع الثاني والذي يتمحور حول الـ Business Domains كما ذكرنا في الكلام عن مفهوم Modeled Around a Business Domain.

وهنا فائدة أخرى أنه ينبغي أن تنظر لما تستخدمه من معمارية - أيًا كانت - وترى ماذا تعزز وماذا تقيد. وهل عندك أي مشكلات نتيجة لاستخدامها؟

—   
هامش

.* Conway's law ذكر في هذا المصدر "How Do Committees Invent"    
.* الصورة 1 و 2  من الكتاب Building Microservices

—   
لو عجبك المحتوى، تفاعل وانشره 
[LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7247502545449844736) - 
[Qabila](https://qabilah.com/posts/dQEDIfqT5ws)     
لو عندك أي تعليق ، يسعدني معرفة رأيك.   
