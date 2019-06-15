# Heroku Build Cache Loader-Persister

## Usage
1. Prepend `heroku-build-cache-loader` to the top of your buildpack stack with Heroku CLI
```
heroku buildpacks:add --index 1 https://github.com/Kenneth-KT/heroku-build-cache-loader.git
```
2. Append `heroku-build-cache-persister` to the bottom of your buildpack stack with
```
heroku buildpacks:add https://github.com/Kenneth-KT/heroku-build-cache-persister.git
```
3. Create file named `.buildcache` which contains pattern of files (in .gitignore like format) that you want to persist across heroku builds. Example:
```
# This is a comment and will be ignored

# single file
single_file.txt

# simple glob
simple/glob/*.txt

# recursive glob
recursive/glob/**/*.txt

# complex glob
complex/glob/**/prefix*suffix.txt
```

4. Commit that file and push to heroku to deploy and you are done.
