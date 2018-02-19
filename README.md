# MonoReaper

Merge GitHub repositories into a monorepo directory while preserving commit history.

## Usage

```bash
git clone git@github.com:ksindi/monoreaper.git && cd monoreaper/
chmod +x monoreaper.sh
bash monoreaper.sh user/repo0 user/repo1
# you can specify branch via `user/repo0/some-branch`.
```

The above script will create a `monorepo` directory with a README.md file and subdirectores `repo0` and `repo1`.

If you now want to add the monorepo to GitHub:

```bash
cd monorepo/
git remote add origin git@github.com:user/monorepo
git push -f origin master
```

### Merging with existing monorepos

If you already have a monorepo and want to merge other repos into it,
all you have to do is include a `MONOREPO_DIR` env variable:

```bash
MONOREPO_DIR=path/to/my/monorepo bash monoreaper.sh user/repo0 user/repo1
```

Note that the `MONOREPO_DIR` must have `master` as default branch.


## Why monorepos?

- Streamlines ops logic like doing CICD. The overhead of setting up pipelines and deployments is cumbersome.
- Shared codebase introduces shared ownership, naming and style.
- Dependencies across services are easier to manage.
- Searching code across multiple repos is a hassle.
- Lots of great tools that take advantage of monorepos:
  - [pull-review](https://github.com/imsky/pull-review): automate pull reviews with lots of configuration options.
  - [buildpipe](https://github.com/ksindi/buildpipe): customizing pipeline logic by looking at git changes in projects.
- Lots of anecdotal evidence:
  - [Optimizing for iteration speed](https://erikbern.com/2017/07/06/optimizing-for-iteration-speed.html)
  - [Why Google Stores Billions of Lines of Code in a Single Repository](https://research.google.com/pubs/pub45424.html)
 
