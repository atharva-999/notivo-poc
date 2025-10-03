Title: Import Android-SDK2.0 project

Summary:
This PR brings the contents of the legacy Android-SDK2.0 project into this repository. Histories were unrelated so the import was merged into a dedicated branch (`merged/import-android-sdk`) for review. The merge includes a combined README and a `.gitignore` update to prevent future addition of IDE/build artifacts.

Checklist before merging:
- [ ] Review `README.md` (merged) and update project description or links if needed.
- [ ] Verify license and third-party binary usage (see `LICENSE`).
- [ ] Inspect and remove any IDE-specific files (e.g. `.idea/` entries) still present in the tree if undesired.
- [ ] Identify large binaries or firmware files that should not remain in repo history. If needed, request a history rewrite (I can do this on `import/android-sdk2.0` before final merge).
- [ ] Consider using Git LFS for large binaries that must remain in the repository.
- [ ] Run a local Gradle build to smoke-test the Android projects if you want a quick verification.

Known large files/binaries to review:
- `NeoSmartpen_SDK_Android_V2110.pdf`
- `NASDK2.0_sample_code/NASDK_sample_code/src/main/assets/firmware_files/*` (zip/firmware)
- `NASDK2.0_Studio/app/src/main/jniLibs/*/*.so`
- `NASDK2.0_Studio/app/src/main/libs/ndac.jar`, `usbserial.jar`
- `NASDK2.0_sample_code/NASDK_sample_code/libs/NASDK-release_2.27.aar`
- Gradle wrapper jars in `gradle/wrapper/` (these are small but benign)

Suggested merge strategy (safe):
1. Review this branch on GitHub: https://github.com/atharva-999/notivo-poc/pull/new/merged/import-android-sdk
2. Make any small cleanup commits on this branch (e.g. remove IDE files, tweak README).
3. Merge via GitHub (non-destructive merge) once reviewed.

If you want me to remove large files from history before merging, say "rewrite history" and I will run a targeted rewrite on the import branch and push the cleaned branch for review.

