# lgrzegorek.github.io
Website powered by Hugo

##How to maintain website from new computer?
    git clone https://github.com/lgrzegorek/website.git && cd website
    hugo server #verify if it is running on localhost:1313
    git submodule add -f git@github.com:lgrzegorek/lgrzegorek.github.io.git public
    hugo
    cd public && git remote -v
    git add . && git commit -m "message" && git push origin master
