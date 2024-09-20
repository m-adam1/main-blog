---
title: "ليه بعمل files أكثر كل لما أحسن architecture"
date: 2023-08-12
tags: ["architecture", "mid-level"]
pinned: true
cover: "images/more_files_better_arch_cover.jpeg"
---

## مقدمة

في ال backend:
- لما اشتغلت على كود قديم، كل حاجة كانت بتحصل في ال controller من request validation و DB requests و response presentation.
- بينما في  better architectures بقيت بعمل files أكثر.

 في ال mobile: 
- لما كنت بستخدم MVC وجربت ال MVP لقيت إني كل مرة بعمل presenter وده فايل جديد ب dependency جديدة لل Controller وهكذا لو بتجرب VIPER، وكنت حاسس إني بعقد الموضوع مش بحسنه.
- لما اشتغلت better architectures نفس الفكرة files أكثر.


والملاحظ إنك غالبا كل لما هتحاول تعمل architecture أحسن هتلاقي نفسك بتعمل files أكثر. (العلاقة مش عكسية \*)

وده ليه! عشان ال separation of concerns

## Separation of Concerns & Abstractions

كل لما بتعمل abstract صح، كل لما بتحصل على فوائد، لكن في المقابل ال files بتكثر.

فوائد مثل:
- Testability
- Reusability
- Maintainability

والفوائد دي بتزداد أهميتها واحتياجك لها كل لما ال code بتاعك يكبر، وتحتاج تغير فيه أكثر.

فلو أنت بتحاول تتعلم architecture جديد، أو بتطبق مبدأ جديد، وحسيت بإنك بتعمل files كثير، فأنت مش لوحدك.

جزء مهم أخير هل ال architecture الجديد أيا كان اسمه هيكون أفضل للمشروع بتاعك ولا لا ده سؤال تاني متعلق بتفاصيل كل مشروع.

---
هامش:

\* العلاقة مش عكسية: يعني مش كل لما ال files تكثر كل لما تكون بالضرورة بتعمل حاجة أحسن.