source "https://rubygems.org"

# The `github-pages` gem pins Jekyll 3 and Liquid 4, which do not run on current Ruby
# (Liquid still calls `String#tainted?`, removed in Ruby 3.2). GitHub Pages deployment
# via Actions only needs a static `_site` directory, so Jekyll 4 is compatible with
# https://pages.github.com/versions/ constraints when you build in CI yourself.
gem "jekyll", "~> 4.3"
gem "webrick", "~> 1.8"
