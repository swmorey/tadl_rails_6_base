=to deploy to dokku=

- on the dokku server:

dokku apps:create appname
dokku config:set appname KEY=value KEY2=value KEY3=value, etc

add required plugins:

-- if you need redis, for example,
dokku redis:create appname
dokku redis:link appname appname

-- or postgres,
dokku postgres:create appname
dokku postgres:link appname appname

- then add remote to your local repo:

git remote add dokku dokku@servername:appname

- then before pushing, make sure app.json in this repo is set up correctly

To perform post-deploy tasks: http://dokku.viewdocs.io/dokku/advanced-usage/deployment-tasks/

- then push

git push dokku branchname


