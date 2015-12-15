### Bitcode must be disabled in XCode:

	Target > Build Settings > Build Options > Enable Bitcode: No

### .plist file must be configured to support the following external protocol:

<key>UISupportedExternalAccessoryProtocols</key>
	<array>
		<string>com.uk.tsl.rfid</string>
	</array>

### The following Frameworks are needed:

	ExternalAccessory.framework
	TSLAsciiCommands.framework
	UIKit.framework
	Foundation.framework
	CoreGraphics.framework

### Install the plugin

cordova plugin add https://github.com/Torchid/TSL-Interface.git

### Example - How to Use the Plugin:

	var rfidResult = "";

	//tagMsg will be the data read off of the NFC tag
	var success = function(tagMsg){
	    rfidResult = tagMsg;
	};

	var fail = function(err){
	    alert("Fail");
	};

	window.background.RFIDGun.pair(success, fail);
