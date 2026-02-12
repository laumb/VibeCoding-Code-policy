# GLOBAL CODE POLICY
Version: 1.0.0
Scope: Applies to ALL generated code, projects and modifications.

------------------------------------------------------------------
1. VERSIONING (MANDATORY)
------------------------------------------------------------------

We follow Semantic Versioning: vX.Y.Z

X = Major
- Breaking changes
- Dramatic functionality change
- Major UX/UI redesign
- Architectural changes
- Database schema changes
- Config format changes

Y = Minor
- New modules
- New features (non-breaking)
- Significant internal improvements
- New integrations

Z = Patch
- Bug fixes
- Minor adjustments
- Small non-breaking improvements
- Documentation updates

Rules:
- Every release MUST update version number.
- Every release MUST update changelog in README.md.
- Git tags MUST follow format: vX.Y.Z
- Pre-releases allowed: -alpha, -beta, -rc.X
- No release without updated README + passing tests.

------------------------------------------------------------------
2. REQUIRED PROJECT STRUCTURE
------------------------------------------------------------------

Every project MUST include:

- README.md (required)
- Changelog (inside README.md)
- Clear setup instructions
- Standard run commands:
  - install
  - dev
  - build
  - test
  - lint
  - format
  - start (production)

- .env.example (if environment variables are used)
- No secrets stored in repository
- Dependencies must be locked (lockfile required)
- Reproducible builds required

Optional but recommended:
- Dockerfile
- docker-compose.yml
- docs/ folder for extended documentation
- ADR (Architecture Decision Records) for major decisions

------------------------------------------------------------------
3. README REQUIREMENTS (MANDATORY)
------------------------------------------------------------------

README.md MUST contain:

- Project description
- Architecture overview
- Setup instructions
- Environment variable documentation
- Run instructions (dev + prod)
- Version number
- Full changelog
- Security considerations (if applicable)

README must be sufficient for a human or machine to continue development.

------------------------------------------------------------------
4. INTERNATIONALIZATION (MANDATORY)
------------------------------------------------------------------

All products MUST support:
- Norwegian (nb)
- English (en)

Rules:
- No hardcoded UI text.
- All user-facing strings must use i18n system.
- Both languages MUST have identical translation keys.
- Date/time/number formatting must respect locale.
- New features MUST update both languages immediately.

------------------------------------------------------------------
5. DARK MODE (MANDATORY)
------------------------------------------------------------------

- Must support Light + Dark mode.
- Default = system preference.
- User must be able to override.
- Theme must use structured design tokens or variables.
- No scattered conditional styling.

------------------------------------------------------------------
6. WEB APPLICATION REQUIREMENTS
------------------------------------------------------------------

If building web apps:

- Must run standalone on a web server.
- Must NOT depend on Codex runtime.
- Must include production start command.
- Must support health endpoint (/healthz recommended).
- Must implement structured logging.
- Must fail safely.

------------------------------------------------------------------
7. SECURITY (HIGH PRIORITY)
------------------------------------------------------------------

Security is mandatory and non-negotiable.

Rules:
- Never hardcode secrets.
- Never log passwords or tokens.
- Validate all inputs.
- Escape all outputs.
- Use secure authentication libraries.
- No custom cryptography.
- Follow OWASP best practices.
- Use secure defaults.
- Document security impact of any security-related change.
- Apply least privilege principle.

Security fixes MUST NOT be bypassed for convenience.

------------------------------------------------------------------
8. CODE QUALITY
------------------------------------------------------------------

All projects MUST include:

- Linting
- Formatting
- Automated tests (minimum: unit tests for core logic)
- Type safety where applicable
- Passing CI before release

Code rules:
- Comment WHY, not obvious WHAT.
- Public functions must include documentation comments.
- Avoid technical debt shortcuts.
- Maintain clean architecture separation.

------------------------------------------------------------------
9. OBSERVABILITY
------------------------------------------------------------------

- Structured logging preferred (JSON).
- Log levels must be used correctly.
- No sensitive data in logs.
- Proper error handling required.
- Clear user-facing error messages.
- Internal error details only in logs.

------------------------------------------------------------------
10. PERFORMANCE & ACCESSIBILITY
------------------------------------------------------------------

Web projects must:
- Avoid unnecessary heavy dependencies.
- Use lazy loading when appropriate.
- Be responsive (mobile + desktop).
- Follow accessibility basics (labels, contrast, keyboard support).

------------------------------------------------------------------
11. DEFINITION OF DONE
------------------------------------------------------------------

A project is NOT complete unless:

[ ] Version number updated
[ ] Changelog updated
[ ] README updated
[ ] Norwegian + English updated
[ ] Dark mode works (system default + toggle)
[ ] Tests pass
[ ] Lint passes
[ ] No secrets in repo
[ ] Standalone production start works
[ ] Security rules respected

------------------------------------------------------------------
12. LANGUAGE & STACK SELECTION
------------------------------------------------------------------

The AI may choose programming language freely,
but must select one that:

- Follows best practices for the project type
- Is secure
- Is performant
- Is maintainable
- Has strong ecosystem support

No unsafe hacks.
No fragile shortcuts.
Long-term maintainability over short-term speed.


------------------------------------------------------------------
STRICT MODE – MANDATORY COMPLIANCE BLOCK
------------------------------------------------------------------

At the end of EVERY completed task, the AI MUST output a
"COMPLIANCE SUMMARY" section in the following format:

--------------------------------------------------
COMPLIANCE SUMMARY
--------------------------------------------------

Version Updated: YES / NO
Changelog Updated: YES / NO
README Updated: YES / NO

i18n (nb/en) Updated: YES / NO / NOT APPLICABLE
Dark Mode Verified: YES / NO / NOT APPLICABLE

Tests Added/Updated: YES / NO / NOT APPLICABLE
Tests Passing: YES / NO / NOT APPLICABLE
Lint Passing: YES / NO / NOT APPLICABLE

Standalone Production Start Verified: YES / NO / NOT APPLICABLE

Security Review Performed: YES / NO
Secrets Hardcoded: NO (MUST always be NO)
Sensitive Data Logged: NO (MUST always be NO)

Breaking Changes Introduced: YES / NO
If YES → Major version bumped: YES / NO

Definition of Done Status: COMPLETE / INCOMPLETE

--------------------------------------------------

Rules:

1. The AI MUST NOT mark "COMPLETE" unless all mandatory fields are compliant.
2. If any field is NO, the AI must explain why.
3. If security-related changes were made, a short
   "SECURITY IMPACT NOTE" must be included.
4. If breaking changes were introduced without version bump,
   the task is automatically INVALID.
5. No silent omissions allowed.

------------------------------------------------------------------
STRICT MODE ENFORCED
------------------------------------------------------------------

END OF POLICY
