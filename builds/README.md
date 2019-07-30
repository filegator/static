### Create a build
Clone with git, cd into dir and run:
```
set version in dist/index.php
sudo chmod -R 777 repository/
sudo chmod -R 777 private/
composer install --no-dev
npm install
npm run build
cp configuration_sample.php configuration.php
rm -Rf node_modules
rm -Rf frontend
rm -Rf tests
rm -Rf docs
rm -Rf .git
rm -Rf .github
rm README.md couscous.yml .travis.yml repository/.gitignore babel.config.js composer* cypress* .env* .eslint* .gitignore jest.* package* .php_cs* phpunit* postcss* vue*
cd ..
./composer-vendor-cleaner/bin/clean --dir filegator/vendor/
zip -r filegator_v7.0.0.zip filegator/

```
