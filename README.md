# Producing

        ./distribute-for-carthage.sh <config>

Where config is the name of a file in the configs/ directory.  Samples exist
there.

At the moment, hub will create a draft release so it can be examined before
fully releasing.  We can make this optional or make it always release
immediately.

# Consuming

Download the Chat iOS Demo application:

        wget https://github.com/twilio/twilio-chat-demo-ios/archive/master.zip

Create a Cartfile:

        cat > Cartfile << _DONE_
        github "rbeiter/twilio-chat-ios"
        github "rbeiter/twilio-accessmanager-ios"
        _DONE_

Or for Sync:

        cat > Cartfile << _DONE_
        github "rbeiter/twilio-sync-ios"
        _DONE_

Boostrap carthage:

        brew install carthage # if needed
        carthage bootstrap

Since Carthage only manages versions and the download of the framework, not integration of it, you'll need to complete the process using the manual integration steps found at:  https://www.twilio.com/docs/api/chat/sdks#manual-integration
