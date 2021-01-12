## gyp: No Xcode or CLT version detected!

To fix this error, you need to re-install the Xcode command-line tools.

1. First, delete the Xcode tools by using the below command.

	`sudo rm -rf $(xcode-select -print-path)`

	This above command asks for a system password.

2. Now, install the Xcode by running this command.

	`xcode-select --install`

	This command prompts with a popup, click on the install button and proceed with the installation.

	It takes some time to download and install the Xcode command-line tools.

	Once you are successfully installed, you can now download new npm packages without any (gyp) error messages.