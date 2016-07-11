Symbolicate Crash Logs for iOS/Mac
==================================

symbolicatecrash script written in Ruby.

* supports symbols in ~/Library/Developer/Xcode/*DeviceSupport
* supports spotlight search for dSYMs


to provide symbolication in server via http PUT
-----------------------------------------------

1. install http_parser ruby gem
        
        sudo gem install http_parser.rb

1. install `etc/symbolicatecrash.plist` into /Library/LaunchDaemons
        
        sudo cp etc/symbolicatecrash.plist /Library/LaunchDaemons
        sudo launchctl load /Library/LaunchDaemons/symbolicatecrash.plist

1. Test using curl
        
        curl -v http://localhost:20611 -T my.crash
