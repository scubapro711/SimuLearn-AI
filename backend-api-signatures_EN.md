# Backend API Signatures

This file describes the signatures (interfaces) of the main Backend functions in the SimuLearn AI project. It does not include implementation code, but focuses on input, output, and the role of each function.

## Core Simulation Functions

```typescript
/**
 * Runs one step in the simulation logic (Game Loop).
 * Retrieves all group decisions, processes them, and updates the game state.
 * @param data - Object containing the active game ID.
 * @returns Promise<void>
 */
async function runSimulationStep(data: { game_id: string }): Promise<void>;

/**
 * Receives and processes a group's decision for the current simulation step.
 * @param data - Object containing the game state ID and the received decision.
 * @returns Promise<DecisionResponse> - Object confirming receipt of the decision.
 */
async function submitDecision(data: { game_state_id: string, decision: object }): Promise<DecisionResponse>;

/**
 * Activates a new simulation based on an existing scenario.
 * Creates the Game, GameState, and initial groups.
 * @param data - Object containing the scenario ID and community ID.
 * @returns Promise<{ game_id: string }>
 */
async function activateSimulation(data: { scenario_id: string, community_id: string }): Promise<{ game_id: string }>;
```

## AI-Powered Functions

```typescript
/**
 * Creates a complete simulation scenario based on a textual prompt from the user.
 * Activates a chain of AI agents to analyze, suggest concepts, and build the scenario.
 * @param data - Object containing the prompt and additional settings.
 * @returns Promise<GameScenario>
 */
async function createScenarioFromPrompt(data: { prompt: string, user_id: string }): Promise<GameScenario>;

/**
 * Analyzes a scenario prompt and provides pedagogical insights and suggestions.
 * @param data - Object containing the prompt to analyze.
 * @returns Promise<AnalysisResult>
 */
async function analyzeScenarioPrompt(data: { prompt: string }): Promise<AnalysisResult>;
```

## xAPI and Compliance Functions

```typescript
/**
 * Generates an xAPI statement based on an activity that occurred in the system.
 * @param data - Object containing activity details and student information.
 * @returns Promise<XapiStatement>
 */
async function generateXapiStatement(data: { 
  activity_type: string, 
  student_id: string, 
  game_state_id: string, 
  details: object 
}): Promise<XapiStatement>;

/**
 * Sends an existing xAPI statement to the configured LRS (Learning Record Store).
 * @param data - Object containing the statement ID to send.
 * @returns Promise<{ success: boolean, lrs_response: object }>
 */
async function sendXapiStatement(data: { statement_id: string }): Promise<{ success: boolean, lrs_response: object }>;

/**
 * Creates or updates parental consent record for a student.
 * @param data - Object containing student and parent information.
 * @returns Promise<ParentConsent>
 */
async function createOrUpdateParentConsent(data: { 
  student_id: string, 
  parent_name: string, 
  parent_email?: string 
}): Promise<ParentConsent>;
```

## Utility Functions

```typescript
/**
 * Retrieves data from the curriculum file (curriculum.json) for mapping purposes.
 * @param data - Object containing subject and grade level.
 * @returns Promise<object>
 */
async function getCurriculumData(data: { subject: string, grade_level: number }): Promise<object>;

/**
 * Handles incoming Telegram webhook requests and processes bot interactions.
 * @param data - Object containing the Telegram update payload.
 * @returns Promise<void>
 */
async function telegramWebhook(data: { update: object }): Promise<void>;
```
