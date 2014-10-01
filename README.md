dev.sh - a simple project collection search tool  
=============================================

I built this script because my development folder, that contains all my dev projects in a numbered order (`01_first-project`, `02_second-project`, etc.), is getting more and more cluttered and it's not easy anymore to quickly find a specific project. Current features:

* list all projects with `dev`
* fuzzy search for projects with `dev <term>`

# Installation

    git clone git://github.com/frdmn/dev-sh.git /usr/local/src/dev-sh

    # if you use Bash shell
    echo 'export devsearch_projectspath="${HOME}/Dropbox/Share/Development"' >> ~/.bashrc
    echo ". /usr/local/src/dev-sh/dev.sh" >> ~/.bashrc
    # or if you use ZSH
    echo 'export devsearch_projectspath="${HOME}/Dropbox/Share/Development"' >> ~/.zshrc
    echo ". /usr/local/src/dev-sh/dev.sh" >> ~/.zshrc

# Usage

You just need to edit the `$projectspath` variable on line 3 and then you are good to go. Make sure you have all your projects in one folder level.

### List projects

    $ dev  
    Info: 8 available projects:
    01_projectA_one  02_projectA_two  03_projectB_one  04_projectB_two  05_projectB_three  06_projectB_four  07_projectB_five  08_projectB_six

### Search for a specific project

If there is only one search result, you'll automatically change into that project directory:

    > dev 01
    Info: Only one result found while searching for "01". cd into "01_projectA_one"...

    > pwd
    /Users/username/Development/01_projectA_one

And if there are multiple results, you'll get a list of those:

    > dev projectB
    Info: Found 6 result while searching for "project":
    03_projectB_one  04_projectB_two  05_projectB_three  06_projectB_four  07_projectB_five  08_projectB_six

# Todo

- [ ] Support folders with whitespaces
