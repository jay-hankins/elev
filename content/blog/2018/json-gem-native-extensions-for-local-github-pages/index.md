---
layout: post
title: "Solution: GitHub Pages Build Failure Due to Error Installing json (1.8.3)"
description: Specify a workaround branch of the gem for Sierra and High Sierra
date: '2018-01-29T22:40:32.169Z'
---

I'm not as familiar with the Ruby and Jekyll ecosystems as I'd like to be, so all I know how to do is follow a GitHub Pages [help article](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/) which tells me how to set up the GH-Pages environment on my system.

Hoewver, I ran into an issue on macOS High Sierra 10.13.2 and ruby 2.5.0 from Homebrew. When I went to install the GitHub Pages gems to my local directory using `bundle install`, I got this error:
```
Installing json 1.8.3 with native extensions
Gem::Ext::BuildError: ERROR: Failed to build gem native extension.
...
An error occurred while installing json (1.8.3), and Bundler cannot continue.
Make sure that `gem install json -v '1.8.3'` succeeds before bundling.
```

Well, from [this issue](https://github.com/flori/json/issues/253) it seems that macOS Sierra and High Sierra with ruby v 2.4 onwards is not compatible with `json` 1.8.3.

I don't know exactly why this happens, but a workaround for now is to modify the Gemfile and add this line to it:
```
gem 'json', github: 'flori/json', branch: 'v1.8'
```

If you have the default GitHub Pages help article Gemfile, it will look like this after correction:
```
source 'https://rubygems.org'
gem 'json', github: 'flori/json', branch: 'v1.8'
gem 'github-pages', group: :jekyll_plugins
```

Now you can ` bundle install ` and `bundle exec jekyll serve` to see your site built locally again. Nice!

P.S. Can anyone tell me why the following happens? "jekyll serve" errors, but "bundle exec jekyll serve" runs everything hunky-dory.

Output:
```
~/dev/personal/jay-hankins.github.io master* 1m
❯ jekyll serve
Traceback (most recent call last):
	10: from /usr/local/bin/jekyll:23:in `<main>'
	 9: from /usr/local/bin/jekyll:23:in `load'
	 8: from /usr/local/lib/ruby/gems/2.5.0/gems/jekyll-3.6.2/exe/jekyll:11:in `<top (required)>'
	 7: from /usr/local/lib/ruby/gems/2.5.0/gems/jekyll-3.6.2/lib/jekyll/plugin_manager.rb:50:in `require_from_bundler'
	 6: from /usr/local/Cellar/ruby/2.5.0/lib/ruby/2.5.0/bundler.rb:107:in `setup'
	 5: from /usr/local/Cellar/ruby/2.5.0/lib/ruby/2.5.0/bundler/runtime.rb:26:in `setup'
	 4: from /usr/local/Cellar/ruby/2.5.0/lib/ruby/2.5.0/bundler/runtime.rb:26:in `map'
	 3: from /usr/local/Cellar/ruby/2.5.0/lib/ruby/2.5.0/forwardable.rb:229:in `each'
	 2: from /usr/local/Cellar/ruby/2.5.0/lib/ruby/2.5.0/forwardable.rb:229:in `each'
	 1: from /usr/local/Cellar/ruby/2.5.0/lib/ruby/2.5.0/bundler/runtime.rb:31:in `block in setup'
/usr/local/Cellar/ruby/2.5.0/lib/ruby/2.5.0/bundler/runtime.rb:313:in `check_for_activated_spec!': You have already activated json 2.1.0, but your Gemfile requires json 1.8.6. Since json is a default gem, you can either remove your dependency on it or try updating to a newer version of bundler that supports json as a default gem. (Gem::LoadError)

~/dev/personal/jay-hankins.github.io master*
❯ bundle exec jekyll serve
Configuration file: /Users/jay/dev/personal/jay-hankins.github.io/_config.yml
       Deprecation: The 'gems' configuration option has been renamed to 'plugins'. Please update your config file accordingly.
            Source: /Users/jay/dev/personal/jay-hankins.github.io
       Destination: /Users/jay/dev/personal/jay-hankins.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
   GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.
                    done in 1.912 seconds.
 Auto-regeneration: enabled for '/Users/jay/dev/personal/jay-hankins.github.io'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
  ```

P.P.S. I need recommendations on a successor to Jekyll. I'm thinking of some React or Vue static server side something something... tell me your faves!
