# 11- Finding Contributors Using Shortlog

If we need to see everyone that made contributions to our project we can use the `git shortlog` command. This will output the following:

```zsh
Fernando Moraes (14):
      html do index/show
      Merge branch 'main' of github.com:jmschp/kids-time into main
      index e show html
 [...]
      bttns
      atualicazao seed
      bttns com link, pagina activitys

Miguel Pimenta (135):
      Initial commit with minimal template from https://github.com/lewagon/rails-templates
      Initialized rails app
      Added and configured Devise gem
      Configured Cloudinary
      Added Models Activity Order, and added columns to users
 [...]
```

The contributor, the number of commits and the commits messages.

The command accepts various options, for example `git shortlog -n` will sort output according to the number of commits per author.

The command `git shortlog -s`, suppress commit descriptions, only provides commit count and authors.

We can also filter using `--before=` and `--after=`, to view teh contributor in a date range.
