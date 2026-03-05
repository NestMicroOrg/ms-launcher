## Dev

1. Clone the repository.
2. Create an `.env` file based on the `.env.template` file and set the necessary environment variables.
3. Run `docker compose up --build` to start the application.

### Steps to Create Git Submodules

1. Create a new repository on GitHub.
2. Clone the repository to your local machine.
3. Add the submodule, where `repository_url` is the URL of the repository and `directory_name` is the name of the folder where you want to save the sub-module (it must not already exist in the project):

```
git submodule add <repository_url> <directory_name>
```

4. Add the changes to the repository (git add, git commit, git push).
   Example:

```
git add .
git commit -m "Add submodule"
git push
```

5. Initialize and update sub-modules. When someone clones the repository for the first time, they must run the following command to initialize and update the sub-modules:

```
git submodule update --init --recursive
```

6. To update the sub-module references:

```
git submodule update --remote
```

## Important

When working in the repository that contains sub-modules, **first update and push** in the sub-module and **then** in the main repository.

If you do it the other way around, you will lose the sub-module references in the main repository and will have to resolve conflicts.
