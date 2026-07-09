heroku-buildpack-imagemagick
=================================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for vendoring the ImageMagick binaries into your project.

This one actually works :)

### Install

In your project root:

`heroku buildpacks:add https://github.com/DuckyTeam/heroku-buildpack-imagemagick  --index 1 --app HEROKU_APP_NAME`

"index 1" means that imagemagick will be installed first.

### Changing version
Find the version you want in the [ImageMagick tags](https://github.com/ImageMagick/ImageMagick/tags). Set `IMAGE_MAGICK_VERSION` or edit the default version in `bin/compile`. Clear the cache, as shown below, and redeploy your app to Heroku.

### Clear cache
Since the installation is cached you might want to clean it out due to config changes.

1. `heroku plugins:install heroku-repo`
2. `heroku repo:purge_cache -app HEROKU_APP_NAME`
