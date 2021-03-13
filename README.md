#### 1. Create Rails API

```rb
rails new <app-name> --api -T --database=postgresql
```

- `-T` to exclude Minitest
- `--database=postgresql` to use PostgreSQL

**Resources:**
- https://guides.rubyonrails.org/api_app.html

#### 2. Install gems

1. Add `rspec-rails` and `factory_bot_rails` to `Gemfile`
```rb
group :development, :test do
  gem 'rspec-rails', '~> 4.1.0'
  gem 'factory_bot_rails'
  gem 'faker'
end
```
2. Then, in `project directory`
```rb
# Download and install
$ bundle install

# Generate boilerplate configuration files
$ rails generate rspec:install
```
3. Configure test suite in `rails_helper.rb`
```rb
RSpec.configure do |config|
  config.include FactoryBot::Syntax::Methods
end
```
4. Check everything is working
```rb
$ rspec
# 0 examples, 0 failures

$ rails s
# See "Yay! You’re on Rails!" on http://localhost:3000/ 
```

**Resources:**
- [rspec-rails](https://github.com/rspec/rspec-rails#installation)
- [factory_bot_rails](https://github.com/thoughtbot/factory_bot_rails#configuration)
- [factory_bot_rails configuration](https://github.com/thoughtbot/factory_bot/blob/master/GETTING_STARTED.md#configure-your-test-suite)
- [faker](https://github.com/faker-ruby/faker)
