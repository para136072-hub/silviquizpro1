# SilviQuiz Pro Live Classroom — Android Source

## What this project is
A source project intended for Android Studio. The teacher tablet runs a local
HTTP server on port 8787 and opens the teacher controller.

## Classroom design
Teacher tablet -> private router -> student phones.
The tablet can be cast to the Android TV.

## Build
Open this folder in Android Studio.
Allow Gradle to sync.
Select a connected Android tablet or emulator.
Run the app, or use Build > Build APK(s).

The generated APK should be in:
app/build/outputs/apk/debug/

## Important production note
This is a complete development source foundation, but the server-side scoring
validation still needs to be hardened before classroom deployment. The current
student UI calculates its displayed score from the embedded question data, while
the server endpoint is prepared for authoritative scoring.

The 60 Wood Structure & Identification questions are embedded in:
app/src/main/assets/questions.json

No internet service is required for the intended local-network architecture.

## NEW: Reusable Question Bank / Exam Manager (v3 source)

The teacher APK is designed to be reusable for future exams. Questions are no longer permanently tied to the original 60-item Wood Structure & Identification exam.

### Teacher features
- **Question Bank / Exam Manager** at `/manager.html`
- Create multiple Exam Sets
- Edit questions and choices A-D
- Change the correct answer and rationale
- Add/delete questions
- Import a new exam from CSV without recompiling the APK
- Export the selected exam to CSV for backup/editing
- Select which Exam Set will run in the live classroom
- Current Wood Structure & Identification 60-item exam is seeded on first launch

### CSV import format
`Question,A,B,C,D,Correct,Rationale`

Example:
`What is sapwood?,Outer living wood,Inner heartwood,Bark,Cambium,A,Sapwood is the outer active conducting wood.`

### Persistence
Exam sets are stored in the Android app's internal storage as `examsets.json`. Future exams therefore do not require rebuilding the APK. The original seeded exam remains available unless the teacher edits or deletes it.

### Live scoring hardening
The current source now validates the correct answer on the Android local server and prevents duplicate scoring for the same student/question. The selected Exam Set determines the active question count.

### Important
This remains an **Android Studio source project**, not a compiled/verified APK. Build it in Android Studio with the Android SDK/Gradle environment.
