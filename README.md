# MonoReaper

Merge github repositories into a monorepo directory while preserving commit history.

## Usage

```bash
git clone git@github.com:ksindi/monoreaper.git && cd monoreaper/
chmod +x monoreaper.sh
bash monoreaper.sh monorepo user/repo0 user/repo1
```

The above script will create a `monorepo` directory with a README.md file and subdirectores `repo0` and `repo1`.

If you now want to add the monorepo to GitHub:

```bash
cd output/monorepo/
git remote add origin git@github.com:user/monorepo
git push -f origin master
```

Note: if the default branch is not master, you can specify it via `userA/repo1/some-branch`.
