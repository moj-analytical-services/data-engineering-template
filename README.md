# Ministry of Justice data engineering template repository

Use this template to [create a repository](https://github.com/moj-analytical-services/data-engineering-template/generate) with the default initial files for a Ministry of Justice data engineering Github repository. These include:

* the correct licence
* Github actions
* .gitignore file

Once you have created your repository, please:

* Edit this readme file to document your project
* Grant permissions to the appropriate MoJ teams
* Set up branch protection

This template is based on the more general [Ministry of Justice template repo](https://github.com/ministryofjustice/template-repository). 

## Githooks
This repo comes with some githooks to make standard checks before you commit files to Github. The checks are: 
- if you're using git-crypt, run `git-crypt status` and check for unencrypted file warnings 
- (NOT YET DONE) run Pytest 

### Installing the hooks
Run this command from the repo's root directory: 

`git config core.hooksPath githooks`

By default hooks live in a .git subfolder that isn't version controlled. This repo instead keeps them in a folder called 'githooks'. The command above tells your copy of the repo to look in this folder instead of the usual location. 

### Skipping the hooks
Once installed, the hooks run each time you commit. To skip them, add `--no-verify` to the end of your commit command. For exmaple, `git commit -m "Committing stuff" --no-verify`.


## To discuss
- How fierce to be on gitignore? We want data to go in S3 rather than in repos, so gitignore csv. But not json as these get used in other ways. 
- nbstripout hook? But we don't really use notebooks

## Licence
[MIT Licence](LICENCE.md)
