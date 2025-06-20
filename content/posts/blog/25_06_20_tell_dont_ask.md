---
title: "عن Tell Don't Ask"
date: 2025-06-20
tags: ["OOP", "testing", "mid-level"]
pinned: true
---

## Tell Don't Ask

--- الله ينصر أهلنا في فلسـطــين ويحفظ دمائهم ويهدينا دعمهم🇵🇸 ---

ده واحد من المفاهيم اللي ممكن تساعدك تكتب كود object-oriented أحسن. 
فكرتة ببساطة أنك مش محتاج تسأل الـ object عن معلوماته الداخلية وبعدين تقوله أمر معين. أنت ممكن تقوله الأمر مباشرة وهو يقرر بناءًا على معرفته هو بمعلوماته الداخلية.

= ايه ده؟ هو حد بيعمل كده؟ 🤔

ما تيجي نشوف، عندك order ومحتاج تعمله reject فكاتب كود قبله بيجيب ال status ويتأكد إنها مثلا مش out-for-delivery or delivered عشان تقدر تعمله reject.

```kotlin
if (order.status != "DELIVERED" && order.status != "OUT_FOR_DELIVERY"){
    order.status = "REJECTED"
}
```

المفهوم ده بيقولك متعملش كده، اعمل على طول order.reject والمفروض الـ reject method هي اللي تحتوى الشرط بتاع الـ status مش أنت تكتبه من بره الـ order.

```kotlin
order.reject()
```

= طب ماذا استفدت من هذه القصة؟  

أنت كده عملت التالي:    
١- من ناحية الـ coupling، أنت بقيت بتظهر معلومات أقل. حاليًا مثلا مثلا ممكن متحتاجش تخلي الـ status دي public ممكن تكون private.     
٢- مين الجميل؟؟ الـ code testability.
أنت دلوقت ممكن تختبر ال order أحسن. وهتبقى مركز على اختبار الـ order نفسه، وال reject وممكن تختبرها في كل قيم ال status وتتأكد إنها شغالة صح.
وكمان الجزء اللي بيستخدم الـ order، الـ tests بتاعه تكون مركزة على الـ logic اللي بيحصل فيه ومش محتاج يختبر الـ order.reject عشان بقى لها مكان تاني بيعملها test.   
٣- من ناحية الـ cohesion، الـ order حاليًا واضح فيه ايه العمليات اللي بتتعمل عليه وإزاي هي معتمدة على معلوماته الداخلية.  
٤- إنه بيساعد في تجنب فكرة الـ anemic model.    
٥- هتكون أخدت feedback عن الـ OO design بتاعك، فالكود بيقولك أنت ممكن تعمل ال reject method دي عشان أنت بتعمل الكود بتاعها مش عشان انت كنت مخطط لها.    

لو حسيت إن اللي بقوله مجرد كلام متكرر عن OO، فاحساسك صح 😎  
هو المفهوم ده بيعزز الـ OO👍

هحط لك كام مصدر بيتكلموا عنه أكثر و Coding kata لتجربته.


### مصادر
[١- مارتن فاولر يشرحه](https://martinfowler.com/bliki/TellDontAsk.html)     
[٢- فيديو لطيف بيتكلم عنه](https://youtu.be/-wnt-UH5VBw?si=LfSwFfByNTi0eJLC)    
[٣- الـ Coding kata عشان تجربه](https://kata-log.rocks/tell-dont-ask-kata)  
[٤- حد بيحل ال Coding kata](https://youtu.be/NjPA6K-1tks?si=FaNpaPsMUMBRR5S0 )

—   
لو عجبك المحتوى، تفاعل وانشره 
[LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7341739123906351104) - 
[Qabila](https://qabilah.com/posts/w3DB6cDHbLU)     
لو عندك أي تعليق ، يسعدني معرفة رأيك.   
