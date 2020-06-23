# Ministry of Justice data engineering template repository

Use this template to [create a repository](https://github.com/moj-analytical-services/data-engineering-template/generate) with the default initial files for a Ministry of Justice data engineering Github repository. These include:

* the correct licence
* pre-commit githooks
* .gitignore file

Once you have created your repository, please:

* edit this readme file to document your project
* grant permissions to the appropriate MoJ teams
* set up branch protection

This template is based on the more general [Ministry of Justice template repo](https://github.com/ministryofjustice/template-repository). 

# Formatting and linting
The file called .flake8 is a config file that sets the linter's max line length to 88. This is to match Black's default. It's the team's agreed preferred max line length. 

Config changes for Black should go in `pyproject.toml`.

Config changes for yamllint should go in `.yamllint`.

Our standard settings use the default for both of these, so at the moment those configs make no changes.  

## Githooks
This repo comes with some githooks to make standard checks before you commit files to Github. The checks are: 
- if you're using git-crypt, run `git-crypt status` and check for unencrypted file warnings 
- run Black on Python files
- run Flake8 on Python files
- (NOT YET DONE) run yamllint on yaml files

### Installing the hooks
Run this command from the repo's root directory: 

`git config core.hooksPath githooks`

By default hooks live in a .git subfolder that isn't version controlled. This repo instead keeps them in a folder called 'githooks'. The command above tells your copy of the repo to look in this folder instead of the usual location. 

You can also add these hook to other repos by copying from this repo's githooks folder and pasting into the other repo's .git/hooks folder.

### Skipping the hooks
Once installed, the hooks run each time you commit. To skip them, add `--no-verify` to the end of your commit command. For exmaple, `git commit -m "Committing stuff" --no-verify`.


## To discuss
- How fierce to be on gitignore? We want data to go in S3 rather than in repos, so gitignore csv. But not json as these get used in other ways. 
- nbstripout hook? But we don't really use notebooks

## Licence
[MIT Licence](LICENCE.md)
