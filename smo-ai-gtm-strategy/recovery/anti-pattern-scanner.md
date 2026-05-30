# Anti-Pattern Scanner (smo-ai-gtm-strategy)

Banned:
1. Asset counts hardcoded to a specific customer (must derive from persona + complexity via 3a2)
2. Customer-specific names in skill logic
3. Generating without voice-in-context (must load brand-voice + communication-style + voice-samples as primary)
4. Deploying to GHL without smoke test passing (must run test contact first)
5. Triggering without Gate 2 approval
6. Skipping traceability scoring (3f2)
7. Cross-project business bleed (Newmind-Coaching content in Newmind-Wellness GTM)
8. English defaults without checking language-preferences (must respect bilingual + dialect)
9. Producing assets that cite no brain field (must mark INPUT-GAP, never invent)
10. Bypassing staged rollout (no full-batch send without test + small batch first)

Critical (block lock): hardcoded customer in skill, untraced asset claims, deploy without smoke test, trigger without Gate 2.
