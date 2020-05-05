# lgrzegorek.github.io
Website powered by Hugo

***How to maintain website from new computer?***

    git clone https://github.com/lgrzegorek/website.git && cd website
    hugo server #verify if it is running on localhost:1313 #lets customize website
    git submodule add -f git@github.com:lgrzegorek/lgrzegorek.github.io.git public
    hugo
    cd public && git remote -v
    git add . && git commit -m "message" && git push origin master

***You can use deploy.sh script***

    #!/bin/sh

    # If a command fails then the deploy stops
    set -e

    printf "\033[0;32mDeploying updates to GitHub...\033[0m\n"

    # Build the project.
    hugo # if using a theme, replace with `hugo -t <YOURTHEME>`

    # Go To Public folder
    cd public

    # Add changes to git.
    git add .

    # Commit changes.
    msg="rebuilding site $(date)"
    if [ -n "$*" ]; then
        msg="$*"
    fi
    git commit -m "$msg"

    # Push source and build repos.
    git push origin master
