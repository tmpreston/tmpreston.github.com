---
layout: post
title: "Normal programming resumes..."
description: ""
date: 2017-06-26
category: 
tags: []
---

![1i]

### Normal programming...

Despite my best intentions I haven't posted recently.  What I did do was test the 'Reset this PC' functionality built into windows 10.
I used to re-install windows as a matter of course every six months or so but haven't done so since free time became so limited.  I started
to have issues with my browser (and http traffic in general) where it would just stop working.  SSH and other TCP services were fine.  
I removed anti-virus/firewalls and still nothing.

So the 'Reset this PC' function in windows 10 works well.  What I didn't count on was the fact that I'd installed/tweaked things for quite
a while getting [Jekyll][1] to play nice on windows.  In the end I decided to try the new [Bash on Ubuntu (on Windows)][2].  There still
ended up being a couple of quirks with Jekyll (even when following the most recent [docs][3]).

#### zlib required!
```
zlib is missing; necessary for building libxml2
```
Solved that error with : apt-get install zlib1g-dev

#### Version hell (just not the DLL kind)
I ended up with incompatible versions of the various libaries required to run/jekyll after attempting `bundle update`

The solution that worked for me was to follow the [github-pages info here][4].  Which seemed like a good idea since it's hosted on
github-pages anyway.

After adding this to the Gemfile everything mostly worked:
```
source 'https://rubygems.org'

require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)

gem 'github-pages', versions['github-pages']
```

#### Last error 
```
/var/lib/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/runtime.rb:317:in `check_for_activated_spec!': You have already activated liquid 4.0.0, but your Gemfile requires liquid 3.0.6. Prepending `bundle exec` to your command may solve this. (Gem::LoadError)
        from /var/lib/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/runtime.rb:32:in `block in setup'
        from /usr/lib/ruby/2.3.0/forwardable.rb:204:in `each'
        from /usr/lib/ruby/2.3.0/forwardable.rb:204:in `each'
        from /var/lib/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/runtime.rb:27:in `map'
        from /var/lib/gems/2.3.0/gems/bundler-1.15.1/lib/bundler/runtime.rb:27:in `setup'
        from /var/lib/gems/2.3.0/gems/bundler-1.15.1/lib/bundler.rb:101:in `setup'
        from /var/lib/gems/2.3.0/gems/jekyll-3.5.0/lib/jekyll/plugin_manager.rb:48:in `require_from_bundler'
        from /var/lib/gems/2.3.0/gems/jekyll-3.5.0/exe/jekyll:9:in `<top (required)>'
        from /usr/local/bin/jekyll:22:in `load'
        from /usr/local/bin/jekyll:22:in `<main>'
```

Points it out right in the console.  Solution is to run using:
```
bundle exec jekyll s
```		

### Next steps
Dealing with these setup quirks kept me busy but since I understand next to no ruby/liquid if I run into other problems I may try something else
to publish this.  There's a dotnet static site generator [Wyam][5] that may be slightly easier to rip apart and work with.  

Jekyll has been interesting and allowed publishing for near zero cost but there seem to be a few ways of chaining together services like
[AppVeyour+Github][6] to do the same thing.

[1]: https://jekyllrb.com
[2]: https://blogs.windows.com/buildingapps/2016/03/30/run-bash-on-ubuntu-on-windows/#kbmjbWBZdF22HbJX.97
[3]: https://jekyllrb.com/docs/windows/
[4]: https://jekyllrb.com/docs/github-pages/#use-the-github-pages-gem
[5]: https://wyam.io/
[6]:https://wyam.io/docs/deployment/appveyor
[1i]: /assets/201706/001_onair.jpg