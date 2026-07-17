# My Protocol

My personal workflow for this course. **All my changes live in a `my-work/` folder inside each phase** — never edit the course's own files (keeps `git merge upstream/main` conflict-free).

```
phases/00-setup-and-tooling/my-work/
phases/01-math-foundations/my-work/
phases/03-deep-learning-core/my-work/
...
```

## Remotes (already set up)

| Remote | Repo | Use |
|--------|------|-----|
| `origin` | my fork (`Dhanush-K-Gowda`) | push my progress |
| `upstream` | course (`rohitg00`), push disabled | pull course updates |

## Per-phase workflow

**1. Start a phase** — branch off updated `main`:

```bash
git checkout main
git fetch upstream && git merge upstream/main   # get latest course
git checkout -b my-progress-phase0              # phase0, phase1, ...
```

**2. Work** — make a `my-work/` folder inside that phase and put everything there:

```bash
mkdir -p phases/00-setup-and-tooling/my-work
# ...code, notes, solutions go here...
```

**3. Save progress** — commit + push to my fork often:

```bash
git add phases/*/my-work
git commit -m "phase0: <what I did>"
git push -u origin my-progress-phase0      # first push of the branch
git push                                    # later pushes
```

## Get course updates anytime

```bash
git fetch upstream
git checkout main
git merge upstream/main
git push            # keep my fork's main current (optional)
```

Pull those updates into my current phase branch if I want them while working:

```bash
git checkout my-progress-phase0
git merge main
```

## Rules

- ✅ Edit only inside a `my-work/` folder within the phase.
- ✅ One branch per phase: `my-progress-phaseN`.
- ✅ `push` = my fork. `fetch upstream` = course updates.
- 🚫 Never `git push upstream` (disabled anyway).
- 🚫 Never edit the course's own lesson files — only add my own under `my-work/`.
