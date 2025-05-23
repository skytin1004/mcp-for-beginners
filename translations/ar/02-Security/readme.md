<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "98be664d3b19a81ee24fa3f920233864",
  "translation_date": "2025-05-17T07:09:02+00:00",
  "source_file": "02-Security/readme.md",
  "language_code": "ar"
}
-->
# أفضل ممارسات الأمان

تبني بروتوكول سياق النموذج (MCP) يجلب قدرات جديدة قوية للتطبيقات المعتمدة على الذكاء الاصطناعي، ولكنه أيضًا يطرح تحديات أمان فريدة تتجاوز المخاطر التقليدية للبرامج. بالإضافة إلى المخاوف المعروفة مثل البرمجة الآمنة، والامتياز الأدنى، وأمان سلسلة التوريد، يواجه MCP وأعباء العمل الخاصة بالذكاء الاصطناعي تهديدات جديدة مثل حقن التعليمات، وتسميم الأدوات، وتعديل الأدوات الديناميكي. يمكن أن تؤدي هذه المخاطر إلى تسريب البيانات، وانتهاكات الخصوصية، وسلوك النظام غير المقصود إذا لم تتم إدارتها بشكل صحيح.

تستكشف هذه الدرس المخاطر الأمنية الأكثر صلة المرتبطة بـ MCP - بما في ذلك المصادقة، والتفويض، والأذونات الزائدة، وحقن التعليمات غير المباشرة، وثغرات سلسلة التوريد - وتقدم ضوابط قابلة للتنفيذ وأفضل الممارسات للتخفيف منها. ستتعلم أيضًا كيفية الاستفادة من حلول Microsoft مثل Prompt Shields، وAzure Content Safety، وGitHub Advanced Security لتعزيز تنفيذ MCP الخاص بك. من خلال فهم وتطبيق هذه الضوابط، يمكنك تقليل احتمال حدوث خرق أمني بشكل كبير وضمان بقاء أنظمة الذكاء الاصطناعي الخاصة بك قوية وجديرة بالثقة.

# أهداف التعلم

بنهاية هذا الدرس، ستكون قادرًا على:

- تحديد وشرح المخاطر الأمنية الفريدة التي يقدمها بروتوكول سياق النموذج (MCP)، بما في ذلك حقن التعليمات، وتسميم الأدوات، والأذونات الزائدة، وثغرات سلسلة التوريد.
- وصف وتطبيق ضوابط التخفيف الفعالة لمخاطر أمان MCP، مثل المصادقة القوية، والامتياز الأدنى، وإدارة الرموز الآمنة، والتحقق من سلسلة التوريد.
- فهم والاستفادة من حلول Microsoft مثل Prompt Shields، وAzure Content Safety، وGitHub Advanced Security لحماية MCP وأعباء العمل الخاصة بالذكاء الاصطناعي.
- التعرف على أهمية التحقق من بيانات الأدوات، ومراقبة التغييرات الديناميكية، والدفاع ضد هجمات حقن التعليمات غير المباشرة.
- دمج أفضل ممارسات الأمان المعروفة - مثل البرمجة الآمنة، وتقوية الخوادم، وهندسة الثقة الصفرية - في تنفيذ MCP الخاص بك لتقليل احتمال وتأثير الخروقات الأمنية.

# ضوابط أمان MCP

أي نظام يتمتع بالوصول إلى موارد مهمة يواجه تحديات أمان ضمنية. يمكن التعامل مع تحديات الأمان بشكل عام من خلال التطبيق الصحيح للضوابط والمفاهيم الأمنية الأساسية. نظرًا لأن MCP تم تعريفه حديثًا فقط، فإن المواصفات تتغير بسرعة كبيرة ومع تطور البروتوكول. في النهاية، ستنضج ضوابط الأمان داخله، مما يمكن من تكامل أفضل مع البنى الأمنية المؤسسية والمعروفة وأفضل الممارسات.

تشير الأبحاث المنشورة في [تقرير الدفاع الرقمي من Microsoft](https://aka.ms/mddr) إلى أن 98% من الخروقات المبلغ عنها كانت ستمنع بواسطة النظافة الأمنية القوية وأفضل حماية ضد أي نوع من الخروقات هي الحصول على نظافة أمان أساسية، وأفضل ممارسات البرمجة الآمنة، وأمان سلسلة التوريد بشكل صحيح - تلك الممارسات المجربة والمختبرة التي نعرفها بالفعل لا تزال تحقق أكبر تأثير في تقليل مخاطر الأمان.

لنلقِ نظرة على بعض الطرق التي يمكنك البدء في معالجة مخاطر الأمان عند تبني MCP.

# مصادقة خادم MCP (إذا كان تنفيذ MCP الخاص بك قبل 26 أبريل 2025)

> **ملاحظة:** المعلومات التالية صحيحة اعتبارًا من 26 أبريل 2025. يتطور بروتوكول MCP باستمرار، وقد تقدم التنفيذات المستقبلية أنماط وضوابط مصادقة جديدة. للحصول على أحدث التحديثات والإرشادات، ارجع دائمًا إلى [مواصفات MCP](https://spec.modelcontextprotocol.io/) والمستودع الرسمي لـ [MCP GitHub](https://github.com/modelcontextprotocol).

### بيان المشكلة 
افترضت المواصفات الأصلية لـ MCP أن المطورين سيكتبون خادم المصادقة الخاص بهم. تطلب ذلك معرفة بـ OAuth والقيود الأمنية ذات الصلة. عملت خوادم MCP كخوادم تفويض OAuth 2.0، تدير المصادقة المطلوبة للمستخدم مباشرة بدلاً من تفويضها لخدمة خارجية مثل Microsoft Entra ID. اعتبارًا من 26 أبريل 2025، يتيح تحديث لمواصفات MCP لخوادم MCP تفويض مصادقة المستخدم إلى خدمة خارجية.

### المخاطر
- يمكن أن يؤدي منطق التفويض المكون بشكل خاطئ في خادم MCP إلى كشف بيانات حساسة وتطبيق ضوابط وصول غير صحيحة.
- سرقة رمز OAuth على خادم MCP المحلي. إذا سُرق، يمكن استخدام الرمز لانتحال شخصية خادم MCP والوصول إلى الموارد والبيانات من الخدمة التي يكون رمز OAuth لها.

### ضوابط التخفيف
- **مراجعة وتقوية منطق التفويض:** قم بتدقيق تنفيذ التفويض في خادم MCP بعناية لضمان أن المستخدمين والعملاء المقصودين فقط يمكنهم الوصول إلى الموارد الحساسة. للحصول على إرشادات عملية، راجع [إدارة واجهة برمجة التطبيقات Azure بوابة المصادقة لخوادم MCP | مجتمع Microsoft](https://techcommunity.microsoft.com/blog/integrationsonazureblog/azure-api-management-your-auth-gateway-for-mcp-servers/4402690) و[استخدام Microsoft Entra ID للمصادقة مع خوادم MCP عبر الجلسات - دن دليمارسكي](https://den.dev/blog/mcp-server-auth-entra-id-session/).
- **فرض ممارسات الرموز الآمنة:** اتبع [أفضل ممارسات Microsoft للتحقق من الرموز وعمرها](https://learn.microsoft.com/en-us/entra/identity-platform/access-tokens) لمنع إساءة استخدام الرموز وتقليل خطر إعادة تشغيل أو سرقة الرموز.
- **حماية تخزين الرموز:** قم دائمًا بتخزين الرموز بأمان واستخدم التشفير لحمايتها أثناء الراحة وفي النقل. للحصول على نصائح التنفيذ، راجع [استخدام تخزين الرموز الآمن وتشفير الرموز](https://youtu.be/uRdX37EcCwg?si=6fSChs1G4glwXRy2).

# الأذونات الزائدة لخوادم MCP

### بيان المشكلة
قد تم منح خوادم MCP أذونات زائدة للخدمة/المورد الذي تصل إليه. على سبيل المثال، يجب أن يكون لخادم MCP الذي يعد جزءًا من تطبيق مبيعات الذكاء الاصطناعي يتصل بمخزن بيانات الشركة وصول محدد إلى بيانات المبيعات ولا يسمح له بالوصول إلى جميع الملفات في المخزن. بالإشارة إلى مبدأ الامتياز الأدنى (أحد أقدم المبادئ الأمنية)، لا يجب أن يكون لأي مورد أذونات تزيد عما هو مطلوب لتنفيذ المهام التي كان مقصودًا بها. يمثل الذكاء الاصطناعي تحديًا متزايدًا في هذا المجال لأنه لتمكينه من أن يكون مرنًا، يمكن أن يكون من الصعب تحديد الأذونات الدقيقة المطلوبة.

### المخاطر 
- يمكن أن يؤدي منح أذونات زائدة إلى تسريب أو تعديل بيانات لم يكن من المفترض أن يتمكن خادم MCP من الوصول إليها. يمكن أن يكون هذا أيضًا مشكلة خصوصية إذا كانت البيانات معلومات تعريف شخصية (PII).

### ضوابط التخفيف
- **تطبيق مبدأ الامتياز الأدنى:** امنح خادم MCP الحد الأدنى من الأذونات اللازمة لأداء مهامه المطلوبة. قم بمراجعة وتحديث هذه الأذونات بانتظام لضمان عدم تجاوزها لما هو مطلوب. للحصول على إرشادات مفصلة، راجع [الوصول الآمن الأقل امتيازًا](https://learn.microsoft.com/entra/identity-platform/secure-least-privileged-access).
- **استخدام التحكم في الوصول المستند إلى الأدوار (RBAC):** تعيين الأدوار لخادم MCP التي تكون محددة بدقة للموارد والإجراءات المحددة، وتجنب الأذونات العامة أو غير الضرورية.
- **مراقبة وتدقيق الأذونات:** مراقبة استخدام الأذونات باستمرار وتدقيق سجلات الوصول لاكتشاف ومعالجة الامتيازات الزائدة أو غير المستخدمة على الفور.

# هجمات حقن التعليمات غير المباشرة

### بيان المشكلة

يمكن أن تقدم خوادم MCP الخبيثة أو المخترقة مخاطر كبيرة عن طريق كشف بيانات العملاء أو تمكين إجراءات غير مقصودة. هذه المخاطر ذات صلة خاصة في أعباء العمل المستندة إلى الذكاء الاصطناعي وMCP، حيث:

- **هجمات حقن التعليمات:** يقوم المهاجمون بتضمين تعليمات خبيثة في المطالبات أو المحتوى الخارجي، مما يتسبب في قيام نظام الذكاء الاصطناعي بإجراءات غير مقصودة أو تسريب بيانات حساسة. تعرف على المزيد: [حقن التعليمات](https://simonwillison.net/2025/Apr/9/mcp-prompt-injection/)
- **تسميم الأدوات:** يقوم المهاجمون بتعديل بيانات الأدوات (مثل الأوصاف أو المعلمات) للتأثير على سلوك الذكاء الاصطناعي، مما قد يتجاوز الضوابط الأمنية أو يسرب البيانات. التفاصيل: [تسميم الأدوات](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks)
- **حقن التعليمات عبر المجالات:** يتم تضمين تعليمات خبيثة في المستندات أو صفحات الويب أو رسائل البريد الإلكتروني، التي تتم معالجتها بعد ذلك بواسطة الذكاء الاصطناعي، مما يؤدي إلى تسريب البيانات أو التلاعب بها.
- **تعديل الأدوات الديناميكي (سحب السجادة):** يمكن تغيير تعريفات الأدوات بعد موافقة المستخدم، مما يؤدي إلى إدخال سلوكيات خبيثة جديدة دون علم المستخدم.

تسلط هذه الثغرات الضوء على الحاجة إلى التحقق الصارم، والمراقبة، والضوابط الأمنية عند دمج خوادم وأدوات MCP في بيئتك. للحصول على فهم أعمق، راجع المراجع المرتبطة أعلاه.

**حقن التعليمات غير المباشرة** (المعروف أيضًا باسم حقن التعليمات عبر المجالات أو XPIA) هو ثغرة خطيرة في الأنظمة الذكية التوليدية، بما في ذلك تلك التي تستخدم بروتوكول سياق النموذج (MCP). في هذا الهجوم، يتم إخفاء تعليمات خبيثة داخل محتوى خارجي - مثل المستندات، أو صفحات الويب، أو رسائل البريد الإلكتروني. عندما يقوم نظام الذكاء الاصطناعي بمعالجة هذا المحتوى، قد يفسر التعليمات المضمنة كأوامر مستخدم شرعية، مما يؤدي إلى إجراءات غير مقصودة مثل تسريب البيانات، أو توليد محتوى ضار، أو التلاعب بتفاعلات المستخدم. للحصول على شرح مفصل وأمثلة من العالم الواقعي، راجع [حقن التعليمات](https://simonwillison.net/2025/Apr/9/mcp-prompt-injection/).

شكل خطير بشكل خاص من هذا الهجوم هو **تسميم الأدوات**. هنا، يقوم المهاجمون بحقن تعليمات خبيثة في بيانات الأدوات الخاصة بـ MCP (مثل أوصاف الأدوات أو المعلمات). نظرًا لأن النماذج اللغوية الكبيرة (LLMs) تعتمد على هذه البيانات لتقرير الأدوات التي سيتم استدعاؤها، يمكن للأوصاف المخترقة خداع النموذج لتنفيذ استدعاءات أدوات غير مصرح بها أو تجاوز الضوابط الأمنية. غالبًا ما تكون هذه التلاعبات غير مرئية للمستخدمين النهائيين ولكن يمكن تفسيرها والتصرف بناءً عليها بواسطة نظام الذكاء الاصطناعي. يزداد هذا الخطر في بيئات خوادم MCP المستضافة، حيث يمكن تحديث تعريفات الأدوات بعد موافقة المستخدم - وهو سيناريو يُشار إليه أحيانًا بـ "[سحب السجادة](https://www.wiz.io/blog/mcp-security-research-briefing#remote-servers-22)". في مثل هذه الحالات، يمكن أن يتم تعديل أداة كانت آمنة سابقًا لتقوم بإجراءات خبيثة لاحقًا، مثل تسريب البيانات أو تغيير سلوك النظام، دون علم المستخدم. لمزيد من المعلومات حول هذا الهجوم، راجع [تسميم الأدوات](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks).

## المخاطر
تقدم الإجراءات غير المقصودة للذكاء الاصطناعي مجموعة متنوعة من المخاطر الأمنية التي تشمل تسريب البيانات وانتهاكات الخصوصية.

### ضوابط التخفيف
### استخدام دروع التعليمات لحماية ضد هجمات حقن التعليمات غير المباشرة
-----------------------------------------------------------------------------

**دروع التعليمات للذكاء الاصطناعي** هي حل طورته Microsoft للدفاع ضد هجمات حقن التعليمات المباشرة وغير المباشرة. تساعد من خلال:

1.  **الكشف والتصفية**: تستخدم دروع التعليمات خوارزميات تعلم الآلة المتقدمة ومعالجة اللغة الطبيعية للكشف عن التعليمات الخبيثة المضمنة في المحتوى الخارجي، مثل المستندات، أو صفحات الويب، أو رسائل البريد الإلكتروني، وتصفية هذه التعليمات.
    
2.  **التسليط**: تساعد هذه التقنية نظام الذكاء الاصطناعي في التمييز بين تعليمات النظام الصالحة والمدخلات الخارجية المحتملة غير الموثوقة. من خلال تحويل نص المدخلات بطريقة تجعله أكثر صلة بالنموذج، يضمن التسليط أن الذكاء الاصطناعي يمكنه التعرف بشكل أفضل على التعليمات الخبيثة وتجاهلها.
    
3.  **الفواصل وعلامات البيانات**: تضمين الفواصل في رسالة النظام يوضح بشكل صريح موقع نص المدخلات، مما يساعد نظام الذكاء الاصطناعي على التعرف على المدخلات وفصلها عن المحتوى الخارجي المحتمل الضار. تمتد علامات البيانات هذا المفهوم باستخدام علامات خاصة لتسليط الضوء على حدود البيانات الموثوقة وغير الموثوقة.
    
4.  **المراقبة والتحديثات المستمرة**: تراقب Microsoft باستمرار وتحدث دروع التعليمات لمعالجة التهديدات الجديدة والمتطورة. يضمن هذا النهج الاستباقي أن تظل الدفاعات فعالة ضد أحدث تقنيات الهجوم.
    
5. **التكامل مع أمان محتوى Azure:** تعد دروع التعليمات جزءًا من مجموعة أمان محتوى Azure AI الأوسع، التي توفر أدوات إضافية للكشف عن محاولات كسر الحماية، والمحتوى الضار، والمخاطر الأمنية الأخرى في تطبيقات الذكاء الاصطناعي.

يمكنك قراءة المزيد عن دروع التعليمات للذكاء الاصطناعي في [وثائق دروع التعليمات](https://learn.microsoft.com/azure/ai-services/content-safety/concepts/jailbreak-detection).

### أمان سلسلة التوريد

يظل أمان سلسلة التوريد أساسيًا في عصر الذكاء الاصطناعي، ولكن نطاق ما يشكل سلسلة التوريد الخاصة بك قد توسع. بالإضافة إلى حزم التعليمات البرمجية التقليدية، يجب عليك الآن التحقق بدقة ومراقبة جميع المكونات المتعلقة بالذكاء الاصطناعي، بما في ذلك النماذج الأساسية، وخدمات التضمين، ومزودي السياق، وواجهات برمجة التطبيقات التابعة لجهات خارجية. يمكن لكل من هذه المكونات أن يقدم ثغرات أو مخاطر إذا لم تتم إدارتها بشكل صحيح.

**ممارسات أمان سلسلة التوريد الرئيسية للذكاء الاصطناعي وMCP:**
- **التحقق من جميع المكونات قبل التكامل:** يشمل ذلك ليس فقط المكتبات مفتوحة المصدر، بل أيضًا نماذج الذكاء الاصطناعي، ومصادر البيانات، وواجهات برمجة التطبيقات الخارجية. تحقق دائمًا من الأصل، والترخيص، والثغرات المعروفة.
- **الحفاظ على خطوط نشر آمنة:** استخدم خطوط CI/CD المؤتمتة مع فحص الأمان المتكامل لاكتشاف المشكلات مبكرًا. تأكد من نشر القطع الأثرية الموثوقة فقط في الإنتاج.
- **المراقبة والتدقيق المستمر:** قم بتنفيذ المراقبة المستمرة لجميع الاعتمادات، بما في ذلك النماذج وخدمات البيانات، للكشف عن ثغرات جديدة أو هجمات سلسلة التوريد.
- **تطبيق الامتياز الأدنى وضوابط الوصول:** قم بتقييد الوصول إلى النماذج والبيانات والخدمات إلى ما هو ضروري فقط لوظيفة خادم MCP الخاص بك.
- **الاستجابة السريعة للتهديدات:** قم بوضع عملية لتصحيح أو استبدال المكونات المخترقة، ولتدوير الأسرار أو بيانات الاعتماد إذا تم اكتشاف خرق.

يوفر [GitHub Advanced Security](https://github.com/security/advanced-security) ميزات مثل فحص الأسرار، وفحص الاعتمادات، وتحليل CodeQL. تتكامل هذه الأدوات مع [Azure DevOps](https://azure.microsoft.com/en-us/products/devops) و[Azure Repos](https://azure.microsoft.com/en-us/products/devops/repos/) لمساعدة الفرق على تحديد وتخفيف الثغرات عبر كل من التعليمات البرمجية ومكونات سلسلة توريد الذكاء الاصطناعي.

تقوم Microsoft أيضًا بتنفيذ ممارسات أمان سلسلة التوريد الواسعة داخليًا لجميع المنتجات. تعرف على المزيد في [رحلة تأمين سلسلة توريد البرامج في Microsoft](https://devblogs.microsoft.com/engineering-at-microsoft/the-journey-to-secure-the-software-supply-chain-at-microsoft/).

# أفضل ممارسات الأمان المعروفة التي سترفع من مستوى أمان تنفيذ MCP الخاص بك

أي تنفيذ لـ MCP يرث الوضع الأمني القائم لبيئة مؤسستك التي تم بناؤها عليها، لذلك عند النظر في أمان MCP كعنصر من عناصر أنظمة الذكاء الاصطناعي الشاملة الخاصة بك، يوصى بالنظر في رفع مستوى الوضع الأمني القائم الخاص بك. الضوابط الأمنية المعروفة التالية ذات صلة خاصة:

-   أفضل ممارسات البرمجة الآمنة في تطبيق الذكاء الاصطناعي الخاص بك - الحماية ضد [أفضل 10 من OWASP](https://owasp.org/www-project-top-ten/)، [أفضل 10 من OWASP للنماذج اللغوية الكبيرة](https://genai.owasp.org/download/43299/?tmstv=1731900559)، استخدام الخزائن الآمنة للأسرار والرموز، تنفيذ الاتصالات الآمنة من البداية إلى النهاية بين جميع مكونات التطبيق، إلخ.
-   تقوية الخوادم - استخدام المصادقة متعددة العوامل حيثما أم
- [OWASP أعلى 10 لـ LLMs](https://genai.owasp.org/download/43299/?tmstv=1731900559)
- [GitHub للأمان المتقدم](https://github.com/security/advanced-security)
- [Azure DevOps](https://azure.microsoft.com/products/devops)
- [Azure Repos](https://azure.microsoft.com/products/devops/repos/)
- [رحلة تأمين سلسلة توريد البرمجيات في مايكروسوفت](https://devblogs.microsoft.com/engineering-at-microsoft/the-journey-to-secure-the-software-supply-chain-at-microsoft/)
- [الوصول الآمن ذو الامتيازات الأقل (مايكروسوفت)](https://learn.microsoft.com/entra/identity-platform/secure-least-privileged-access)
- [أفضل الممارسات للتحقق من الرموز وصلاحيتها](https://learn.microsoft.com/entra/identity-platform/access-tokens)
- [استخدام تخزين الرموز الآمن وتشفير الرموز (YouTube)](https://youtu.be/uRdX37EcCwg?si=6fSChs1G4glwXRy2)
- [إدارة واجهة برمجة تطبيقات Azure كبوابة مصادقة لـ MCP](https://techcommunity.microsoft.com/blog/integrationsonazureblog/azure-api-management-your-auth-gateway-for-mcp-servers/4402690)
- [استخدام Microsoft Entra ID للمصادقة مع خوادم MCP](https://den.dev/blog/mcp-server-auth-entra-id-session/)

### التالي 

التالي: [الفصل الثالث: البدء](/03-GettingStarted/README.md)

**إخلاء المسؤولية**:  
تم ترجمة هذه الوثيقة باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار الوثيقة الأصلية بلغتها الأصلية المصدر الرسمي. للحصول على معلومات حاسمة، يُوصى بالترجمة البشرية المهنية. نحن غير مسؤولين عن أي سوء فهم أو تفسير خاطئ ينشأ عن استخدام هذه الترجمة.