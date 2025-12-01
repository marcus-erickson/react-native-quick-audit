Quick Project Health Check (QUICK_AUDIT)
Step 1: Architecture Detection
Quickly scan the codebase and identify the architecture:
Look for these indicators:

Backend folder (server/, api/, backend/) + database calls → UI_BACKEND_DB
Supabase/Firebase/Clerk imports but no backend folder → UI_REMOTE_DB_NO_BACKEND
No backend folder, no remote database imports → STANDALONE_UI
Multiple app folders or workspaces → MONOREPO_OR_MULTI_APP
Mixed or unclear patterns → UNKNOWN_OR_MIXED

Step 2: Essential Project Setup Checks
Universal Project Hygiene (All Apps):

Version Control - Missing .git folder, no repository initialization
Project Documentation - No README.md, missing setup instructions
Environment Configuration - No .env.example, hardcoded config values
Git Configuration - Missing .gitignore, sensitive files at risk
Dead Code - Unused dependencies, template leftovers, console logs
Bundle Optimization - Large unused libraries bloating app size

Architecture-Specific Red Flags:
UI_REMOTE_DB_NO_BACKEND:

Database credentials visible in source code

UI_BACKEND_DB:

Missing backend documentation or setup instructions

Step 3: Output Format
Project Health Report Card
⚡ PROJECT HEALTH CHECK
=======================
Architecture: [DETECTED_ARCHITECTURE]
Issues Found: [X]/[X] checks
🔴 Critical: [X]
🟠 High: [X]  
🟡 Medium: [X]

Project Health Score: [A/B/C/D/F][+/-]
Quick Fix Time: ~[X] minutes
Top Issues Found
For each issue, include:
[SEVERITY] [Issue Title]

Problem: [1 sentence explanation]
AI Fix Prompt: "[Copy-pasteable prompt for AI coding tools]"
Time: ~[X] minutes

Ready for More?
✅ This quick check found [X] issues in 30 seconds.
Want the complete professional audit? Run the full suite for:

🔒 Security Audit - 20+ vulnerability checks (API keys, validation, file uploads, etc.)
📊 Code Quality Review - Component organization and maintainability analysis
⚡ Performance Analysis - Bundle size, loading speed, and mobile optimization
📱 Mobile Layout Check - Device compatibility and touch interface review
🚀 Deployment Readiness - Production config and app store preparation

Total: 100+ professional-grade checks to make your app production-ready

Instructions for AI:

Detect architecture first
Run 6-8 basic project hygiene checks - focus on fundamental gaps almost all projects have
Always find 4-7 issues - version control, documentation, environment setup, dead code
Write actionable AI fix prompts:

Be specific about files to create/modify
Reference project patterns they're already using
Keep prompts under 2 sentences


Keep fixes achievable - 2-10 minute tasks, not hours of work
Hook them for the full suite - mention specific audit capabilities
Use encouraging tone - focus on quick wins and professional setup

AI Fix Prompt Guidelines:

Start with action: "Create...", "Remove...", "Add...", "Update..."
Be specific about what to implement
Reference their existing code patterns when possible
Focus on immediate, visible improvements
