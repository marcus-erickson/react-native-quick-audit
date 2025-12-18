# React Native Quick Audit

A free, AI-powered health check that scans your React Native app in **30 seconds** and finds 4-7 critical issues—complete with copy-paste AI fix prompts.

## What Makes This Different

Most audit tools give you a wall of text. This one:

✅ **Detects your architecture** (standalone UI, backend + DB, remote services, etc.)  
✅ **Finds real issues** in your specific project setup  
✅ **Gives you AI fix prompts** - just copy, paste into Claude/Cursor, and fix it  
✅ **Provides a health score** (A through F) so you know where you stand  
✅ **Takes 30 seconds** to run, 2-10 minutes per fix

## What It Checks

**Universal Project Hygiene:**
- Version Control setup
- Project Documentation (README, setup instructions)
- Environment Configuration (.env.example, hardcoded values)
- Git Configuration (.gitignore, sensitive files)
- Dead Code (unused dependencies, console logs)
- Bundle Optimization (large unused libraries)

**Plus Architecture-Specific Checks:**
The audit automatically detects your app type and runs targeted checks for issues like exposed database credentials, missing backend docs, and more.

## Sample Output
```
⚡ PROJECT HEALTH CHECK
=======================
Architecture: UI_REMOTE_DB_NO_BACKEND
Issues Found: 5/8 checks
🔴 Critical: 1
🟠 High: 2  
🟡 Medium: 2

Project Health Score: C+
Quick Fix Time: ~18 minutes

🔴 Database Credentials Exposed
Problem: Supabase anon key hardcoded in source
AI Fix Prompt: "Move all Supabase keys to .env file and create .env.example with placeholder values"
Time: ~5 minutes
```

## How to Use

1. Copy the prompt from [`quick-audit-prompt.md`](./quick-audit-prompt.md)
2. Paste it into Claude, Cursor, or your favorite AI coding assistant
3. Let it scan your React Native project (takes ~30 seconds)
4. Get your health score + actionable fix prompts
5. Copy each fix prompt into your AI tool and implement

**Total time:** 30 seconds to scan + 2-10 minutes per fix

## Why This Works

Instead of generic advice, you get **specific AI prompts** tailored to your project:
- "Create a .env.example with [your actual config keys]"
- "Remove console.log statements from [your specific files]"
- "Add .gitignore rules for [your actual sensitive files]"

Just copy, paste, fix. No thinking required.

## Ready for Production?

✅ This quick check finds **fundamental setup issues** in 30 seconds.

For a comprehensive pre-launch audit:

**[React Project Checkup Toolkit - Deep Audit](https://marcus-erickson.github.io)** ($49)
- 🔒 **Security Audit** - 20+ vulnerability checks (API keys, validation, file uploads)
- 📊 **Code Quality Review** - Component organization and maintainability
- ⚡ **Performance Analysis** - Bundle size, loading speed, mobile optimization
- 📱 **Mobile Layout Check** - Device compatibility and touch interfaces
- 🚀 **Deployment Readiness** - Production config and app store requirements
- and more....

**100+ professional checks** to make your app production-ready.

## Stay Updated

Want to know when new React Native tools and guides launch?

👉 [Join the mailing list](https://thundergodsoftware.substack.com/subscribe)

## About

Built by [Marcus Erickson](https://github.com/marcus-erickson),Experienced developer and AI coder. I have shipped multiple React Native apps and built these tools from real-world pain points.

Check out our blog for articles on vibe coding with a focus on getting apps shipped with quality at (https://thundergodsoftware.substack.com/)

Part of [Thunder God Software](https://marcus-erickson.github.io) - developer tools that bridge the gap from AI prototype to production-ready app.

## License

MIT - use it however you want!
