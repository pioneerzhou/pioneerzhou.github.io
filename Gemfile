source "https://rubygems.org"

# Hello! This is where you manage which Jekyll version is used to run.
# When you want to use a different version, change it below, save the
# file and run `bundle install`. Run Jekyll with `bundle exec`, like so:
#
#     bundle exec jekyll serve
#
# This will help ensure the proper Jekyll version is running.
# Happy Jekylling!

gem "github-pages", group: :jekyll_plugins

# If you want to use Jekyll native, uncomment the line below.
# To upgrade, run `bundle update`.

# gem "jekyll"

gem "wdm", "~> 0.1.0" if Gem.win_platform?

# If you have any plugins, put them here!
group :jekyll_plugins do
  # gem "jekyll-archives"
  gem "jekyll-feed"
  gem 'jekyll-sitemap'
  gem 'hawkins'
  gem "webrick", "~> 1.8"
  gem "jekyll-sass-converter", "1.5.2" # 使用 1.5.2 版本
end

# Add tzinfo-data gem
gem 'tzinfo-data'

gem 'faraday-retry'
#faraday-retry 是 Faraday HTTP 客户端库的一个插件，它为 HTTP 请求添加了自动重试的功能。
#在网络请求中，有时由于网络问题或服务器问题导致请求失败，为了增加请求的稳定性和可靠性，我们可以使用重试机制来重新发送失败的请求。
#faraday-retry 可以配置在发生特定类型的错误时自动重试请求，并提供了一些参数来自定义重试的行为，例如重试次数、重试延迟等。