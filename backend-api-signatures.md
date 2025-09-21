'''markdown
# Backend API Signatures

קובץ זה מתאר את החתימות (interfaces) של פונקציות ה-Backend העיקריות בפרויקט SimuLearn AI. הוא אינו כולל את קוד המימוש, אלא מתמקד בקלט, בפלט, ובתפקיד של כל פונקציה.

### Core Simulation Functions

```typescript
/**
 * מריץ צעד אחד בלוגיקת הסימולציה (Game Loop).
 * מאחזר את כל החלטות הקבוצות, מעבד אותן, ומעדכן את מצב המשחק.
 * @param data - אובייקט המכיל את מזהה המשחק הפעיל.
 * @returns Promise<void>
 */
async function runSimulationStep(data: { game_id: string }): Promise<void>;

/**
 * מקבל ומעבד החלטה של קבוצה עבור שלב נוכחי בסימולציה.
 * @param data - אובייקט המכיל את מזהה מצב המשחק וההחלטה שהתקבלה.
 * @returns Promise<DecisionResponse> - אובייקט המאשר את קבלת ההחלטה.
 */
async function submitDecision(data: { game_state_id: string, decision: object }): Promise<DecisionResponse>;

/**
 * מפעיל סימולציה חדשה על בסיס תרחיש קיים.
 * יוצר את ה-Game, GameState, והקבוצות הראשוניות.
 * @param data - אובייקט המכיל את מזהה התרחיש ומזהה הקהילה.
 * @returns Promise<{ game_id: string }>
 */
async function activateSimulation(data: { scenario_id: string, community_id: string }): Promise<{ game_id: string }>;
```

### AI-Powered Functions

```typescript
/**
 * יוצר תרחיש סימולציה מלא על בסיס פרומפט טקסטואלי מהמשתמש.
 * מפעיל שרשרת של סוכני AI כדי לנתח, להציע קונספטים, ולבנות את התרחיש.
 * @param data - אובייקט המכיל את הפרומפט והגדרות נוספות.
 * @returns Promise<GameScenario>
 */
async function createScenarioFromPrompt(data: { prompt: string, user_id: string }): Promise<GameScenario>;
```
'''
