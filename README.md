# OmniAuth CreateSend
[![Build Status](https://secure.travis-ci.org/campaignmonitor/omniauth-createsend.png)][travis] [![Dependency Status](https://gemnasium.com/campaignmonitor/omniauth-createsend.png)][gemnasium] [![Gem Version](https://badge.fury.io/rb/omniauth-createsend.png)][gembadge]

This is the official [OmniAuth](http://www.omniauth.org/) strategy for authenticating with the [Campaign Monitor API](http://www.campaignmonitor.com/api/). You'll need to register an OAuth Application in your Campaign Monitor account to get a Client ID and Client Secret to use with this OmniAuth strategy.

[travis]: http://travis-ci.org/campaignmonitor/omniauth-createsend
[gemnasium]: https://gemnasium.com/campaignmonitor/omniauth-createsend
[gembadge]: http://badge.fury.io/rb/omniauth-createsend

## Installing

Add a dependency in your `Gemfile`:

```ruby
gem 'omniauth-createsend'
```

Then `bundle install`.

## Basic Usage

```ruby
use OmniAuth::Builder do
  provider "createsend", ENV['CREATESEND_CLIENT_ID'], ENV['CREATESEND_CLIENT_SECRET'], :scope => 'ViewReports,CreateCampaigns,SendCampaigns'
end
```

This gem also includes an [example](https://github.com/campaignmonitor/omniauth-createsend/blob/master/example/config.ru) Rack application which demonstrates how to authenticate with the Campaign Monitor API using this OmniAuth strategy.

Once you've authenticated, you should use the [createsend](http://campaignmonitor.github.com/createsend-ruby/) gem to access Campaign Monitor resources.

## Contributing
1. Fork the repository
2. Make your changes, including tests for your changes.
3. Ensure that the build passes, by running `bundle exec rake` (CI runs on: `1.9.3`, `1.9.2`, `1.8.7` and `ree`)
4. It should go without saying, but do not increment the version number in your commits.
5. Submit a pull request.