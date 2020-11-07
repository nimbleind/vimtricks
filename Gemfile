source 'https://rubygems.org'
ruby '2.4.3'

foo
require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)

gem 'github-pages', versions['github-pages']
gem 'jekyll-gravatar'
gem 'jekyll-sitemap'
gem 'rake'
gem 's3_website'
