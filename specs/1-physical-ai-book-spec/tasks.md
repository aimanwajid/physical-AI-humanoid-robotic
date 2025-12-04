---
description: "Task list template for feature implementation"
---

# Tasks: Physical AI Book

**Input**: Design documents from `/specs/1-physical-ai-book-spec/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Tests**: No specific test tasks are generated as tests were not explicitly requested in the feature specification for each task.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Single project**: `src/`, `tests/` at repository root
- **Web app**: `backend/src/`, `frontend/src/`
- **Mobile**: `api/src/`, `ios/src/` or `android/src/`
- Paths shown below assume single project - adjust based on plan.md structure

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Project initialization and basic Docusaurus structure

- [x] T001 Initialize Docusaurus project in `physical-ai-book/`
- [x] T002 Configure `docusaurus.config.js` for project metadata and plugins in `physical-ai-book/docusaurus.config.js`
- [x] T003 Configure `sidebars.js` for initial navigation structure in `physical-ai-book/sidebars.js`
- [x] T004 Clean up default Docusaurus pages and content in `physical-ai-book/docs/`

---

## Phase 2: User Story 1 - Explore Book Content (Priority: P1) 🎯 MVP

**Goal**: Enable readers to easily navigate through the book's chapters and lessons.

**Independent Test**: A user can access the book's main page, browse the table of contents, and successfully open and read any chapter or lesson page.

### Implementation for User Story 1

- [x] T005 [P] [US1] Create `intro.md` for the book's introduction in `physical-ai-book/docs/intro.md`
- [x] T006 [US1] Create `chapter-1/` directory for the first chapter in `physical-ai-book/docs/chapter-1/`
- [x] T007 [US1] Create `_category_.json` for Chapter 1 metadata in `physical-ai-book/docs/chapter-1/_category_.json`
- [x] T008 [P] [US1] Create `lesson-1.md` for the first lesson in `physical-ai-book/docs/chapter-1/lesson-1.md`
- [x] T009 [P] [US1] Create `lesson-2.md` for the second lesson in `physical-ai-book/docs/chapter-1/lesson-2.md`
- [x] T010 [P] [US1] Create `lesson-3.md` for the third lesson in `physical-ai-book/docs/chapter-1/lesson-3.md`
- [x] T011 [US1] Add placeholder content to `intro.md` in `physical-ai-book/docs/intro.md`
- [x] T012 [P] [US1] Add placeholder content to `lesson-1.md` in `physical-ai-book/docs/chapter-1/lesson-1.md`
- [x] T013 [P] [US1] Add placeholder content to `lesson-2.md` in `physical-ai-book/docs/chapter-1/lesson-2.md`
- [x] T014 [P] [US1] Add placeholder content to `lesson-3.md` in `physical-ai-book/docs/chapter-1/lesson-3.md`

**Checkpoint**: At this point, User Story 1 should be fully functional and testable independently

---

## Phase 3: User Story 2 - Engage with Hands-on Lessons (Priority: P1)

**Goal**: Enable learners to interact with code examples and complete exercises within each lesson.

**Independent Test**: A user can open a lesson with a code example, copy the code, execute it, and verify the expected output.

### Implementation for User Story 2

- [x] T015 [US2] Define content guidelines for code blocks and exercises in `specs/1-physical-ai-book-spec/spec.md`
- [x] T016 [US2] Add example runnable code blocks to `physical-ai-book/docs/chapter-1/lesson-1.md`
- [x] T017 [US2] Add example hands-on exercises to `physical-ai-book/docs/chapter-1/lesson-2.md`
- [x] T018 [US2] Ensure all code examples are runnable and accurate in `physical-ai-book/docs/chapter-1/`

**Checkpoint**: At this point, User Stories 1 AND 2 should both work independently

---

## Phase 4: Polish & Cross-Cutting Concerns

**Purpose**: Improvements that affect multiple user stories

- [x] T019 Run Docusaurus build process and fix any errors in `physical-ai-book/`
- [x] T020 Review all book content for consistent tone and brand voice in `physical-ai-book/docs/`
- [x] T021 Implement/configure link checking for external resources in `physical-ai-book/docusaurus.config.js`
- [x] T022 Validate accessibility and performance using Lighthouse in `physical-ai-book/`

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - can start immediately
- **User Stories (Phase 2+)**: All depend on Setup phase completion.
  - User stories can then proceed in parallel (if staffed)
  - Or sequentially in priority order (P1 → P2)
- **Polish (Final Phase)**: Depends on all desired user stories being complete

### User Story Dependencies

- **User Story 1 (P1)**: Can start after Setup (Phase 1) - No dependencies on other stories
- **User Story 2 (P1)**: Can start after Setup (Phase 1) - May integrate with US1 (e.g., modifying already created lesson files) but should be independently testable for its core goal.

### Within Each User Story

- Models before services (if applicable, not explicitly here)
- Services before endpoints (if applicable, not explicitly here)
- Core implementation before integration
- Story complete before moving to next priority

### Parallel Opportunities

- All Setup tasks T001-T004 can generally be done sequentially, but some configuration tasks could be considered in parallel if they don't block each other. For this specific Docusaurus setup, sequential is safer.
- Tasks T005, T008, T009, T010, T012, T013, T014 within User Story 1 are marked [P] as they involve creating/populating distinct files.
- Tasks T016, T017, T018 within User Story 2, while modifying existing lesson files, can be approached in parallel if working on different aspects of the content (e.g., one person adds code blocks to lesson-1, another adds exercises to lesson-2, as long as content is managed carefully).
- Different user stories (US1, US2) could be worked on in parallel by different team members once the initial Docusaurus setup is complete.

---

## Parallel Example: User Story 1

```bash
# Launch all parallel content creation for User Story 1 together:
Task: "Create intro.md for the book's introduction in `physical-ai-book/docs/intro.md`"
Task: "Create lesson-1.md for the first lesson in `physical-ai-book/docs/chapter-1/lesson-1.md`"
Task: "Create lesson-2.md for the second lesson in `physical-ai-book/docs/chapter-1/lesson-2.md`"
Task: "Create lesson-3.md for the third lesson in `physical-ai-book/docs/chapter-1/lesson-3.md`"
Task: "Add placeholder content to lesson-1.md in `physical-ai-book/docs/chapter-1/lesson-1.md`"
Task: "Add placeholder content to lesson-2.md in `physical-ai-book/docs/chapter-1/lesson-2.md`"
Task: "Add placeholder content to lesson-3.md in `physical-ai-book/docs/chapter-1/lesson-3.md`"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup
2. Complete Phase 2: User Story 1
3. **STOP and VALIDATE**: Test User Story 1 independently (navigation, content display)
4. Deploy/demo if ready

### Incremental Delivery

1. Complete Setup → Foundation ready
2. Add User Story 1 → Test independently → Deploy/Demo (MVP!)
3. Add User Story 2 → Test independently → Deploy/Demo
4. Each story adds value without breaking previous stories

### Parallel Team Strategy

With multiple developers:

1. Team completes Setup together
2. Once Setup is done:
   - Developer A: User Story 1 (focus on structure and basic content)
   - Developer B: User Story 2 (focus on hands-on elements, potentially modifying content created by A)
3. Stories complete and integrate independently

---

## Notes

- [P] tasks = different files, no dependencies (or can be managed with care on shared files)
- [Story] label maps task to specific user story for traceability
- Each user story should be independently completable and testable
- Commit after each task or logical group
- Stop at any checkpoint to validate story independently
- Avoid: vague tasks, same file conflicts, cross-story dependencies that break independence
