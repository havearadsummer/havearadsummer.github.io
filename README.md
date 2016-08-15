# havearadsummer

This site uses jekyll to generate static content for our blog.  The subdirectory /jekyll contains the non-generated content and overwrites the /gh-pages directory with the static hosted content.

jekyll build
rsync -r ../gh-pages/* ../
rm -r ../gh-pages

We are using the twenty theme by https://html5up.net/ (purchased at pixelarity)

Bootstrap timeline from http://codepen.io/jasondavis/pen/fDGdK (Jason Davis)

Integrating Instagram feed via https://snapwidget.com

Dashboard page(s) by Pleasure - https://themeforest.net/item/pleasure-material-design-responsive-admin-panel/10579013

