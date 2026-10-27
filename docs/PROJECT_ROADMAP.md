# Web & App Development Roadmap

This roadmap separates currently available work from ideas that still need implementation. It is intentionally honest about project status.

## 1. Portfolio website

**Status:** Initial static version in this repository.

**Goal:** Present web, app, and AI-integration capabilities in a clear, mobile-friendly portfolio.

**Acceptance checklist**
- [x] Responsive page layout
- [x] Accessible skip link and keyboard-friendly navigation
- [x] Reduced-motion preference support
- [x] SEO title and description
- [x] Clear project status labels
- [ ] Cross-browser and real-device testing
- [ ] Add screenshots from real working projects
- [ ] Publish with GitHub Pages and add the live URL

## 2. AI website assistant

**Status:** Concept only.

**Goal:** Help website visitors find service information and identify an appropriate next step.

**First version**
- Define approved source material and questions the assistant can answer.
- Design a chat interface with loading, error, and empty states.
- Connect to an AI API through a server-side endpoint; never expose API secrets in browser code.
- Add a visible handoff path for questions the assistant cannot answer.
- Test inaccurate answers, prompt injection, and privacy-sensitive questions.

**Definition of done**
- A working demo uses an explicitly configured backend.
- Responses are grounded in approved content.
- Errors and limitations are visible to the user.
- No API key or private data is committed to the repository.

## 3. Real estate workspace

**Status:** Planned product concept.

**Goal:** Organize property enquiries and follow-up work in a simple interface.

**Potential first version**
- Property and enquiry list using synthetic demo data.
- Search and filters for status and property type.
- Enquiry details and follow-up status.
- Form validation and clear empty/error states.
- Optional database integration after the data model and access rules are defined.

**Privacy rule:** Public examples must use fictional listings and contact details. Do not upload client WhatsApp messages, owner/dealer phone numbers, or private property records.

## 4. Mobile business companion

**Status:** Planned product concept.

**Goal:** Make a small set of business tasks easier to access on a phone.

**Before implementation**
- Identify target users and the top three tasks.
- Sketch navigation and key screens.
- Decide whether a responsive web app or native/cross-platform app is appropriate.
- Define authentication, data storage, and API requirements.
- Test a clickable prototype before committing to a framework.

## Suggested delivery sequence

1. Test and publish the portfolio.
2. Build a small interactive web app with synthetic data.
3. Add a working AI assistant with a secure server-side integration.
4. Use feedback to choose the mobile app concept and implementation path.

## Release checklist

- [ ] Project status matches what actually works.
- [ ] No credentials or private customer data are present.
- [ ] Layout works at mobile, tablet, and desktop widths.
- [ ] Links, buttons, forms, and keyboard navigation are tested.
- [ ] README includes setup and demo instructions.
- [ ] Screenshots are from the real build, not misleading mockups.
