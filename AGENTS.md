## Code Review Rules

- Check changes to claims about local storage, backup or sharing, AdMob, deletion and contact details against available evidence for the app. Flag contradictions and unsupported changes to what the app says it collects or shares.
- Preserve a readable, accessible static policy page and its public entry point. Review changes that make policy text, navigation or contact depend on JavaScript or external availability.
- Check new external destinations, embeds and scripts for unexpected tracking or exposure of user data. Verify HTTPS policy links and the support email destination.

Report actionable regressions introduced by the pull request. Anchor each finding to the relevant changed line and describe the triggering condition, concrete impact, and severity. Read affected callers and platform boundaries when needed to establish impact. Keep findings focused on behavior, compatibility, privacy, and security.
