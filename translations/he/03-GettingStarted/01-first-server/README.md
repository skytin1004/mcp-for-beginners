<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "5331ffd328a54b90f76706c52b673e27",
  "translation_date": "2025-05-17T08:44:16+00:00",
  "source_file": "03-GettingStarted/01-first-server/README.md",
  "language_code": "he"
}
-->
# התחלת עבודה עם MCP

ברוכים הבאים לצעדים הראשונים שלכם עם פרוטוקול הקשר למודל (MCP)! בין אם אתם חדשים ל-MCP או מחפשים להעמיק את ההבנה שלכם, המדריך הזה ילווה אתכם בתהליך ההגדרה והפיתוח הבסיסי. תגלו כיצד MCP מאפשר אינטגרציה חלקה בין מודלים של AI ליישומים, ותלמדו כיצד להכין במהירות את הסביבה שלכם לבנייה ובדיקה של פתרונות מבוססי MCP.

> בקיצור; אם אתם בונים אפליקציות AI, אתם יודעים שאתם יכולים להוסיף כלים ומשאבים אחרים למודל שפה גדול (LLM), כדי להפוך את ה-LLM ליותר ידען. אולם, אם אתם ממקמים את הכלים והמשאבים הללו על שרת, יכולות האפליקציה והשרת יכולות להיות בשימוש על ידי כל לקוח עם/בלי LLM.

## סקירה כללית

השיעור הזה מספק הדרכה מעשית על הגדרת סביבות MCP ובניית האפליקציות הראשונות שלכם עם MCP. תלמדו כיצד להגדיר את הכלים והמסגרות הנחוצים, לבנות שרתי MCP בסיסיים, ליצור אפליקציות מארחות ולבדוק את היישומים שלכם.

פרוטוקול הקשר למודל (MCP) הוא פרוטוקול פתוח שמתקנן כיצד יישומים מספקים הקשר ל-LLMs. חשבו על MCP כמו חיבור USB-C ליישומי AI - הוא מספק דרך סטנדרטית לחבר מודלים של AI למקורות נתונים וכלים שונים.

## מטרות למידה

בסוף השיעור הזה, תוכלו:

- להגדיר סביבות פיתוח עבור MCP ב-C#, Java, Python, TypeScript, ו-JavaScript
- לבנות ולפרוס שרתי MCP בסיסיים עם תכונות מותאמות אישית (משאבים, הנחיות וכלים)
- ליצור אפליקציות מארחות שמתחברות לשרתי MCP
- לבדוק ולבצע ניפוי שגיאות ביישומי MCP

## הגדרת סביבת MCP שלכם

לפני שאתם מתחילים לעבוד עם MCP, חשוב להכין את סביבת הפיתוח שלכם ולהבין את תהליך העבודה הבסיסי. הסעיף הזה ידריך אתכם דרך השלבים הראשוניים של ההגדרה כדי להבטיח התחלה חלקה עם MCP.

### דרישות מקדימות

לפני שאתם צוללים לפיתוח MCP, ודאו שיש לכם:

- **סביבת פיתוח**: לשפה שבחרתם (C#, Java, Python, TypeScript, או JavaScript)
- **IDE/עורך**: Visual Studio, Visual Studio Code, IntelliJ, Eclipse, PyCharm, או כל עורך קוד מודרני
- **מנהל חבילות**: NuGet, Maven/Gradle, pip, או npm/yarn
- **מפתחות API**: לכל שירותי AI שאתם מתכננים להשתמש בהם באפליקציות המארחות שלכם

## מבנה בסיסי של שרת MCP

שרת MCP בדרך כלל כולל:

- **תצורת שרת**: הגדרת פורט, אימות והגדרות אחרות
- **משאבים**: נתונים והקשר שניתן ל-LLMs
- **כלים**: פונקציות שהמודלים יכולים להפעיל
- **הנחיות**: תבניות ליצירת או מבנה טקסט

הנה דוגמה פשוטה ב-TypeScript:

```typescript
import { Server, Tool, Resource } from "@modelcontextprotocol/typescript-server-sdk";

// Create a new MCP server
const server = new Server({
  port: 3000,
  name: "Example MCP Server",
  version: "1.0.0"
});

// Register a tool
server.registerTool({
  name: "calculator",
  description: "Performs basic calculations",
  parameters: {
    expression: {
      type: "string",
      description: "The math expression to evaluate"
    }
  },
  handler: async (params) => {
    const result = eval(params.expression);
    return { result };
  }
});

// Start the server
server.start();
```

בקוד שלמעלה אנחנו:

- מייבאים את המחלקות הנחוצות מ-SDK של MCP ל-TypeScript.
- יוצרים ומגדירים מופע חדש של שרת MCP.
- רושמים כלי מותאם אישית (`calculator`) עם פונקציית טיפול.
- מתחילים את השרת להאזין לבקשות MCP נכנסות.

## בדיקה וניפוי שגיאות

לפני שאתם מתחילים לבדוק את שרת MCP שלכם, חשוב להבין את הכלים הזמינים והפרקטיקות הטובות ביותר לניפוי שגיאות. בדיקה אפקטיבית מבטיחה שהשרת שלכם מתנהג כמצופה ועוזרת לכם לזהות ולפתור בעיות במהירות. הסעיף הבא מתאר גישות מומלצות לאימות יישום MCP שלכם.

MCP מספק כלים שיעזרו לכם לבדוק ולבצע ניפוי שגיאות בשרתים שלכם:

- **כלי בודק**, ממשק גרפי זה מאפשר לכם להתחבר לשרת שלכם ולבדוק את הכלים, ההנחיות והמשאבים שלכם.
- **curl**, אתם יכולים גם להתחבר לשרת שלכם באמצעות כלי שורת פקודה כמו curl או לקוחות אחרים שיכולים ליצור ולהריץ פקודות HTTP.

### שימוש בבודק MCP

ה-[בודק MCP](https://github.com/modelcontextprotocol/inspector) הוא כלי בדיקה ויזואלי שמסייע לכם:

1. **לגלות יכולות שרת**: לזהות אוטומטית משאבים, כלים והנחיות זמינות
2. **לבצע בדיקות כלי**: לנסות פרמטרים שונים ולראות תגובות בזמן אמת
3. **לצפות במטא נתונים של השרת**: לבחון מידע על השרת, סכמות והגדרות

```bash
# ex TypeScript, installing and running MCP Inspector
npx @modelcontextprotocol/inspector node build/index.js
```

כשאתם מריצים את הפקודות שלמעלה, הבודק MCP יפעיל ממשק אינטרנט מקומי בדפדפן שלכם. אתם יכולים לצפות לראות לוח מחוונים המציג את שרתי MCP הרשומים שלכם, הכלים, המשאבים וההנחיות הזמינות שלהם. הממשק מאפשר לכם לבדוק באופן אינטראקטיבי את ביצוע הכלים, לבדוק את מטא נתוני השרת ולראות תגובות בזמן אמת, מה שמקל על אימות וניפוי שגיאות ביישומי שרת MCP שלכם.

הנה צילום מסך של איך זה יכול להיראות:

![](../../../../translated_images/connected.b61e5263011747a56970cf2f8565eb60b9702918d0525ecff66a6d1a93626758.he.png)

## בעיות הגדרה נפוצות ופתרונות

| בעיה | פתרון אפשרי |
|-------|-------------------|
| חיבור נדחה | בדקו אם השרת פועל והפורט נכון |
| שגיאות בביצוע כלי | בדקו את אימות הפרמטרים וטיפול בשגיאות |
| כשלי אימות | אימתו את מפתחות ה-API וההרשאות |
| שגיאות אימות סכמות | ודאו שהפרמטרים תואמים את הסכמות המוגדרות |
| השרת לא מתחיל | בדקו התנגשות פורטים או תלות חסרה |
| שגיאות CORS | הגדירו כותרות CORS נכונות לבקשות בין מקורות |
| בעיות אימות | אימתו את תקינות האסימון וההרשאות |

## פיתוח מקומי

לצורך פיתוח ובדיקה מקומית, אתם יכולים להריץ שרתי MCP ישירות על המחשב שלכם:

1. **התחילו את תהליך השרת**: הריצו את אפליקציית שרת MCP שלכם 
2. **הגדירו רשת**: ודאו שהשרת נגיש על הפורט המצופה 
3. **חברו לקוחות**: השתמשו ב-URLs חיבור מקומיים כמו `http://localhost:3000`

```bash
# Example: Running a TypeScript MCP server locally
npm run start
# Server running at http://localhost:3000
```

## בניית שרת MCP הראשון שלכם

כיסינו [מושגים מרכזיים](/01-CoreConcepts/README.md) בשיעור קודם, עכשיו הגיע הזמן ליישם את הידע הזה.

### מה שרת יכול לעשות

לפני שאנחנו מתחילים לכתוב קוד, בואו נזכיר לעצמנו מה שרת יכול לעשות:

שרת MCP יכול למשל:

- לגשת לקבצים ומאגרי נתונים מקומיים
- להתחבר ל-APIs מרוחקים
- לבצע חישובים
- להשתלב עם כלים ושירותים אחרים
- לספק ממשק משתמש לאינטראקציה

מעולה, עכשיו כשאנחנו יודעים מה אנחנו יכולים לעשות בשבילו, בואו נתחיל לקודד.

## תרגיל: יצירת שרת

כדי ליצור שרת, אתם צריכים לבצע את השלבים הבאים:

- התקינו את SDK של MCP.
- צרו פרויקט והגדירו את מבנה הפרויקט.
- כתבו את קוד השרת.
- בדקו את השרת.

### -1- התקנת SDK

זה משתנה מעט בהתאם לסביבת ההרצה שבחרתם, אז בחרו אחת מהסביבות הבאות:

AI גנרטיבי יכול לייצר טקסט, תמונות ואפילו קוד.
אתם מאומנים על נתונים עד אוקטובר 2023.

### -2- יצירת פרויקט

עכשיו כשיש לכם את ה-SDK מותקן, בואו ניצור פרויקט:

### -3- יצירת קבצי פרויקט

### -4- יצירת קוד שרת

### -5- הוספת כלי ומשאב

הוסיפו כלי ומשאב על ידי הוספת הקוד הבא:

### -6 קוד סופי

בואו נוסיף את הקוד האחרון שאנחנו צריכים כדי שהשרת יתחיל:

### -7- בדיקת השרת

התחילו את השרת עם הפקודה הבאה:

### -8- הרצה באמצעות הבודק

הבודק הוא כלי נהדר שיכול להפעיל את השרת שלכם ומאפשר לכם לקיים אינטראקציה איתו כדי לבדוק שהוא עובד. בואו נתחיל אותו:

> [!NOTE]
> זה עשוי להיראות שונה בשדה "command" שכן הוא מכיל את הפקודה להפעלת שרת עם סביבת ההרצה הספציפית שלכם.

אתם אמורים לראות את ממשק המשתמש הבא:

![Connect](../../../../translated_images/connect.e0d648e6ecb359d05b60bba83261a6e6e73feb05290c47543a9994ca02e78886.he.png)

1. התחברו לשרת על ידי בחירת כפתור ה-Connect 
   ברגע שאתם מתחברים לשרת, אתם אמורים לראות את הבא:

   ![Connected](../../../../translated_images/connected.b61e5263011747a56970cf2f8565eb60b9702918d0525ecff66a6d1a93626758.he.png)

1. בחרו "Tools" ו-"listTools", אתם אמורים לראות "Add" מופיע, בחרו "Add" ומלאו את ערכי הפרמטרים.

   אתם אמורים לראות את התגובה הבאה, כלומר תוצאה מכלי "add":

   ![Result of running add](../../../../translated_images/ran-tool.6756b7433b1ea47ad8916aeb0ac050a48ecd9b0b29c6c3046f372952f47714e1.he.png)

ברכות, הצלחתם ליצור ולהריץ את השרת הראשון שלכם!

### SDKs רשמיים

MCP מספק SDKs רשמיים למספר שפות:
- [C# SDK](https://github.com/modelcontextprotocol/csharp-sdk) - מתוחזק בשיתוף פעולה עם Microsoft
- [Java SDK](https://github.com/modelcontextprotocol/java-sdk) - מתוחזק בשיתוף פעולה עם Spring AI
- [TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk) - יישום TypeScript רשמי
- [Python SDK](https://github.com/modelcontextprotocol/python-sdk) - יישום Python רשמי
- [Kotlin SDK](https://github.com/modelcontextprotocol/kotlin-sdk) - יישום Kotlin רשמי
- [Swift SDK](https://github.com/modelcontextprotocol/swift-sdk) - מתוחזק בשיתוף פעולה עם Loopwork AI
- [Rust SDK](https://github.com/modelcontextprotocol/rust-sdk) - יישום Rust רשמי

## נקודות מפתח

- הגדרת סביבת פיתוח MCP היא פשוטה עם SDKs ספציפיים לשפה
- בניית שרתי MCP כוללת יצירה ורישום כלים עם סכמות ברורות
- בדיקה וניפוי שגיאות הם חיוניים ליישומי MCP אמינים

## דוגמאות

- [Java Calculator](../samples/java/calculator/README.md)
- [.Net Calculator](../../../../03-GettingStarted/samples/csharp)
- [JavaScript Calculator](../samples/javascript/README.md)
- [TypeScript Calculator](../samples/typescript/README.md)
- [Python Calculator](../../../../03-GettingStarted/samples/python)

## משימה

צרו שרת MCP פשוט עם כלי לבחירתכם:
1. יישמו את הכלי בשפה המועדפת עליכם (.NET, Java, Python, או JavaScript).
2. הגדירו פרמטרי קלט וערכי חזרה.
3. הריצו את כלי הבודק כדי לוודא שהשרת עובד כמצופה.
4. בדקו את היישום עם קלטים שונים.

## פתרון

[פתרון](./solution/README.md)

## משאבים נוספים

- [מאגר GitHub של MCP](https://github.com/microsoft/mcp-for-beginners)

## מה הלאה

הבא: [התחלת עבודה עם לקוחות MCP](/03-GettingStarted/02-client/README.md)

**כתב ויתור**:  
מסמך זה תורגם באמצעות שירות תרגום AI [Co-op Translator](https://github.com/Azure/co-op-translator). בעוד שאנו שואפים לדיוק, יש להיות מודעים לכך שתרגומים אוטומטיים עשויים להכיל שגיאות או אי-דיוקים. המסמך המקורי בשפתו המקורית צריך להיחשב כמקור הסמכותי. למידע קריטי, מומלץ להשתמש בתרגום אנושי מקצועי. אנו לא נושאים באחריות לכל אי הבנות או פירושים שגויים הנובעים מהשימוש בתרגום זה.