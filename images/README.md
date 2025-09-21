# SimuLearn AI: פלטפורמה לסימולציות חינוכיות מבוססות AI

> **🚧 הפרויקט נמצא כעת בפיתוח פעיל** - תכונות חדשות מתווספות באופן קבוע

פרויקט SimuLearn AI הוא פלטפורמה חדשנית לסימולציות חינוכיות, המפותחת על גבי פלטפורמת Base44. הפרויקט נועד לספק למורים וסטודנטים סביבת למידה חווייתית ואינטראקטיבית באמצעות סימולציות מורכבות, המונעות על ידי בינה מלאכותית.

## הבעיה שאנו פותרים

הלמידה המסורתית בכיתה לוקה לעיתים קרובות בחסר בכל הנוגע להתנסות מעשית ופיתוח מיומנויות של קבלת החלטות בתנאי אי-ודאות. סטודנטים קוראים על תיאוריות, אך רק לעיתים רחוקות זוכים ליישם אותן בעולם דינמי המגיב למעשיהם. SimuLearn AI גובר על פער זה על ידי יצירת "מגרש משחקים" חינוכי, בו ניתן להתנסות, לטעות וללמוד בסביבה בטוחה ומרתקת.

## קהל היעד

*   **מורים ומחנכים:** יכולים ליצור בקלות תרחישי סימולציה מותאמים אישית, לנהל קהילות למידה וקבוצות סטודנטים, לעקוב אחר התקדמות, ולהעריך ביצועים באמצעות כלים מבוססי AI.
*   **סטודנטים ותלמידים:** משתתפים בסימולציות חווייתיות, מקבלים החלטות המשפיעות על עולם המשחק, לומדים מתוך התנסות ועובדים בשיתוף פעולה עם חבריהם לקבוצה.

## תכונות עיקריות

*   **יצירת תרחישים מונחית AI:** אשף אינטואיטיבי המאפשר למורים ליצור סימולציות מקיפות מ"אפס" או על בסיס תבניות קיימות. האשף מסתייע ב-AI לניתוח פדגוגי, יצירת נרטיב, ואיזון משחקיות.
*   **מנוע סימולציה דינמי (Game Loop):** לוגיקה מתקדמת המנהלת את שלבי הסימולציה, מעבדת החלטות של קבוצות, ומעדכנת את מצב עולם המשחק בזמן אמת.
*   **AI Agents ייעודיים:** מערך של סוכני AI הפועלים מאחורי הקלעים כדי להעשיר את החוויה:
    *   `scenario_engine`: מנוע הסימולציה המרכזי.
    *   `scoring_engine`: מנוע ניקוד וחישוב ביצועים.
    *   `economy_balancer`: מאזן את הכלכלה הגלובלית בסימולציה.
    *   `crisis_manager`: יוצר אירועים ומשברים דינמיים.
    *   `adaptive_hints`: מספק רמזים מותאמים אישית לקבוצות מתקשות.
    *   `engagement_nudge`: מעודד מעורבות של סטודנטים פחות פעילים.
    *   `rubric_rater`: מעריך תשובות פתוחות על פי רובריקות שהוגדרו מראש.
*   **ניהול קהילות וקבוצות:** כלים למורים ליצירת קהילות, חלוקת סטודנטים לקבוצות, והזמנת משתתפים.
*   **מערכת הערכה חכמה:** מעקב וניתוח ביצועים מבוסס AI, כולל דוחות מפורטים והערכה אוטומטית באמצעות רובריקות.
*   **אינטגרציה עם Telegram:** בוט טלגרם המאפשר אינטראקציה בזמן אמת, קבלת התראות, והגשת החלטות ישירות מהאפליקציה.
*   **עמידה בדרישות משרד החינוך:** התאמה מלאה לדרישות xAPI לדיווח על פעילויות למידה ומנגנון לניהול הסכמות הורים.

## ארכיטקטורה כללית

תרשים סכמטי של ארכיטקטורת המערכת:

```
+----------------+      +--------------------------------+      +---------------------+
|   Frontend     |      |      Base44 Backend            |      | External Services   |
| (React, Shadcn)|<---->|                                |<---->| (Telegram, LRS)     |
+----------------+      | +------------+  +------------+ |      +---------------------+
                        | |  Functions |  |  Entities  | |
                        | +------------+  +------------+ |
                        | +----------------------------+ |
                        | |         AI Agents          | |
                        | +----------------------------+ |
                        +--------------------------------+
```

## טכנולוגיות בשימוש

*   **פלטפורמה:** Base44 Platform
*   **Frontend:** React, Tailwind CSS, Shadcn/ui
*   **Backend Runtime:** Deno
*   **AI:** מודלי שפה גדולים (LLMs) דרך OpenAI API
*   **אינטגרציות:** Telegram Bot API, xAPI

## לינקים ודוגמאות

*   **אפליקציה חיה:** [WWW.EDULEARNAI.COM](https://WWW.EDULEARNAI.COM)

*   **סרטוני הדגמה:** (במידה וקיימים, הוסף קישור ל-YouTube/Vimeo כאן)
## צילומי מסך

### אשף יצירת תרחישים
![יצירת תרחיש חדש](images/scenario-creation.png)

### דאשבורד מורה
![דאשבורד מורה](images/teacher-dashboard.png)

### ניהול משברים דינמיים
![ניהול משברים](images/crisis-management.png)

### מסך ניהול קהילות
![ניהול קהילות](images/community-management.png)

