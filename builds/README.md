### Create a build

```
git clone git@github.com:filegator/filegator.git
cd filegator
set version in dist/index.php
chmod -R 775 repository/
chmod -R 775 private/
composer install --no-dev --ignore-platform-reqs
npm install
npm run build
rm -Rf node_modules
rm -Rf frontend
rm -Rf tests
rm -Rf docs
rm -Rf .git
rm -Rf .github
rm README.md couscous.yml .travis.yml repository/.gitignore babel.config.js cypress* .env* .eslint* .gitignore jest.* .php_cs* phpunit* postcss* vue*
cd ..

git clone git@github.com:mediamonks/composer-vendor-cleaner.git
cd composer-vendor-cleaner/ && composer install
chmod 777 ./bin/clean
cd ..

./composer-vendor-cleaner/bin/clean --dir filegator/vendor/
zip -r filegator_v7.x.x.zip filegator/

cp filegator_v7.x.x.zip static/builds/filegator_v7.x.x.zip
rm static/builds/filegator_latest.zip
cp filegator_v7.x.x.zip static/builds/filegator_latest.zip
cd static
git add -A && git commit -m 'cont' && git push


# release version tag on github for filegator/filegator
# create dockerhub tag & upload
# update docs (couscous dep) in filegator/filegator folder

```
