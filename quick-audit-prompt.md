Quick Architecture Audit (QUICK_ARCHITECTURE_AUDIT)

Step 1: Platform Detection
Scan for these indicators to determine mobile platform:

REACT_NATIVE_EXPO:
- Has `app.json` or `app.config.js` with expo config
- Dependencies include `expo`, `react-native` 
- Imports from 'react-native' or 'expo-*' packages

CAPACITOR_WEB:
- Has `capacitor.config.ts` or `capacitor.config.json`
- Dependencies include `@capacitor/core`, `@capacitor/cli`
- Vite/webpack config present
- React web code (divs, Tailwind classes, etc.)

WEB_ONLY:
- React + Vite/webpack but no Capacitor config
- No app.json, no mobile platform folders

UNKNOWN:
- Mixed indicators or unclear structure

Step 2: Architecture Detection
Identify data architecture:

Backend folder (server/, api/, backend/) + database calls → UI_BACKEND_DB
Supabase/Firebase/Clerk imports but no backend folder → UI_REMOTE_DB_NO_BACKEND
No backend folder, no remote database imports → STANDALONE_UI
Multiple app folders or workspaces → MONOREPO_OR_MULTI_APP

Step 3: Essential Architecture Checks

Universal Checks (All Platforms):
1. Version Control - Missing .git folder, no repository initialization
2. Project Documentation - No README.md, missing setup instructions, missing getting started guide
3. AI Assistant Configuration 
   - Check for ANY of these files: `.cursorrules`, `claude.md`, `CLAUDE.md`, `.clinerules`, `.clauderc`
   - ❌ FAIL if NONE of these files exist
   - ✅ PASS if ANY of these files exist
   - Problem: No project-specific prompts or coding guidelines for AI assistants
   - Risk: Inconsistent code style and architecture as you iterate with AI tools
4. Environment Configuration - No .env.example, hardcoded config values, missing environment documentation
5. Git Configuration - Missing .gitignore, sensitive files at risk, build artifacts in repo
6. Dead Code - Unused dependencies, template leftovers, commented code blocks, console.logs in production code
7. Bundle Optimization - Large unused libraries bloating app size, unoptimized images
8. Security Issues - API keys in source code, hardcoded credentials, exposed secrets

Platform-Specific Checks:

REACT_NATIVE_EXPO:
- Missing TypeScript configuration or JavaScript without type safety
- No error boundary components for crash handling
- Missing SafeAreaView or safe area handling
- Platform-specific code without Platform.OS checks
- Images not optimized for mobile (large file sizes)
- No FlatList for scrollable lists (using ScrollView with map instead)
- Navigation not properly configured
- Async storage used without error handling

CAPACITOR_WEB:
- Missing or incomplete `capacitor.config.ts`
- Web app not optimized for mobile viewport (no viewport meta tag)
- Touch targets smaller than 44x44px
- No responsive design breakpoints
- Missing mobile-first CSS approach
- Web fonts not optimized for mobile loading

WEB_ONLY:
- No mobile platform consideration (mention this is web-only)
- Missing responsive design patterns
- No accessibility considerations (a11y)

Architecture-Specific Red Flags:
- UI_REMOTE_DB_NO_BACKEND: Database credentials visible in source code, client-side security rules missing
- UI_BACKEND_DB: Missing backend documentation, no API error handling, backend not containerized
- STANDALONE_UI: No data persistence strategy, localStorage used without fallbacks

Step 4: Output Format

⚡ ARCHITECTURE HEALTH CHECK
============================
Platform: [DETECTED_PLATFORM]
Architecture: [DETECTED_ARCHITECTURE]
Issues Found: [X]/[X] checks
🔴 Critical: [X]
🟠 High: [X]  
🟡 Medium: [X]

Architecture Health Score: [A/B/C/D/F][+/-]
Quick Fix Time: ~[X] minutes

Top Issues Found
[For each issue:]

[SEVERITY] [Issue Title]
Problem: [1 sentence explanation]
AI Fix Prompt: "[Platform-appropriate prompt]"
Time: ~[X] minutes

Platform-Specific AI Fix Prompt Guidelines:

REACT_NATIVE_EXPO:
- Reference Expo SDK and React Native APIs
- Use expo-* packages where appropriate
- Mention proper mobile patterns (SafeAreaView, FlatList, etc.)
- Include error handling and loading states

CAPACITOR_WEB:
- Reference Capacitor plugins for native features
- Keep web code patterns (React + Tailwind)
- Mention responsive mobile design
- Include viewport and touch optimization

Ready for More?
✅ This quick check found [X] architecture issues in 30 seconds.

Want to check if you're ready to publish?
🚀 Run APP_STORE_READINESS_AUDIT to see what you need before submitting to app stores

Instructions for AI:
1. Detect platform first (Step 1)
2. Detect architecture (Step 2)
3. Run universal checks + platform-specific checks
4. Tailor AI fix prompts to the detected platform
5. Report actual issues found - if a check passes, mark it as ✅ passing
6. If all checks pass, celebrate it! Show Architecture Health Score: A+ and "No issues found"
7. The audit should be completeable - don't invent problems that don't exist
