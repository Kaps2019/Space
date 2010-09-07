require 'rake/clean'
require 'jspp'
require 'colored'

NAME = 'faviconize-google.user.js'
CHROME_EXTENSION = 'chrome/faviconize-google.user.js'
SAFARI_EXTENSION = 'Faviconize Google.safariextension'

task :default => :userjs
task :userjs do
  file = JSPP 'chrome/userscript.js'
  File.open NAME, 'w' do |f|
    f.puts file
  end
  puts NAME.green
end

task :chrome do
	file = JSPP 'chrome/userscript.js'
	File.open CHROME_EXTENSION, 'w' do |f|
	  f.puts file
	end
	puts NAME.green
end

task :safari do
  cp 'chrome/faviconize-google.js', SAFARI_EXTENSION
  cp 'chrome/style.css', SAFARI_EXTENSION
  puts SAFARI_EXTENSION.green
end

CLOBBER.include [
	NAME,
	CHROME_EXTENSION,
	"#{SAFARI_EXTENSION}/faviconize-google.js",
	"#{SAFARI_EXTENSION}/style.css"
]