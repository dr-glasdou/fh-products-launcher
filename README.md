# DEV

1. clone the repo
2. create `.env` file based on `.env.template`
3. run `docker-compose up --build`

## Steps to Create Git Submodules

1. **Create a new repository on GitHub**
2. **Clone the repository to your local machine**
3. **Add the submodule**, where `repository_url` is the URL of the repository and `directory_name` is the name of the folder where you want the submodule to be saved (it must not exist in the project yet).
   ```
   git submodule add <repository_url> <directory_name>
   ```
4. **Add the changes to the repository** (git add, git commit, git push). Example:
   ```
   git add .
   git commit -m "Add submodule"
   git push
   ```
5. **Initialize and update Submodules**. When someone clones the repository for the first time, they must execute the following command to initialize and update the submodules.
   ```
   git submodule update --init --recursive
   ```
6. **To update the submodule references**:
   ```
   git submodule update --remote
   ```

## Important

When working in the repository that contains the submodules, **first update and push** in the submodule and **then** in the main repository.

If done the other way around, the submodule references in the main repository will be lost, and conflicts will have to be resolved.
