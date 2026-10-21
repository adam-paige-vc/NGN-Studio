# NGN Studio

NGN Studio is a desktop application for building, taking, and reviewing NCLEX practice exams. It combines an exam library, a question creator, exam results and progress tracking, and a rotating question bank in one locally stored workspace.

You can use NGN Studio to practice with existing exams, create your own, or build a study session from questions collected across your library. Exams support six question types: multiple choice, select all that apply, ordered response, matrix, drag and drop, and fill in the blank. Each type has its own answer format and scoring behavior, including partial credit for select-all-that-apply and drag-and-drop questions and row-by-row scoring for matrix questions.

## Exam practice

Start an exam from the library, choose whether to shuffle its questions, and work through it with navigation, answer tracking, and an optional timer. You can flag questions, cross out options, and highlight text while answering. Depending on the exam settings, feedback may appear immediately or after submission.

When you finish, NGN Studio presents your results with question-level answers and rationales. You can review a completed exam with your saved answers or retake it. Review sessions are kept separate from new exam results, and a retake updates the exam’s recorded contribution to progress rather than counting every attempt as a new contribution.

## Exam library and creator

The library supports bundled example exams as well as user exams organized in folders. You can import individual exams, folders, and ZIP packages, then browse and manage the resulting collection. Exams can also be exported as JSON or text.

The built-in creator lets you write and edit questions using the same six question types available in the exam player. Save an exam to your library and use it for practice or as a source of questions for the study bank. Saved exams receive unique IDs and are protected against accidental overwriting when another exam has the same ID.

## Question bank and study sessions

The question bank gathers questions from saved exams and explicit imports. It removes duplicates based on question text, while retaining source information for questions contributed by exams. Library synchronization adds missing questions without replacing existing bank entries or removing them when a source exam changes.

Choose a study session by filtering for source exam, tags, or question type. The app shows how many questions match before you begin. Filters select questions for the current session; they do not replace the full bank or its queue. As you complete questions, the bank rotates them and saves the updated study order. If saving fails, the session stays open so you can retry.

## Progress tracking

NGN Studio records results and aggregates progress by question type and tag, along with each exam’s contribution. This gives you a way to see how your practice is distributed across the material in your library. Retaking an exam replaces that exam’s prior contribution instead of accumulating repeated attempts.

## Optional AI exam generation

The AI generation flow can create a draft exam from selected source documents and your configuration. You can set the question count, time limit, question types and distribution, difficulty, order, rationale detail, source scope, and custom instructions. Supported source formats include PDF, DOCX, PPTX, TXT, and Markdown. The app provides extraction previews and format limits; it does not interpret images or perform OCR.

There are two ways to use the generation flow:

- **Manual workflow:** Copy the prepared instructions into an external AI service and attach the source files there.
- **Optional local Codex workflow:** Connect through the supported local Codex app-server using your own account. Only selected extracted text and any explicitly included question inventory are sent after consent.

Generated output is checked for exam structure, question types, IDs, answer formats, and requested question counts before it can be saved. The app may make one structural repair attempt, but passing validation does not guarantee clinical accuracy. AI drafts can be saved automatically after validation, or held for manual review when that preference is enabled.

## Local data and privacy

NGN Studio stores the exam library, question bank, and progress on the device. AI features are optional. When using local Codex generation, source text and any included inventory are sent only after you consent; credentials are managed by Codex through the operating system’s keychain. Selected source files and sending consent are not stored with remembered generation preferences.

NGN Studio is built with Electron, React, and JavaScript. It has no backend service.
