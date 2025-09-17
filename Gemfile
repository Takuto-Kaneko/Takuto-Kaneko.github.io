source "https://rubygems.org"

gem "jekyll", "~> 4.4.1"

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-remote-theme", "~> 0.4.3"
end

gem "webrick" 

# Windows, JRuby
platforms :windows, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

platform :windows do
  gem "wdm", "~> 0.2.0", require: false
end

gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]

gem "jekyll-seo-tag", "~> 2.8"
