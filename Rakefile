require 'rake'
require 'spec'
require 'spec/rake/spectask'
require 'cucumber/rake/task'

$:.unshift File.join(File.dirname(__FILE__), 'lib')
require 'carrierwave'

Dir['tasks/**/*.rake'].each { |t| load t }

Spec::Rake::SpecTask.new(:spec) do |t|
  t.spec_opts = %w(-fs -c)
  t.spec_files = FileList['spec/*_spec.rb']
end

Cucumber::Rake::Task.new(:features, 'Run features that should pass') do |t|
  t.profile = 'default'
end

task :default => [:spec, :features]

require 'jeweler'
Jeweler::Tasks.new do |s|
  s.name = 'dsturnbull-carrierwave'
  s.summary = 'fork of carrierwave'
  s.email = 'dsturnbull@me.com'
  s.homepage = 'http://github.com/dsturnbull/carrierwave'
  s.description =<<-eod
    Fork with some nice features
  eod
  s.executables = []
  s.authors = ['David Turnbull']
  s.files = FileList['**/**']
  s.version = CarrierWave::VERSION
end
