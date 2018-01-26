source ENV['GEM_SOURCE'] || "https://rubygems.org"

puppetversion = ENV.key?('PUPPET_GEM_VERSION') ? ENV['PUPPET_GEM_VERSION'] : '~> 3.8'
facterversion = ENV.key?('FACTER_GEM_VERSION') ? ENV['FACTER_GEM_VERSION'] : '~> 2.4.6'

group :development, :test do
  gem 'puppet', puppetversion,              :require => false
  gem 'facter', facterversion,              :require => false
  gem 'rspec-puppet',                       :require => false
  gem 'puppetlabs_spec_helper', '>= 1.2.0', :require => false
  gem 'puppet-lint', '>= 1.0.0',            :require => false
  gem 'puppet_facts',                       :require => false

  if RUBY_VERSION >= '1.9.3' && RUBY_VERSION < '2.0'
    gem 'rake', '< 12.3.0',                 :require => false
    gem 'public_suffix', '~> 1.4.6',        :require => false
    gem 'nokogiri', '~> 1.6.8',             :require => false
    # metadata-json-lint > 1.0.0 needs ruby 2.0 or greater
    gem 'metadata-json-lint', '< 1.0.0',    :require => false
    gem 'json_pure', '< 2',                 :require => false
    gem 'json', '< 2',                      :require => false
  elsif RUBY_VERSION >= '2.0' && RUBY_VERSION < '3.0'
    gem 'rake',                             :require => false
    gem 'metadata-json-lint',               :require => false
    # rubocop requires ruby >= 2.0
    gem 'rubocop',                          :require => false
  end

  unless puppetversion >= '5.0'
    gem 'semantic_puppet',                  :require => false
  end
end

group :system_tests do
  gem 'beaker', '~> 2.4',    :require => false
  gem 'beaker-rspec',        :require => false
  gem 'serverspec',          :require => false
  gem 'rspec-system-puppet', :require => false
end

# vim:ft=ruby
