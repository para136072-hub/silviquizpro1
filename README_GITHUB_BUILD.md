# SilviQuiz Pro — GitHub Online APK Build

This repository includes a GitHub Actions workflow that builds a debug APK online.

## Build from GitHub
1. Create a GitHub repository.
2. Upload the contents of this folder to the repository (not the outer ZIP folder).
3. Open **Actions**.
4. Select **Build SilviQuiz Pro APK**.
5. Click **Run workflow**.
6. Wait for the build to finish.
7. Open the successful workflow run.
8. Under **Artifacts**, download **SilviQuizPro-debug-APK**.

GitHub stores workflow output as an artifact that can be downloaded from the run summary.

## Important
- This produces a **debug APK**, suitable for installation/testing.
- It is not a Play Store release build.
- The source contains the Wood Structure & Identification 60-item seed exam and the reusable Exam Manager.
