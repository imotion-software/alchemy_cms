source 'https://rubygems.org'

gemspec

rails_version = ENV.fetch('RAILS_VERSION', 6.0).to_f
gem 'rails', "~> #{rails_version}.0"

# Profiling
gem 'rack-mini-profiler', group: :development, require: false

if ENV['DB'].nil? || ENV['DB'] == 'sqlite'
  gem 'sqlite3', rails_version > 5.0 ? '~> 1.4.1' : '~> 1.3.6'
end
gem 'mysql2', '~> 0.5.1' if ENV['DB'] == 'mysql'
gem 'pg',     '~> 1.0'   if ENV['DB'] == 'postgresql'
gem 'sassc-rails'

group :development, :test do
  gem 'simplecov', require: false
  gem 'bootsnap', require: false
  unless ENV['CI']
    gem 'launchy'
    gem 'annotate'
    gem 'bumpy'
    gem 'yard'
    gem 'redcarpet'
    gem 'pry-byebug'
    gem 'rubocop', require: false
    gem 'listen'
    gem 'localeapp', '~> 3.0', require: false
    gem 'dotenv', '~> 2.2'
    gem 'github_fast_changelog', require: false
    gem 'active_record_query_trace', require: false
  end
end
