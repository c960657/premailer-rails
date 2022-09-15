source 'https://rubygems.org'

gemspec

rails_version = ENV.fetch('ACTION_MAILER_VERSION', '6')

if rails_version == 'master'
  git 'git://github.com/rails/rails.git' do
    gem 'rails'
  end
  gem 'sprockets-rails', github: 'rails/sprockets-rails'
  gem 'arel', github: 'rails/arel'
elsif rails_version.split('.').first.to_i >= 7
  gem 'rails', "~> #{rails_version}"
  gem ENV.fetch("ASSETS_GEM", "sprockets-rails")
else
  gem 'rails', "~> #{rails_version}"
end

gem 'byebug'
gem 'net-smtp', require: false

# platforms :rbx do
#   gem 'rubysl'
#   gem 'racc'
# end

gem 'tins', '< 1.7' if RUBY_VERSION.split('.').first.to_i < 2
