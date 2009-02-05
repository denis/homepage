gem "BlueCloth"
require "BlueCloth"

task :default => :regenerate
 
desc "Regenerate html files from source"
task :regenerate do
  FileUtils.mkdir("html") unless File.exists?("html")
  
  Dir.glob("src/*.markdown") do |file|
    input = File.new(file).read
    doc = BlueCloth::new(input)
    
    File.open("html/index.html", "w") do |output|
      output << doc.to_html
    end
  end
end
