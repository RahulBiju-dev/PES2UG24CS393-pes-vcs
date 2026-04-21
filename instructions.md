# Phase 2 Instructions

Follow these steps on your Ubuntu 22.04 VM (Simulation Chamber) to verify Phase 2 is correctly implemented and capture the required screenshots.

## 1. Pull the Latest Code
Make sure you have pulled the latest code from GitHub into your Ubuntu 22.04 VM:

```bash
git pull origin main
```

## 2. Build and Test
Run the test command for Phase 2:

```bash
make test_tree
./test_tree
```

If it shows all tests passing, capture your first screenshot.

**📸 Screenshot 2A:** Output of `./test_tree` showing all tests passing.

## 3. Inspect the Object Store
Next, find the generated tree objects and view the raw binary format of one of them.

```bash
find .pes/objects -type f
```

Pick one of the output files (e.g., `.pes/objects/XX/YYY...`) and run:

```bash
xxd .pes/objects/XX/YYY... | head -20
```

**📸 Screenshot 2B:** The output of `xxd` showing the raw binary format of a tree object.

## 4. Final Verification
If both steps worked correctly, Phase 2 is complete.
