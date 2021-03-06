require 'opal'
require_relative 'opal/dxopal/version'

desc "Build dxopal.js"
task :build => ["build/dxopal.js"]

desc "Build dxopal.js and dxopal.min.js"
task :build_min => ["build/dxopal.min.js", "starter-kit/dxopal.min.js"]

file "starter-kit/dxopal.min.js" => "build/dxopal.min.js" do |t| cp t.source, t.name end

file "build/dxopal.min.js" => "build/dxopal.js" do |t|
  sh "uglifyjs #{t.source} -o #{t.name}"
end

file "build/dxopal.js" => Dir["opal/**/*.rb"] do |t|
  Opal.append_path("opal")
  js = Opal::Builder.build("dxopal.rb").to_s
  File.write(t.name, js)
end

desc "Rebuild API reference"
task :api do
  sh "yard doc -o doc/api/ opal/**/*.rb"
end

namespace "release" do
  desc "Make a release commit"
  task :make_release_commit do
    sh "rake api"
    sh "rake build_min -B"
    sh "gem build dxopal.gemspec"
    sh "git ci -a -m 'v#{DXOpal::VERSION}'"
  end

  desc "Make a tag and push to github"
  task :push_tag do
    sh "git tag 'v#{DXOpal::VERSION}'"
    sh "git push origin master --tags"
  end

  desc "Release gem"
  task :push_gem do
    sh "gem push dxopal-#{DXOpal::VERSION}.gem"
  end

  desc "Release starter kit"
  task :release_kit do
    cd "starter-kit" do
      sh "git status"
      print "ok? [y/n] "
      if $stdin.gets.chomp == "y"
        sh "git ci dxopal.min.js -m 'v#{DXOpal::VERSION}'"
        sh "git tag 'v#{DXOpal::VERSION}'"
        sh "git push origin master --tags"
      end
    end
  end
end

# How to make a release
# 0. Edit opal/dxopal/version.rb
# 1. Add release date in CHANGELOG.md
# 2. `rake release:make_release_commit`
# 3. Test
#   - Open starter-kit/index.html in Firefox
#   - rackup and open http://localhost:9292/
# 4. `rake release:push_tag`
# 5. `rake release:push_gem`
# 6. `rake release:release_kit`
