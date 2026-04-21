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

# Phase 3 Instructions

Follow these steps on your Ubuntu 22.04 VM (Simulation Chamber) to verify Phase 3 is correctly implemented and capture the required screenshots.

## 1. Pull the Latest Code
Make sure you have pulled the latest code from GitHub into your Ubuntu 22.04 VM:

```bash
git pull origin main
```

## 2. Build and Test the Index
Run the following commands to initialize the repository, add files to the staging area, and check the status:

```bash
make pes
./pes init
echo "hello" > file1.txt
echo "world" > file2.txt
./pes add file1.txt file2.txt
./pes status
```

**📸 Screenshot 3A:** Output of the `pes init`, `pes add`, and `pes status` sequence.

## 3. Inspect the Staging Area
Check the contents of the index file:

```bash
cat .pes/index
```

**📸 Screenshot 3B:** Output showing the text-format index with your entries.

# Phase 4 Instructions

Follow these steps on your Ubuntu 22.04 VM (Simulation Chamber) to verify Phase 4 is correctly implemented and capture the required screenshots.

## 1. Pull the Latest Code
Make sure you have pulled the latest code from GitHub into your Ubuntu 22.04 VM:

```bash
git pull origin main
```

## 2. Create Commits
Run the following commands to create multiple commits:

```bash
./pes init
echo "Hello" > hello.txt
./pes add hello.txt
./pes commit -m "Initial commit"

echo "World" >> hello.txt
./pes add hello.txt
./pes commit -m "Add world"

echo "Goodbye" > bye.txt
./pes add bye.txt
./pes commit -m "Add farewell"

./pes log
```

**📸 Screenshot 4A:** Output of `./pes log` showing three commits with hashes, authors, timestamps, and messages.

## 3. Inspect Object Growth and Refs
View the accumulated objects and references:

```bash
find .pes -type f | sort
```
**📸 Screenshot 4B:** Output showing object store growth after three commits.

```bash
cat .pes/refs/heads/main
cat .pes/HEAD
```
**📸 Screenshot 4C:** Output showing the branch pointer and HEAD reference.

## 4. Integration Test
Finally, run the full integration test:

```bash
make test-integration
```
If it passes successfully, you are done! Capture any required screenshots.
