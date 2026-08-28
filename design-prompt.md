# PART 1: LifeBridge is an AI-powered patient assistance case manager that coordinates financial, administrative, medical-support, and community assistance throughout a patient's journey—identifying relevant support sources, preparing and submitting applications, tracking their progress, following up, and continuously finding additional assistance when the patient's needs change.

---

# PART 2: INFORMATION ARCHITECTURE

---

## 2.1 Screen Inventory

### Splash & Entry

| # | Screen | Purpose |
|---|--------|---------|
| SP1 | Splash Screen | Brand logo, app name, session restore check, auto-redirect based on auth state |
| SP2 | Session Restoring Loader | Checking stored tokens, refreshing auth, loading user profile |

### Onboarding

| # | Screen | Purpose |
|---|--------|---------|
| OB1 | Onboarding — Slide 1 | What LifeBridge does — value proposition |
| OB2 | Onboarding — Slide 2 | One case, multiple support sources — how it works |
| OB3 | Onboarding — Slide 3 | AI assistance, privacy, no guarantees — trust & transparency |
| OB4 | Onboarding — Get Started | CTA to choose user type |

### User Type Selection

| # | Screen | Purpose |
|---|--------|---------|
| UT1 | User Type Selection | Choose: "I need help" (Patient/Guardian) or "We provide help" (Organization) |
| UT2 | User Type — Patient Info | Brief explanation of patient/guardian experience |
| UT3 | User Type — Organization Info | Brief explanation of organization portal experience |

### Patient / Guardian — Login

| # | Screen | Purpose |
|---|--------|---------|
| PL1 | Patient Login — Main | Email/phone input, "Continue" button, links to methods below |
| PL2 | Patient Login — Email + Password | Email field, password field, show/hide toggle, "Forgot password?" link |
| PL3 | Patient Login — Phone + OTP | Phone number input with country code, "Send OTP" button |
| PL4 | Patient Login — OTP Entry | 6-digit OTP input, resend timer, change number link |
| PL5 | Patient Login — Social: Google | "Continue with Google" — OAuth flow |
| PL6 | Patient Login — Social: Apple | "Continue with Apple" — Apple Sign In flow |
| PL7 | Patient Login — Social: Facebook | "Continue with Facebook" — Facebook OAuth flow |
| PL8 | Patient Login — Biometric | "Use fingerprint / face" prompt, fallback to password |
| PL9 | Patient Login — Success | Auth success, profile loaded, prompt: "Enable biometric login?" (first login only), redirect to Home |
| PL10 | Patient Login — Error: Wrong Password | Inline error, "Try again" / "Forgot password?" |
| PL11 | Patient Login — Error: Account Not Found | "No account found" with "Create account" link |
| PL12 | Patient Login — Error: Account Locked | "Account temporarily locked" with retry timer |
| PL13 | Patient Login — Error: Too Many Attempts | Rate limit notice, wait time display |

### Patient / Guardian — Registration

| # | Screen | Purpose |
|---|--------|---------|
| PR1 | Patient Register — Main | "Create your account" — choose registration method |
| PR2 | Patient Register — Email + Password | Full name, email, password, confirm password, strength indicator |
| PR3 | Patient Register — Phone + OTP | Full name, phone with country code, OTP verification |
| PR4 | Patient Register — Social: Google | OAuth — pre-fill name/email from Google profile |
| PR5 | Patient Register — Social: Apple | Apple Sign In — pre-fill from Apple ID |
| PR6 | Patient Register — Social: Facebook | Facebook OAuth — pre-fill from Facebook profile |
| PR7 | Patient Register — OTP Verification | 6-digit code sent to phone/email, verify before proceeding |
| PR8 | Patient Register — Profile Setup | Date of birth, gender, relationship to patient (self/guardian), location |
| PR9 | Patient Register — Guardian Details | If "guardian": patient name, relationship, patient DOB, patient location |
| PR10 | Patient Register — Terms & Consent | Terms of service, privacy policy, AI consent, data processing agreement |
| PR11 | Patient Register — Success | Welcome message, "Create your first case" CTA |
| PR12 | Patient Register — Error: Email Taken | "Email already registered" with "Login instead" link |
| PR13 | Patient Register — Error: Phone Taken | "Phone already registered" with "Login instead" link |

### Patient / Guardian — Forgot Password

| # | Screen | Purpose |
|---|--------|---------|
| PF1 | Forgot Password — Entry | Enter email or phone to receive reset link/code |
| PF2 | Forgot Password — OTP Verification | 6-digit code sent to email/phone |
| PF3 | Forgot Password — New Password | New password, confirm password, strength indicator |
| PF4 | Forgot Password — Success | "Password updated" with "Login" CTA |
| PF5 | Forgot Password — Error: Account Not Found | "No account with this email/phone" |
| PF6 | Forgot Password — Error: Expired Code | "Code expired" with "Resend" button |

### Organization — Login

| # | Screen | Purpose |
|---|--------|---------|
| OL1 | Organization Login — Main | Email/organization code input, "Continue" button |
| OL2 | Organization Login — Email + Password | Organization email, password, show/hide toggle, "Forgot password?" |
| OL3 | Organization Login — Organization Code | 8-12 digit org code field, "Verify Code" button |
| OL4 | Organization Login — Code Verified | Shows org name/logo for confirmation, "Continue as [name]" |
| OL5 | Organization Login — SSO | "Continue with SSO" — enterprise single sign-on redirect |
| OL6 | Organization Login — SSO Provider Select | List of SSO providers (Okta, Azure AD, Google Workspace) |
| OL7 | Organization Login — SSO Redirect | Loading/redirecting to SSO provider page |
| OL8 | Organization Login — SSO Callback | Processing SSO response, mapping to org account |
| OL9 | Organization Login — Invite Link | Direct link from email — auto-creates/accesses org account |
| OL10 | Organization Login — OTP Entry | 6-digit OTP to verify your identity (sent to your phone/email after org code verified) |
| OL11 | Organization Login — Success | Auth success, org profile loaded, redirect to Org Home |
| OL12 | Organization Login — Error: Invalid Code | "Organization code not recognized" |
| OL13 | Organization Login — Error: Org Not Verified | "Organization pending verification" with status info |
| OL14 | Organization Login — Error: Wrong Password | Inline error, "Try again" / "Forgot password?" |
| OL15 | Organization Login — Error: Account Locked | "Account temporarily locked" with retry timer |

### Organization — Registration

| # | Screen | Purpose |
|---|--------|---------|
| OR1 | Organization Register — Main | "Register your organization" |
| OR2 | Organization Register — Organization Details | Organization name, type (NGO/hospital/government/other), registration number, country |
| OR3 | Organization Register — Contact Person | Admin name, email, phone, role/title |
| OR4 | Organization Register — Email + Password | Organization email, password, confirm password |
| OR5 | Organization Register — Phone OTP | Verify phone number with OTP |
| OR6 | Organization Register — Document Upload | Registration certificate, tax ID, authorization letter |
| OR7 | Organization Register — Mission & Scope | Organization mission, service areas, target beneficiaries |
| OR8 | Organization Register — Terms & Consent | Organization terms, data processing, compliance agreement |
| OR9 | Organization Register — Submission Confirmation | "Application submitted for review" — pending verification status |
| OR10 | Organization Register — Pending Verification | Status tracker: submitted → under review → approved/rejected |
| OR11 | Organization Register — Approved | "Your organization is verified" with "Login" CTA |
| OR12 | Organization Register — Rejected | "Verification rejected" with reason and "Reapply" option |
| OR13 | Organization Register — Error: Email Taken | "Email already registered" with "Login instead" |
| OR14 | Organization Register — Error: Org Already Exists | "Organization already registered" with admin contact info |

### Organization — Forgot Password

| # | Screen | Purpose |
|---|--------|---------|
| OF1 | Forgot Password — Entry | Enter organization email |
| OF2 | Forgot Password — OTP Verification | 6-digit code sent to email |
| OF3 | Forgot Password — New Password | New password, confirm password |
| OF4 | Forgot Password — Success | "Password updated" with "Login" CTA |

### Admin — Login

| # | Screen | Purpose |
|---|--------|---------|
| AL1 | Admin Login — Main | Email/password input, admin-specific branding |
| AL2 | Admin Login — Email + Password | Admin email, password, show/hide toggle |
| AL3 | Admin Login — 2FA Verification | 6-digit TOTP code (Google Authenticator / Authy) |
| AL4 | Admin Login — 2FA Setup | QR code scan + manual entry key for first-time 2FA setup |
| AL5 | Admin Login — Backup Codes | View/download one-time backup codes |
| AL6 | Admin Login — Success | Admin session started, redirect to Admin Dashboard |
| AL7 | Admin Login — Error: Invalid Credentials | "Invalid email or password" |
| AL8 | Admin Login — Error: 2FA Failed | "Invalid verification code" with retry |
| AL9 | Admin Login — Error: Account Disabled | "Admin account disabled" with support contact |
| AL10 | Admin Login — Error: Too Many Attempts | Rate limit with wait time |

### Admin — Password Reset

| # | Screen | Purpose |
|---|--------|---------|
| AF1 | Admin Reset — Entry | Enter admin email |
| AF2 | Admin Reset — OTP Verification | 6-digit code via email |
| AF3 | Admin Reset — 2FA Confirmation | TOTP code required before password change |
| AF4 | Admin Reset — New Password | New password, confirm password |
| AF5 | Admin Reset — Success | "Password updated, all sessions revoked" with "Login" CTA |

### Shared Authentication Screens

| # | Screen | Purpose |
|---|--------|---------|
| SA1 | OTP Input — Generic | 6-digit code input, auto-detect, resend timer |
| SA2 | OTP Sent Confirmation | "Code sent to [masked phone/email]" |
| SA3 | Biometric Prompt | System biometric dialog (fingerprint/face) |
| SA4 | Session Expired | "Your session expired" with "Login again" CTA |
| SA5 | Session Timeout Warning | "Session expires in X minutes" with "Extend" button |
| SA6 | Auto-Login Success | Silent token refresh, no user action needed |
| SA7 | Auth Loading State | "Verifying..." spinner |
| SA8 | Device Trust | "Trust this device?" with Yes/No |
| SA9 | Logged Out Confirmation | "You have been logged out" |
| SA10 | Multi-Device Alert | "Login detected on another device" with details |

### Home

| # | Screen | Purpose |
|---|--------|---------|
| H1 | Home Dashboard (Patient) | Command center — case state, gap, next action |
| H2 | Home — Empty State | No active case, prompt to create |
| H3 | Home — Multiple Cases | Select between active cases |

### Case Creation

| # | Screen | Purpose |
|---|--------|---------|
| C1 | Create Case — Start | Choose case type (medical, etc.) |
| C2 | Step 1: Patient Details | Name, age, gender, location, guardian |
| C3 | Step 2: Medical/Treatment | Diagnosis, hospital, treatment, urgency |
| C4 | Step 3: Financial | Costs, income, insurance, available funds |
| C5 | Step 4: Documents | Upload required documents |
| C6 | Step 5: Review | Review all information, consent |
| C7 | Case Created — Confirmation | Success state, next steps |

### Case Management

| # | Screen | Purpose |
|---|--------|---------|
| CM1 | Cases List | All patient cases |
| CM2 | Case Detail | Full case view with tabs |
| CM3 | Case Detail — Overview Tab | Summary, funding gap, status |
| CM4 | Case Detail — Applications Tab | All applications for this case |
| CM5 | Case Detail — Documents Tab | All documents for this case |
| CM6 | Case Detail — Timeline Tab | Case event history |
| CM7 | Case Detail — Support Tab | Matched support sources for this case |
| CM8 | Edit Case | Modify case information |
| CM9 | Case Status Indicator | Color-coded status bar |
| CM10 | Funding Gap Widget | Visual gap tracker |

### Documents

| # | Screen | Purpose |
|---|--------|---------|
| D1 | Document List | All documents for a case |
| D2 | Document Upload | Camera / file selection |
| D3 | Document Preview | View uploaded document |
| D4 | Document Detail | Metadata, extracted info, status |
| D5 | Document Category Selector | Assign document type |
| D6 | Document Missing List | What documents are still needed |
| D7 | AI Extraction Result | Extracted values for user review |
| D8 | Document Rejection / Review Needed | Low-confidence extraction flagged |

### Support Discovery

| # | Screen | Purpose |
|---|--------|---------|
| S1 | Support Sources List | All discovered support sources for selected case |
| S2 | Support Match Card | Individual source with match score |
| S3 | Support Detail | Full source information |
| S4 | Eligibility Check | Potential eligibility explanation |
| S5 | Required Documents List | What this source requires |
| S6 | Match Score Breakdown | Why this source matched |
| S7 | Source Verification Badge | Verified / pending / unverified |

### Applications

| # | Screen | Purpose |
|---|--------|---------|
| AP1 | Applications List | All applications across all cases |
| AP2 | Application Detail | Full application view |
| AP3 | Application Timeline | Status progression |
| AP4 | Application Card | Summary card in list |
| AP5 | Create Application — Start | Select support source |
| AP6 | Create Application — Draft Review | AI-prepared application |
| AP7 | Create Application — Document Checklist | Missing vs. provided docs |
| AP8 | Create Application — Consent & Submit | Authorization before submission |
| AP9 | Application Submitted Confirmation | Success state |
| AP10 | Application Status Change | Status update notification view |
| AP11 | Rejection Detail | Why rejected, what next |
| AP12 | Rejection Recovery Options | Correct / reapply / alternatives |
| AP13 | Documents Required | Organization-requested documents |
| AP14 | Application Action Sheet | Contextual actions per application |

### Follow-Up

| # | Screen | Purpose |
|---|--------|---------|
| F1 | Follow-Up List | All pending follow-ups across all cases |
| F2 | Follow-Up Detail | Single follow-up info |
| F3 | Follow-Up Preparation | Draft follow-up for review |
| F4 | Follow-Up Confirmation | Confirm send |
| F5 | Follow-Up History | Completed follow-ups |
| F6 | Overdue Follow-Up Alert | Highlighted overdue items |

### AI Assistant

| # | Screen | Purpose |
|---|--------|---------|
| AI1 | Chat Interface | Main conversation screen |
| AI2 | Suggested Actions | Quick-action chips above input |
| AI3 | AI Response Card | Structured response with actions |
| AI4 | AI Processing State | "Thinking..." indicator |
| AI5 | AI Confidence Indicator | High / needs review / insufficient |
| AI6 | AI Action Confirmation | User approves AI-suggested action |
| AI7 | AI Escalation Prompt | Transfer to human |
| AI8 | Case Context Header | Current case summary in chat |
| AI9 | Quick Question Prompts | Pre-built question starters |
| AI10 | Conversation History | Past conversations list |

### "I Need More Help"

| # | Screen | Purpose |
|---|--------|---------|
| MH1 | Help Request Entry | What changed / what's needed |
| MH2 | Change Type Selector | Cost increase / rejection / delay / new need |
| MH3 | Change Detail Form | Details of the change |
| MH4 | Reassessment Result | Updated gap, new options |
| MH5 | New Support Options | Additional sources found |
| MH6 | Help Request Confirmation | Change recorded, reassessment triggered |

### Notifications

| # | Screen | Purpose |
|---|--------|---------|
| N1 | Notifications List | All notifications |
| N2 | Notification Detail | Full notification content |
| N3 | Notification Preferences | Configure notification settings |
| N4 | Notification Badge | Count indicator on bell icon |

### Profile & Settings

| # | Screen | Purpose |
|---|--------|---------|
| P1 | Profile — Patient/Guardian | Personal information |
| P2 | Profile — Edit | Modify profile |
| P3 | Profile — Documents | Identity, insurance docs |
| P4 | Settings — Main | Settings overview |
| P5 | Settings — Language | Language selection |
| P6 | Settings — Notifications | Opens Notification Preferences (N3) |
| P7 | Settings — Privacy & Consent | Data sharing, consent management |
| P8 | Settings — Security | Password, 2FA, biometric toggle |
| P9 | Settings — Connected Organizations | Authorized organizations |
| P10 | Settings — About | App info, version |
| P11 | Settings — Help & Education | Explanations, FAQ |
| P12 | Settings — Data Export/Deletion | GDPR/data rights |
| P13 | Settings — Active Sessions | View/revoke active login sessions |
| P14 | Settings — Login History | Recent login attempts with device/location |
| P15 | Settings — Change Password | Current password, new password, confirm |
| P16 | Settings — Enable/Disable Biometric | Toggle biometric login |
| P17 | Settings — 2FA Management | Enable/disable/change 2FA method |

### Emergency

| # | Screen | Purpose |
|---|--------|---------|
| E1 | Emergency Hub | Categories of urgent help |
| E2 | Emergency — Hospital Assistance | Urgent hospital financial aid |
| E3 | Emergency — Blood Support | Blood donation finding |
| E4 | Emergency — Emergency Financial | Immediate financial assistance |
| E5 | Emergency — Contact Help | Emergency contacts |
| E6 | Emergency — Disclaimer | "Use emergency medical services" notice |
| E7 | Emergency Confirmation | Action initiated / contact made |

### Admin Dashboard

| # | Screen | Purpose |
|---|--------|---------|
| AD1 | Admin Home | Key metrics overview |
| AD2 | Admin — Cases List | All cases with filters |
| AD3 | Admin — Case Detail | Patient case (admin view) |
| AD4 | Admin — Applications Queue | Applications needing review |
| AD5 | Admin — Support Sources Management | CRUD for support sources |
| AD6 | Admin — Organizations List | All organizations |
| AD7 | Admin — Organization Verification | Verify/reject organizations |
| AD8 | Admin — Users Management | User accounts |
| AD9 | Admin — Escalations Queue | AI escalations needing humans |
| AD10 | Admin — Fraud Reports | Suspicious activity queue |
| AD11 | Admin — Analytics | Charts, metrics, reports |
| AD12 | Admin — Audit Log | System audit history |
| AD13 | Admin — AI Configuration | AI policies, confidence thresholds |
| AD14 | Admin — Search | Global admin search |
| AD15 | Admin — Auth Settings | Login policies, session limits, 2FA requirements |

### Organization Portal

| # | Screen | Purpose |
|---|--------|---------|
| ORG1 | Organization Home | Assigned cases, pending actions |
| ORG2 | Organization — Case List | Cases assigned to org |
| ORG3 | Organization — Case Review | Review patient case |
| ORG4 | Organization — Application Review | Review application |
| ORG5 | Organization — Request Documents | Request specific docs from patient |
| ORG6 | Organization — Update Status | Change application status |
| ORG7 | Organization — Approve/Reject | Decision with reason |
| ORG8 | Organization — Communication | Message patient |
| ORG9 | Organization — Profile | Organization profile |
| ORG10 | Organization — Verification Status | Verification info |
| ORG11 | Organization — Team Members | Manage org users/roles |
| ORG12 | Organization — Invite Member | Send invite to new team member |

### Search

| # | Screen | Purpose |
|---|--------|---------|
| SR1 | Search — Patient | Search assistance sources |
| SR2 | Search — Results | Filtered results |
| SR3 | Search — Filters | Filter panel |

### Help & Education

| # | Screen | Purpose |
|---|--------|---------|
| HE1 | Help Home | Topics overview |
| HE2 | Help Topic Detail | Explanation of a concept |
| HE3 | About LifeBridge | What the app does |
| HE4 | What is a Funding Gap | Educational |
| HE5 | What is a Support Source | Educational |
| HE6 | What AI Can and Cannot Do | Educational |

### Shared / Cross-Cutting

| # | Screen | Purpose |
|---|--------|---------|
| SH1 | Empty State — Generic | No data to display |
| SH2 | Error State — Generic | Something went wrong |
| SH3 | Loading State — Generic | Content loading |
| SH4 | Offline State | No network connection |
| SH5 | Success Confirmation — Generic | Action completed |
| SH6 | Confirmation Dialog — Destructive | Confirm delete, withdraw |
| SH7 | Permission Request | Camera, notification access |
| SH8 | Image Viewer | Full-screen document preview |
| SH9 | PDF Viewer | Full-screen PDF view |
| SH10 | Map View | Location-based support sources |

---

## 2.2 Navigation Architecture

### Patient / Guardian Navigation

```
Bottom Navigation Bar (5 items):
├── Home          → H1
├── Cases         → CM1
├── Applications  → AP1
├── Follow-Ups    → F1
└── Profile       → P1

Floating Action:
├── FAB: "Ask LifeBridge" → AI1 (accessible from any screen)

Top Bar Actions (contextual):
├── Bell icon → N1 (notifications) → N2 (detail) → N3 (preferences)
├── Search icon → SR1 → SR2 → SR3
└── More menu → Emergency (E1-E7), Settings (P4-P12), Help (HE1-HE6)
```

### Admin Navigation

```
Side Navigation (desktop/tablet) or Bottom Nav (mobile):
├── Dashboard       → AD1
├── Cases           → AD2
├── Applications    → AD4
├── Organizations   → AD6
├── Support Sources → AD5
├── Escalations     → AD9
├── Fraud Reports   → AD10
├── Analytics       → AD11
├── Audit Log       → AD12
├── Users           → AD8
├── Search          → AD14
└── Settings        → AD13
```

### Organization Portal Navigation

```
Bottom Navigation (mobile) or Side Nav (desktop):
├── Home          → ORG1
├── Cases         → ORG2
├── Applications  → ORG4
├── Messages      → ORG8
└── Profile       → ORG9
```

---

## 2.3 Screen Hierarchy Map

### Pre-Auth Flow (all users)

```
App Launch
  └─→ Splash Screen (SP1)
       ├─→ [Session exists] → Session Restoring (SP2)
       │    ├─→ [Token valid] → Role-based redirect
       │    │    ├─→ Patient → Home Dashboard (H1)
       │    │    ├─→ Organization → Org Home (ORG1)
       │    │    └─→ Admin → Admin Home (AD1)
       │    └─→ [Token expired] → Check stored role → Role-based login
       │         ├─→ Patient → Patient Login (PL1)
       │         ├─→ Organization → Organization Login (OL1)
       │         └─→ Admin → Admin Login (AL1)
       │
       └─→ [No session] → Onboarding
            ├─→ Slide 1 (OB1)
            ├─→ Slide 2 (OB2)
            ├─→ Slide 3 (OB3)
            └─→ Get Started (OB4) → User Type Selection (UT1)
                 │
                 ├─→ [I need help] → Patient Info (UT2) → Patient Auth Flow
                 │
                 └─→ [We provide help] → Organization Info (UT3) → Organization Auth Flow
```

### Patient / Guardian — Login Flow

```
User Type Selection (UT1) → Patient Login (PL1)
  │
  ├─→ Email + Password (PL2)
  │    ├─→ [Success] → Success (PL9) → Home Dashboard (H1)
  │    ├─→ [Wrong Password] → Error (PL10) → retry or Forgot Password
  │    ├─→ [Account Not Found] → Error (PL11) → Register (PR1)
  │    ├─→ [Account Locked] → Error (PL12) → wait timer
  │    └─→ [Too Many Attempts] → Error (PL13) → rate limit
  │
  ├─→ Phone + OTP (PL3) → OTP Entry (PL4)
  │    ├─→ [OTP Valid] → Success (PL9) → Home Dashboard (H1)
  │    ├─→ [OTP Expired] → Resend (PL3)
  │    └─→ [OTP Invalid] → Retry (PL4)
  │
  ├─→ Google (PL5) → OAuth → [New User] → Register Flow
  │                         → [Existing] → Success (PL9) → Home Dashboard (H1)
  │
  ├─→ Apple (PL6) → Apple Sign In → [New User] → Register Flow
  │                                  → [Existing] → Success (PL9) → Home Dashboard (H1)
  │
  ├─→ Facebook (PL7) → OAuth → [New User] → Register Flow
  │                           → [Existing] → Success (PL9) → Home Dashboard (H1)
  │
  └─→ Biometric (PL8) → System Prompt (SA3)
       ├─→ [Success] → Success (PL9) → Home Dashboard (H1)
       └─→ [Fail] → Fallback to Email + Password (PL2)

Forgot Password (from PL2):
  PL2 → Forgot Password (PF1)
    → OTP Verification (PF2)
    → New Password (PF3)
    → Success (PF4) → Login (PL1)
```

### Patient / Guardian — Registration Flow

```
Register (PR1) or Social OAuth new user
  │
  ├─→ Email + Password (PR2)
  │    → OTP Verification (PR7) → Profile Setup (PR8)
  │
  ├─→ Phone + OTP (PR3) → OTP Verification (PR7) → Profile Setup (PR8)
  │
  ├─→ Google (PR4) → OAuth → OTP Verification (PR7) → Profile Setup (PR8)
  │
  ├─→ Apple (PR5) → Apple Sign In → Profile Setup (PR8)
  │    (Apple provides verified identity — OTP step skipped)
  │
  └─→ Facebook (PR6) → OAuth → OTP Verification (PR7) → Profile Setup (PR8)

Profile Setup (PR8):
  ├─→ [Self patient] → Terms & Consent (PR10) → Success (PR11) → Home (H1)
  └─→ [Guardian] → Guardian Details (PR9) → Terms & Consent (PR10) → Success (PR11) → Home (H1)

Errors:
  ├─→ Email Taken (PR12) → Login (PL1)
  └─→ Phone Taken (PR13) → Login (PL1)
```

### Organization — Login Flow

```
User Type Selection (UT1) → Organization Login (OL1)
  │
  ├─→ Email + Password (OL2)
  │    ├─→ [Success] → Success (OL11) → Org Home (ORG1)
  │    ├─→ [Wrong Password] → Error (OL14) → retry or Forgot Password
  │    ├─→ [Org Not Verified] → Error (OL13) → Pending Status (OR10)
  │    ├─→ [Account Locked] → Error (OL15) → wait timer
  │    └─→ [Too Many Attempts] → Rate limit
  │
  ├─→ Organization Code (OL3) → Code Verified (OL4)
  │    └─→ [Confirm org] → OTP Entry (OL10) → Success (OL11) → Org Home (ORG1)
  │
  ├─→ SSO (OL5) → Provider Select (OL6) → Redirect (OL7) → Callback (OL8)
  │    ├─→ [Success + mapped] → Success (OL11) → Org Home (ORG1)
  │    └─→ [Success + new] → Org Details (OR2) → Contact Person (OR3) → Document Upload (OR6) → Mission & Scope (OR7) → Terms & Consent (OR8) → Submission Confirmation (OR9)
  │
  └─→ Invite Link (OL9) → [Valid invite] → OTP Entry (OL10) → Success (OL11) → Org Home (ORG1)

Forgot Password (from OL2):
  OL2 → Forgot Password (OF1) → OTP Verification (OF2) → New Password (OF3) → Success (OF4) → Login (OL1)
```

### Organization — Registration Flow

```
Register (OR1) or SSO new user completion
  │
  └─→ Organization Details (OR2)
       → Contact Person (OR3)
       → Email + Password (OR4) → Phone OTP (OR5)
       → Document Upload (OR6)
       → Mission & Scope (OR7)
       → Terms & Consent (OR8)
       → Submission Confirmation (OR9)

Pending Verification (OR10):
  ├─→ [Approved] → Success (OR11) → Login (OL1)
  └─→ [Rejected] → Rejected (OR12) → Reapply (OR1)

Errors:
  ├─→ Email Taken (OR13) → Login (OL1)
  └─→ Org Already Exists (OR14) → Contact admin
```

### Admin — Login Flow

```
Admin Login (AL1)
  │
  └─→ Email + Password (AL2)
       ├─→ [Success + 2FA enabled] → 2FA Verification (AL3)
       │    ├─→ [2FA Valid] → Success (AL6) → Admin Home (AD1)
       │    ├─→ [2FA Invalid] → Error (AL8) → retry
       │    └─→ [Backup Code] → AL5 → Success (AL6) → Admin Home (AD1)
       │
       ├─→ [Success + 2FA not set] → 2FA Setup (AL4) → QR scan → Verify code → AL3 → Success (AL6) → Admin Home (AD1)
       │
       ├─→ [Invalid Credentials] → Error (AL7) → retry
       ├─→ [Account Disabled] → Error (AL9) → support contact
       └─→ [Too Many Attempts] → Error (AL10) → rate limit

Admin Password Reset:
  AF1 → OTP Verification (AF2) → 2FA Confirmation (AF3) → New Password (AF4) → Success (AF5) → Login (AL1)
```

### Patient / Guardian — Main App Flow (post-auth)

```
Home Dashboard (H1)
  │
  ├─→ [No active case] → Home Empty State (H2) → Create Case (C1)
  │
  ├─→ [Multiple cases] → Home Multiple Cases (H3) → select → Case Detail (CM2)
  │
  ├─→ Create Case Flow (C1-C7)
  │    └─→ Case Detail (CM2)
  │         ├── Overview Tab (CM3) → Funding Gap Widget (CM10)
  │         ├── Documents Tab (CM5) → Document List (D1)
  │         │    ├─→ Document Upload (D2) → Document Preview (D3)
  │         │    │    └─→ Document Category Selector (D5)
  │         │    ├─→ Document Detail (D4) → AI Extraction Result (D7)
  │         │    └─→ Document Missing List (D6) → Document Rejection (D8)
  │         ├── Applications Tab (CM4) → Applications List (AP1)
  │         │    └─→ Application Detail (AP2)
  │         │         ├─→ Application Timeline (AP3)
  │         │         ├─→ Rejection Detail (AP11) → Rejection Recovery (AP12)
  │         │         ├─→ Documents Required (AP13)
  │         │         └─→ Application Action Sheet (AP14)
  │         ├── Support Tab (CM7) → Support Sources List (filtered)
  │         │    └─→ Support Match Card (S2) → Support Detail (S3)
  │         │         ├─→ Source Verification Badge (S7)
  │         │         ├─→ Eligibility Check (S4)
  │         │         ├─→ Required Documents (S5)
  │         │         └─→ Match Score Breakdown (S6)
  │         ├── Timeline Tab (CM6)
  │         ├── Edit Case (CM8)
  │         └─→ "I Need More Help" button (Overview Tab) → MH1
  │              → Change Type Selector (MH2) → Change Detail Form (MH3)
  │              → Reassessment Result (MH4) → New Support Options (MH5)
  │              → Help Request Confirmation (MH6)
  │
  ├─→ Cases List (CM1) → Case Detail (CM2) [same subtree]
  │
  ├─→ Applications List (AP1) → Application Detail (AP2) [same subtree]
  │
  ├─→ Follow-Ups
  │    ├─→ Follow-Up List (F1) → Follow-Up Detail (F2)
  │    │    ├─→ Follow-Up Preparation (F3) → Follow-Up Confirmation (F4)
  │    │    └─→ Follow-Up History (F5)
  │    └─→ Overdue Follow-Up Alert (F6) → Follow-Up Detail (F2)
  │
  ├─→ Notifications
  │    ├─→ Notifications List (N1) → Notification Detail (N2)
  │    └─→ Notification Preferences (N3) [also via Settings]
  │
  ├─→ Profile (P1) → Profile Edit (P2) / Profile Documents (P3)
  │
  ├─→ Settings
  │    └─→ Settings Main (P4)
  │         ├─→ Language (P5)
  │         ├─→ Notifications (P6) / Notification Preferences (N3)
  │         ├─→ Privacy & Consent (P7)
  │         ├─→ Security (P8)
  │         │    ├─→ Change Password (P15)
  │         │    ├─→ Enable/Disable Biometric (P16)
  │         │    ├─→ 2FA Management (P17)
  │         │    ├─→ Active Sessions (P13)
  │         │    └─→ Login History (P14)
  │         ├─→ Connected Organizations (P9)
  │         ├─→ About (P10)
  │         ├─→ Help & Education (P11) → Help Home (HE1)
  │         │    └─→ Help Topic Detail (HE2)
  │         │         ├─→ About LifeBridge (HE3)
  │         │         ├─→ What is a Funding Gap (HE4)
  │         │         ├─→ What is a Support Source (HE5)
  │         │         └─→ What AI Can and Cannot Do (HE6)
  │         └─→ Data Export/Deletion (P12)
  │
  ├─→ More menu → Emergency Hub (E1) [also accessible from top bar]
  │    ├─→ Hospital Assistance (E2) → Emergency Confirmation (E7)
  │    ├─→ Blood Support (E3) → Emergency Confirmation (E7)
  │    ├─→ Emergency Financial (E4) → Emergency Confirmation (E7)
  │    ├─→ Contact Help (E5) → Emergency Confirmation (E7)
  │    └─→ Disclaimer (E6)
  │
  ├─→ Search (SR1) → Search Results (SR2) → Filters (SR3)
  │
  └─→ AI Chat (FAB from any screen)
       ├─→ Chat Interface (AI1)
       │    ├─→ Suggested Actions (AI2)
       │    ├─→ AI Response Card (AI3) → AI Action Confirmation (AI6)
       │    └─→ Case Context Header (AI8)
       ├─→ AI Processing State (AI4)
       ├─→ AI Confidence Indicator (AI5)
       ├─→ AI Escalation Prompt (AI7)
       ├─→ Quick Question Prompts (AI9)
       └─→ Conversation History (AI10)
```

### Organization — Main App Flow (post-auth)

```
Organization Home (ORG1)
  ├─→ Case List (ORG2) → Case Review (ORG3)
  ├─→ Applications List → Application Review (ORG4)
  │    ├─→ Request Documents (ORG5)
  │    ├─→ Update Status (ORG6)
  │    └─→ Approve/Reject (ORG7)
  ├─→ Messages (ORG8) → Communication Thread
  ├─→ Profile (ORG9) → Verification Status (ORG10)
  ├─→ Team Members (ORG11) → Invite Member (ORG12)
  └─→ [Notifications via bell icon]
```

### Admin — Main App Flow (post-auth)

```
Admin Home (AD1)
  ├─→ Cases List (AD2) → Case Detail (AD3)
  ├─→ Applications Queue (AD4) → Application Review
  ├─→ Organizations List (AD6) → Organization Verification (AD7)
  ├─→ Support Sources Management (AD5)
  ├─→ Escalations Queue (AD9) → Escalation Detail
  ├─→ Fraud Reports (AD10) → Fraud Detail
  ├─→ Analytics (AD11)
  ├─→ Audit Log (AD12)
  ├─→ Users Management (AD8)
  ├─→ AI Configuration (AD13)
  ├─→ Auth Settings (AD15)
  └─→ Search (AD14) → Search Results
```

### Shared States (appear on any screen)

```
Any Screen
  ├─→ Empty State (SH1)
  ├─→ Error State (SH2)
  ├─→ Loading State (SH3)
  ├─→ Offline State (SH4)
  ├─→ Success Confirmation (SH5)
  ├─→ Confirmation Dialog — Destructive (SH6)
  ├─→ Permission Request (SH7)
  ├─→ Session Expired (SA4) → Login (role-based)
  ├─→ Image Viewer (SH8)
  ├─→ PDF Viewer (SH9)
  └─→ Map View (SH10)
```

---

## 2.4 Auth Method Summary

### Patient / Guardian Login Methods

| Method | Entry Screen | Verification | Landing |
|--------|-------------|-------------|---------|
| Email + Password | PL2 | Session token | H1 |
| Phone + OTP | PL3 → PL4 | 6-digit OTP | H1 |
| Google OAuth | PL5 | OAuth redirect | H1 (new → PR flow) |
| Apple Sign In | PL6 | Apple Auth (verified identity — OTP skipped) | H1 (new → PR flow) |
| Facebook OAuth | PL7 | OAuth redirect | H1 (new → PR flow) |
| Biometric | PL8 | System biometric | H1 |

### Organization Login Methods

| Method | Entry Screen | Verification | Landing |
|--------|-------------|-------------|---------|
| Email + Password | OL2 | Session token | ORG1 |
| Organization Code | OL3 → OL4 | Code + OTP | ORG1 |
| SSO (Okta/Azure/Google) | OL5 → OL6 → OL7 → OL8 | SSO callback | ORG1 |
| Invite Link | OL9 | Invite token + OTP | ORG1 |

### Admin Login Methods

| Method | Entry Screen | Verification | Landing |
|--------|-------------|-------------|---------|
| Email + Password + 2FA | AL2 → AL3 | TOTP code | AD1 |
| Backup Code | AL2 → AL3 → AL5 | One-time code | AD1 |

### Registration Flows

| User Type | Methods Available | Verification Steps | Approval Required |
|-----------|------------------|-------------------|-------------------|
| Patient/Guardian | Email, Phone, Google, Apple, Facebook | OTP (except Apple), Terms & Consent | No — instant access |
| Organization | Email + Org Details + Documents | Phone OTP, Document upload, Terms | Yes — admin verification |
| Admin | Admin invite only | Email, Password, 2FA setup | Yes — super admin invite |
