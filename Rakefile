require 'rubygems'
require 'bundler/setup'
require 'less'
require 'listen'

desc "Compile custom less/bootstrap-build.less to css/"
task :build do
  # The master file we're building
  build_file = File.expand_path('../less/bootstrap-build.less', __FILE__)
  parser = Less::Parser.new :paths => [ './less', './bootstrap/less' ], :filename => 'bootstrap-build.less'
  tree = parser.parse(open(build_file).read)
  # Save the minified version
  File.open('./css/compiled-min.css', 'w+') do |f|
    f.write tree.to_css(:yuicompress => true)
  end
  # Save the full version
  File.open('./css/compiled.css', 'w+') do |f|
    f.write tree.to_css
  end
end

desc "Watch all less files and build on change"
task :watch do
  puts "I'm watching you...\n"
  Listen.to(File.expand_path('../', __FILE__), :filter => /\.less$/) do
    puts "Building #{Time.now.strftime('%r')}\n"
    Rake::Task["build"].execute
  end
end
