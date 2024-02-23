# PROJECT_NAME

This is a simple boilerplate for a Python project. To personalise it, you can:
use a combination of `sed` and `rename`:

```bash
# Replace PROJECT_NAME with the name of your project
your_project_name=$(read -p "Enter your project name: " name; echo $name)
find . -type f -exec sed -i 's/PROJECT_NAME/your_project_name/g' {} +
find . -type f -exec rename 's/PROJECT_NAME/your_project_name/g' {} +
```
The LICENSE file is a template. You should replace `COPYRIGHT_YEAR` and
`COPYRIGHT_HOLDER` with the appropriate values, for example `2020` and `Your Name`.

```bash
# set copyright year to current year
CURRENT_YEAR=$(date +'%Y')
# if you want to use your git user:
COPYRIGHT_HOLDER=$(git config user.name)
# or set it manually
COPYRIGHT_HOLDER=$(read -p "Enter your name: " name; echo $name)
find . -type f -exec sed -i "s/COPYRIGHT_YEAR/$CURRENT_YEAR/g" {} +
find . -type f -exec sed -i "s/COPYRIGHT_HOLDER/$COPYRIGHT_HOLDER/g" {} +
```

You'll probably want to set up a virtual environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
# upgrade pip to the latest version
pip install --upgrade pip
```
And for the sake of completeness, remove .git and start a new repository:

```bash
rm -rf .git
git init
```
bonus: use the github cli `gh` to create a new repository on GitHub:

```bash
repo_description=$(read -p "Enter a description for your project: " description; echo $description)
gh repo create -d "$repo_description" --public -y "$(basename $(pwd))"
```

finally, replace the contents of this file with your PROJECT_NAME and a
description of your project.
``` bash
echo -e "# your_project_name" > README.md
echo -e "\n$repo_description" >> README.md
```


