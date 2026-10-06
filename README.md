# Practical 3 - Version Control System

Student ID: 20243007027

This project uses the [provided Android application](https://github.com/jibrilmuhammadadam/Practical3_GitHub). The original Commit 001 and its history are preserved. The main development branch is `master`.

## Changes

| Commit | Branch | Change |
| --- | --- | --- |
| 001 | master | Original login interface |
| 002 | master | Center the Welcome Back title |
| 003 | master | Add Cancel beside Log In |
| 004 | feature-button-background-color | Set both buttons to black with white text |

The buttons use equal LinearLayout weights and an 8dp gap. The existing login behavior is unchanged. Cancel is the additional button view required by the practical.

## Run

Open the project root in Android Studio, wait for Gradle sync, then run `app` on an emulator. The project uses the supplied Gradle and Android SDK configuration.

To build from a terminal:

```text
gradlew.bat :app:assembleDebug
```

Each UI change was built and run on a Medium Phone AVD with Android API 35, a 1080 x 2400 display and 420 dpi. The title position, button alignment and visibility were checked. The two button backgrounds in Commit 004 were also checked as RGB 0, 0, 0.

The original Log In action was checked with the supplied sample account and with empty input. It displayed the expected success and invalid-credentials messages. See the [successful login](docs/screenshots/login-success.png) and [invalid input](docs/screenshots/login-invalid.png) screenshots.

## Screenshots

| Stage | Screenshot |
| --- | --- |
| Original application | [Commit 001](docs/screenshots/commit-001.png) |
| Centered title | [Commit 002](docs/screenshots/commit-002.png) |
| Cancel added | [Commit 003](docs/screenshots/commit-003.png) |
| Black buttons | [Commit 004](docs/screenshots/commit-004.png) |

## Git workflow

The provided repository was cloned using HTTPS. An empty public repository was created, `origin` was changed to this repository, and the original branches and tags were pushed. The color change is developed on `feature-button-background-color`.

To merge the feature into the main development branch:

```text
git switch master
git pull origin master
git merge --no-ff feature-button-background-color
git push origin master
```

Keep the feature branch so both development branches can be inspected. View the history with `git log --graph --oneline --all`, check changes with `git status`, list branches with `git branch`, and check the repository URL with `git remote -v`.

## Android Studio and terminal commands

| Operation | Android Studio | Terminal |
| --- | --- | --- |
| Clone | Get from VCS / Clone Repository | `git clone <URL>` |
| Commit | Git > Commit | `git add .` then `git commit` |
| Push | Git > Push | `git push` |
| Pull | Git > Pull | `git pull` |
| Create branch | Branch widget > New Branch | `git switch -c <branch>` |
| Switch branch | Branch widget > Checkout | `git switch <branch>` |
| Merge | Branch widget > Merge into Current | `git merge <branch>` |
| View history | Git > Show History / Log | `git log` |

## Reflection

In a large project, commits make it possible to trace a change and find the version that introduced a problem. Branches let developers work on separate features, while merging brings those changes together. A remote repository shares the history with the team. Reviewing and testing changes before merging helps keep the main branch working, and earlier commits provide a way to recover from mistakes.
