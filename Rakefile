desc "Compile custom less/bootstrap-build.less to css/"
task :build do

  # Check for the node.js less module
  if `which lessc`.chomp == ''
    puts "Please install the less node package globally [sudo] npm install -g less."
    exit
  end

  # Current Directory from rake root
  base_path = File.expand_path('../', __FILE__ )

  # An array of pathes relative to the base for the include path of the less compiler
  include_paths = %w( bootstrap/less )

  # The less master source file
  source = File.join(base_path, 'less/bootstrap-build.less')
  # The destination css file
  destination = File.join(base_path, 'css/compiled.css')
  # The destination minified css file
  min_destination = File.join(base_path, 'css/compiled-min.css')

  # The base command
  command_base = "lessc --include-path=#{include_paths.map { |p| File.join(base_path, p)}.join(':')}"

  ##
  # Run the commands
  ##
  # Un-minified
  system "#{command_base} #{source} #{destination}"
  # Minified with the -x option to the min_destination
  system "#{command_base} -x #{source} #{min_destination}"
end
