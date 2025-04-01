# frozen_string_literal: true

Dir.glob('tasks/*.rake').each {|file| load file }
task default: %w(test:all)

namespace :wasm do
  desc 'Build the project for WebAssembly target'
  task :build do    
    puts "Building for WebAssembly..."
    
    sh 'BUNDLE_GEMFILE=Gemfile-wasm bundle install'
    
    sh 'BUNDLE_GEMFILE=Gemfile-wasm bundle exec rbwasm build --build-profile minimal -o bin/asciidoctor.wasm'
    
    puts "WASM build completed successfully!"
  end
end
