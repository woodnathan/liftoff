require_relative '../deployment/lib/deployment/release'
require 'rspec/core/rake_task'
require 'rake/packagetask'

$LOAD_PATH.unshift(File.expand_path('../lib', __FILE__))
require 'liftoff/version'

Deployment::Release.new do |release|
  release.name = 'Liftoff'
  release.version = Liftoff::VERSION
  release.gem_directory = 'vendor/gems'

  release.git = 'git@github.com:thoughtbot/liftoff.git'

  release.homebrew_directory = 'homebrew-formulae'
  release.homebrew_git = 'git@github.com:thoughtbot/homebrew-formulae'

  release.gh_pages_dir = 'gh-pages'

  release.package = Proc.new do |p|
    p.need_tar_gz = true
    p.package_files.include('src/**/*')
    p.package_files.include('defaults/**/*')
    p.package_files.include('lib/**/*')
    p.package_files.include('templates/**/*')
    p.package_files.include('vendor/**/*')
    p.package_files.include('man/**/*')
    p.package_files.include('LICENSE.txt')
  end
end

desc 'Run tests'
RSpec::Core::RakeTask.new(:spec)

task :default => :spec
