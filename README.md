# ChatGPT Alternative Built With Superpowers - ChatSonic (Now GPT-4 Powered) Rails Gem

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/alexrudall/ruby-openai/blob/main/LICENSE.txt)
[![Maintainability](https://api.codeclimate.com/v1/badges/a99a88d28ad37a79dbf6/maintainability)](https://codeclimate.com/github/codeclimate/codeclimate/maintainability)

Use the [ChatSonic API](https://writesonic.com/chat) with Ruby! 🤖❤️

Trusted by 1,000,000+ marketing teams, agencies, and freelancers. 10,000+ 5-star ratings.

### 1. Write Factual Trending Content
### 2. Generate AI Art
### 3. Write anywhere and everywhere

## How to Use ?

### Bundler

Add this line to your application's Gemfile:

```ruby
gem "chatsonic"
```

And then execute:

$ bundle install

### Gem install

Or install with:

$ gem install chatsonic

and require with:

```ruby
require "chatsonic"
```


## Usage

- Get your API key from [https://app.writesonic.com/settings/api](https://app.writesonic.com/settings/api)

### Quickstart

For a quick test you can pass your token directly to a new client:

```ruby
client = ChatSonic::Client.new(access_token: "Your API Key")
```

### With Config

For a more robust setup, you can configure the gem with your API keys, for example in an `chatsonic.rb` initializer file. Never hardcode secrets into your codebase - instead use something like [dotenv](https://github.com/motdotla/dotenv) to pass the keys safely into your environments.

```ruby
ChatSonic.configure do |config|
    config.access_token = ENV.fetch('OPENAI_ACCESS_TOKEN')
end
```

Then you can create a client like this:

```ruby
client = ChatSonic::Client.new
```

#### Custom timeout or base URI

The default timeout for any OpenAI request is 120 seconds. You can change that passing the `request_timeout` when initializing the client. You can also change the base URI used for all requests. 

```ruby
client = ChatSonic::Client.new(
    access_token: "access_token_goes_here",
    uri_base: "https://api.writesonic.com/",
    request_timeout: 240
)
```

or when configuring the gem:

```ruby
OpenAI.configure do |config|
    config.access_token = ENV.fetch("OPENAI_ACCESS_TOKEN")
    config.uri_base = "https://api.writesonic.com/" # Optional
    config.request_timeout = 240 # Optional
end
```

### ChatSonic

ChatSonic is a model that can be used to generate text in a conversational style.

```ruby

client.prompt(parameters: {
    enable_google_results: true,
    enable_memory: true,
    input_text: 'Write Me a Poem'
  })
# => "Hello! How may I assist you today?"
```

input_text can be your prompt

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the Ruby OpenAI project's codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/alexrudall/ruby-openai/blob/main/CODE_OF_CONDUCT.md).


## ToDo: Implement
1. Create a pull request template
2. Create a circle CI for CI/CD
3. Rspec to be implemented
