task default: %w[build]

task :build do
  puts "\nBuilding project"
  try "middleman build"
end

namespace :travis do
  task :script do
    Rake::Task["build"].invoke
  end
end

## Helper so we fail as soon as a command fails.
def try(command)
  system command
  if $? != 0 then
    raise "Command: `#{command}` exited with code #{$?.exitstatus}"
  end
end