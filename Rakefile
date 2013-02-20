require "rake/clean"
CLEAN.include "**/.DS_Store"

desc "Build .NET library for Carrot"
task :default

# Docs task
DOXYGEN_BINARY = "/Applications/Doxygen.app/Contents/Resources/doxygen"

def doxygen?
  return if not File.exist?(DOXYGEN_BINARY)
  return true
end

if doxygen?
  task :docs do
    sh DOXYGEN_BINARY
  end
end

#
# Mono build tasks
#
task :default => "mono:library"

desc "Build .NET Library"
task :mono => "mono:library"
namespace :mono do
  task :library do
    sh "xbuild"
  end
end
