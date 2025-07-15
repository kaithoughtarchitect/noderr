# Noderr

Your AI already knows how to code. Noderr teaches it how to engineer.

---

## Documentation

- **[Getting Started](./docs/getting-started.md)** - Complete user guide and first steps
- **[Understanding Noderr](./docs/understanding-noderr.md)** - Deep dive into concepts and architecture  
- **[Prompts Guide](./docs/noderr-prompts-guide.md)** - Command reference for all workflows
- **[Visual Guide](./docs/noderr-visual-guide.md)** - Visual roadmap of files and structure
- **[Installation](./INSTALL.md)** - Quick setup instructions

## What is Noderr?

Noderr gives AI what every senior developer has: **permanent memory** and **system understanding**.

### Quick Start

1. **Prepare Your Vision** - Create blueprint, project overview, and architecture documents
2. **Build Initial Prototype** - AI creates your first version based on the plans
3. **Install Noderr** - Extract framework and reconcile with what was built
4. **Develop Systematically** - Use the Noderr loop for all future development

*Noderr documents what you ACTUALLY built, not just what you planned.*

### Prerequisites
- Any AI assistant that can read/write files (ChatGPT, Claude, Cursor, etc.)
- Basic familiarity with AI-assisted coding
- A project idea (new or existing)

---

## The Noderr Difference

### 1. Building Blocks with Identity (NodeIDs)

Every piece of your system gets a unique, permanent name:
- `UI_LoginForm` - That specific login form
- `API_AuthCheck` - That specific authentication endpoint  
- `SVC_TokenValidator` - That specific validation service

Unlike traditional AI coding where the AI forgets what it built between conversations, NodeIDs give each building block a permanent identity that persists forever.

**The Impact:** Instead of "update the login", you can say "update `API_AuthCheck`" and the AI knows EXACTLY what you mean, even months later.

### 2. Visual Architecture That Remembers

These NodeIDs aren't just labels - they live in a visual map (Mermaid diagram) that shows:
- **WHERE** each piece fits in your system
- **HOW** it connects to other pieces
- **WHAT** depends on it

```mermaid
graph TD
    %% --- Legend ---
    subgraph Legend
        direction TB
        L_IDConv[NodeID Convention: TYPE_DescriptiveName]
        L_UI[/UI Component/] --- L_UIDesc(User Interface)
        L_API{{API Endpoint}} --- L_APIDesc(REST API Routes)
        L_SVC[[Service Layer]] --- L_SvcDesc(Business Logic)
        L_DB[(Database)] --- L_DBDesc(Data Operations)
        L_Decision{Decision} --- L_DecDesc(Conditional Flow)
        L_State[["State Manager"]] --- L_StateDesc(Client State)
        L_External{{External API}} --- L_ExtDesc(3rd Party Service)
    end

    %% --- Entry Flow ---
    APP_Start((User Opens App)):::./specs/APP_Start.md --> AUTH_Check{User Logged In?}:::./specs/AUTH_Check.md
    
    %% --- Authentication Subgraph ---
    subgraph "Authentication System"
        AUTH_Check -->|No| UI_LoginPage[/Login Page/]:::./specs/UI_LoginPage.md
        UI_LoginPage --> UI_LoginForm[/Login Form/]:::./specs/UI_LoginForm.md
        UI_LoginForm -->|Submit| API_Login{{POST /api/auth/login}}:::./specs/API_Login.md
        
        API_Login --> SVC_AuthValidator[[Auth Validator Service]]:::./specs/SVC_AuthValidator.md
        SVC_AuthValidator --> DB_Users[(Users Database)]:::./specs/DB_Users.md
        
        DB_Users --> LoginResult{Valid Credentials?}:::./specs/LoginResult.md
        LoginResult -->|No| UI_LoginError[/Show Login Error/]:::./specs/UI_LoginError.md
        LoginResult -->|Yes| SVC_TokenGenerator[[Token Generator]]:::./specs/SVC_TokenGenerator.md
        
        UI_LoginError --> UI_LoginForm
        SVC_TokenGenerator --> API_Login
        API_Login -->|Success| STATE_UserSession[["Store User Session"]]:::./specs/STATE_UserSession.md
    end
    
    %% --- Main Application ---
    AUTH_Check -->|Yes| UI_Dashboard[/Dashboard/]:::./specs/UI_Dashboard.md
    STATE_UserSession --> UI_Dashboard
    
    subgraph "E-Commerce Flow"
        UI_Dashboard --> UI_ProductGrid[/Product Grid/]:::./specs/UI_ProductGrid.md
        UI_ProductGrid --> UI_ProductCard[/Product Card/]:::./specs/UI_ProductCard.md
        
        UI_ProductCard -->|View Details| UI_ProductModal[/Product Details Modal/]:::./specs/UI_ProductModal.md
        UI_ProductCard -->|Quick Add| STATE_CartManager[["Cart State Manager"]]:::./specs/STATE_CartManager.md
        
        UI_ProductModal -->|Add to Cart| STATE_CartManager
        STATE_CartManager -->|Update| UI_CartIcon[/Cart Icon Badge/]:::./specs/UI_CartIcon.md
        
        UI_CartIcon -->|Click| UI_CartDrawer[/Shopping Cart Drawer/]:::./specs/UI_CartDrawer.md
        UI_CartDrawer -->|Checkout| UI_CheckoutFlow[/Checkout Page/]:::./specs/UI_CheckoutFlow.md
    end
    
    subgraph "Checkout Processing"
        UI_CheckoutFlow --> API_CreateOrder{{POST /api/orders}}:::./specs/API_CreateOrder.md
        API_CreateOrder --> SVC_OrderProcessor[[Order Processor]]:::./specs/SVC_OrderProcessor.md
        
        SVC_OrderProcessor --> SVC_InventoryCheck[[Inventory Service]]:::./specs/SVC_InventoryCheck.md
        SVC_InventoryCheck --> DB_Inventory[(Inventory DB)]:::./specs/DB_Inventory.md
        
        DB_Inventory --> StockCheck{Items In Stock?}:::./specs/StockCheck.md
        StockCheck -->|No| UI_StockError[/Out of Stock Error/]:::./specs/UI_StockError.md
        StockCheck -->|Yes| SVC_PaymentGateway[[Payment Service]]:::./specs/SVC_PaymentGateway.md
        
        SVC_PaymentGateway --> EXT_Stripe{{Stripe API}}:::./specs/EXT_Stripe.md
        EXT_Stripe --> PaymentResult{Payment Success?}:::./specs/PaymentResult.md
        
        PaymentResult -->|No| UI_PaymentError[/Payment Failed/]:::./specs/UI_PaymentError.md
        PaymentResult -->|Yes| DB_Orders[(Orders Database)]:::./specs/DB_Orders.md
        
        DB_Orders --> SVC_EmailService[[Email Service]]:::./specs/SVC_EmailService.md
        SVC_EmailService --> EXT_SendGrid{{SendGrid API}}:::./specs/EXT_SendGrid.md
        
        DB_Orders --> UI_OrderSuccess[/Order Confirmation/]:::./specs/UI_OrderSuccess.md
    end
    
    %% --- Error Handling Flow ---
    subgraph "Error Management"
        API_Login -->|Error| UI_ErrorToast[/Error Toast Notification/]:::./specs/UI_ErrorToast.md
        API_CreateOrder -->|Error| UI_ErrorToast
        EXT_Stripe -->|Error| UI_ErrorToast
        EXT_SendGrid -->|Error| SVC_ErrorLogger[[Error Logger]]:::./specs/SVC_ErrorLogger.md
        SVC_ErrorLogger --> DB_ErrorLogs[(Error Logs)]:::./specs/DB_ErrorLogs.md
    end
    
    %% --- Search Feature ---
    subgraph "Product Search"
        UI_Dashboard --> UI_SearchBar[/Search Bar/]:::./specs/UI_SearchBar.md
        UI_SearchBar -->|Type| SVC_SearchDebounce[[Debounce Service]]:::./specs/SVC_SearchDebounce.md
        SVC_SearchDebounce -->|300ms| API_Search{{GET /api/search}}:::./specs/API_Search.md
        API_Search --> SVC_SearchEngine[[Search Engine]]:::./specs/SVC_SearchEngine.md
        SVC_SearchEngine --> DB_Products[(Products DB)]:::./specs/DB_Products.md
        DB_Products --> UI_SearchResults[/Search Results Dropdown/]:::./specs/UI_SearchResults.md
        UI_SearchResults -->|Select| UI_ProductModal
    end
    
    %% --- Visual Highlighting for Change Impact ---
    style SVC_PaymentGateway fill:#ff9999,stroke:#ff0000,stroke-width:3px
    style API_CreateOrder fill:#ffcccc
    style UI_CheckoutFlow fill:#ffcccc
    style EXT_Stripe fill:#ffcccc
    
    %% --- Classification ---
    classDef critical fill:#ff6b6b,color:#fff
    classDef complex fill:#4ecdc4,color:#fff
    classDef standard fill:#45b7d1,color:#fff
    
    class AUTH_Check,SVC_PaymentGateway,DB_Orders critical
    class STATE_CartManager,SVC_OrderProcessor,SVC_SearchEngine complex
    class UI_ProductCard,UI_SearchBar,API_Search standard
```

The AI uses this visual memory to understand that changing `API_AuthCheck` will affect both the login form above it and the validator below it.

### 3. Blueprints for Every Building Block (Specifications)

Each NodeID has its own detailed blueprint in the `specs/` folder. These contain:
- Purpose and responsibilities
- Dependencies and interfaces
- Core logic and behavior
- Verification criteria
- Technical debt notes

### 4. Lightning-Fast Context Assembly

When you say "Fix the login timeout issue", here's what happens:

1. AI looks at the visual architecture
2. Finds `API_AuthCheck` and sees all connections
3. Reads only the relevant specs
4. Has perfect understanding in seconds

No more loading entire codebases or missing critical connections.

### 5. Mission Control Dashboard (Tracker)

See everything at a glance:

| Status | WorkGroupID | NodeID | Dependencies | Progress |
|:---|:---|:---|:---|:---|
| 🟢 | - | UI_LoginForm | - | VERIFIED |
| 🟡 | feat-20250107-143022 | API_AuthCheck | UI_LoginForm | WIP |
| ⚪️ | - | API_PasswordReset | API_AuthCheck | TODO |

Track what's done, what's in progress, what's blocked, and what's next.

### 6. Perfect Historical Memory (Log)

Every significant action is permanently recorded:
- What was built and when
- Why decisions were made
- What problems were discovered
- What technical debt was created

The AI can answer "Why does this code look weird?" with "According to the log, we had to work around a third-party API limitation on Jan 15."

---

## Core Concepts in 30 Seconds

### 🏷️ **NodeIDs - Permanent Identity**
Every building block gets a unique name (like `API_AuthCheck` or `UI_LoginForm`) that persists across all AI sessions forever. No more "what login are you talking about?"

### 📦 **Change Sets - Complete Updates**
AI identifies ALL NodeIDs affected by a feature and updates them together. No more partial implementations that break other features.

### 🗺️ **Visual Architecture - Spatial Memory**  
NodeIDs live in a Mermaid diagram showing how everything connects. AI sees your system as an architect would - not as random files.

### 📋 **Living Specifications**
Each NodeID has a detailed blueprint (spec) that evolves from plan → built → verified. AI always knows what each NodeID should do.

### 📊 **Real-Time Mission Control**
The tracker dashboard shows exactly what's done, what's in progress, and what's blocked - with WorkGroupIDs that track related changes together.

---

## How is Noderr Different?

| Traditional AI Coding | Noderr |
|----------------------|-------------|
| "Add login feature" → AI writes some login code somewhere | "Add login feature" → AI identifies all affected NodeIDs, shows system impact, builds everything together |
| "Update the auth system" → "What auth system? I don't see one" | "Update API_AuthCheck" → AI knows exactly what you mean, sees all connections |
| Files and functions with no permanent identity | Every building block has a NodeID that persists forever |
| AI reads entire codebase each time (or misses connections) | AI uses visual architecture to instantly find relevant specs |
| Changes break other features → discover during testing | AI sees ripple effects before coding → builds complete Change Sets |
| "I'll add error handling" → Inconsistent patterns | ARC Verification ensures every NodeID meets quality gates before completion |
| Context lost between sessions → repetitive explanations | Perfect memory via log → "Per the Jan 15 entry, we worked around API limitation" |
| Technical debt accumulates invisibly | Every debt logged → REFACTOR_NodeID tasks auto-scheduled |
| Documentation drifts from reality | Specs updated to "as-built" state after every change |
| Each feature built in isolation | Visual architecture ensures system cohesion |

---

## The Noderr Loop

Every feature follows this systematic 4-step process:

**Step 1A: Impact Analysis**
→ Use prompt: `ND__[LOOP_1A]__Propose_Change_Set.md`
```
You: "Add password reset"
AI: "This requires changing:
     - NEW: UI_ResetForm, API_ResetPassword
     - MODIFY: UI_LoginPage (add 'forgot password' link)
     - MODIFY: DB_Users (add reset_token field)"
```

**Step 1B: Draft Specs**
→ Use prompt: `ND__[LOOP_1B]__Draft_Specs.md`
- AI marks NodeIDs as Work-In-Progress (WIP)
- Creates detailed blueprints for every affected NodeID
- You review the specifications

**Step 2: Implement Change Set**
→ Use prompt: `ND__[LOOP_2]__Implement_Change_Set.md`
- AI builds ALL NodeIDs in the Change Set together
- Runs tests and verification
- Ensures quality gates are met

**Step 3: Finalize & Commit**
→ Use prompt: `ND__[LOOP_3]__Finalize_And_Commit.md`
- Updates all specs to match what was built
- Logs decisions and discoveries
- Creates a clean git commit

---

## Installation & Setup

### The Noderr Approach

Unlike traditional tools, Noderr is installed AFTER you build your initial prototype. This ensures it documents what actually exists, not just what was planned.

### Quick Install
1. **Prepare your vision** (blueprint, project overview, architecture)
2. **Build initial prototype** with AI based on those plans
3. **Download & add Noderr** - [Get noderr-starter.zip](https://github.com/kaithoughtarchitect/noderr/releases/latest/download/noderr-starter.zip)
4. **Run Install prompt** - `ND__Install_And_Reconcile.md`
5. **Run System Audit** - `ND__Post_Installation_Audit.md`

See [Getting Started](./docs/getting-started.md) for detailed instructions.

---

## What Gets Created

```
your-project/
├── 📁 noderr/
│   ├── 📄 noderr_project.md      # Your project's vision & standards
│   ├── 🗺️  noderr_architecture.md # Visual system map  
│   ├── 📊 noderr_tracker.md      # Progress dashboard
│   ├── 📝 noderr_log.md          # Development history
│   └── 🔧 noderr_loop.md         # AI's instruction manual
├── 📁 specs/                     # Blueprints for each NodeID
├── 📁 planning/                  # Feature analysis docs
└── 📄 environment_context.md     # Your environment setup
```

---

## Real Example

**Without Noderr:**
```javascript
// Monday: "Add user profile"
function UserProfile() { ... }

// Wednesday: "Add user settings"  
function Settings() { ... }  // New component, doesn't connect

// Friday: "Make profile show settings"
// AI: "I don't see how these relate..."
```

**With Noderr:**
```javascript
// Monday: "Add user profile"
// You: Use prompt "ND__[LOOP_1A]__Propose_Change_Set.md"
// AI: "Creating UI_UserProfile (NodeID), updating UI_Navigation to include 
//      profile link, adding API_GetProfile endpoint. All connected in architecture."

// Wednesday: "Add user settings"
// AI: "I see UI_UserProfile exists. Creating UI_UserSettings as child component,
//      adding to architecture, creating API_UpdateSettings, updating tracker."

// Friday: "Make profile show settings"  
// AI: "I see both in the architecture. They're already connected. 
//      Just need to update UI_UserProfile render method. One-line change."
```

---

## Critical Concepts

### The Environment Context
The AI cannot function without `environment_context.md` being configured. This file teaches the AI:
- What commands to use on YOUR system (npm vs yarn, python vs python3)
- How to run tests in YOUR setup
- Where YOUR database lives
- How to commit code in YOUR environment

### The Prompts System
You don't just chat with the AI. You use specific prompt files to trigger each phase:
```
ND__Start_Work_Session.md         → Begin work
ND__[LOOP_1A]__Propose_Change_Set.md → Start a feature
ND__[LOOP_1B]__Draft_Specs.md    → Review specs
ND__[LOOP_2]__Implement_Change_Set.md → Build it
ND__[LOOP_3]__Finalize_And_Commit.md → Finish up
```

### ARC Verification
**A**ttentive **R**eview & **C**ompliance - Before marking any NodeID as complete, the AI verifies:
- All tests pass
- Code meets security standards
- Performance is acceptable
- Error handling is robust
- Documentation matches reality

---

## License

MIT License - Use freely in your projects

---

## The Bottom Line

Noderr transforms AI from an eager intern who writes random code into a disciplined engineer who understands your system, follows your standards, and builds with purpose.

Welcome to systematic AI development. Welcome to Noderr.

---

*Because great software isn't just coded. It's engineered.*
