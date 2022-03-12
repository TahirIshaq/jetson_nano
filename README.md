# jetson_nano
Setting up mediapipe library on jetson nano 2gb

# Install mediapipe using docker on nvidia jetson nano 2gb

System Setup
1. Flashed the SD card with the latest operaiting system from the official website
2. Configured the operating system using serial mode. Used wifi as the default communication method.
	- Was able to connect to the router after several failed attempts despite the correct ssid and password. Connection attempts including manual setup were made
3. Fixed docker permission issue. Containers can now run without root permission.

Mediapie
1. Cloned the latest mediapipe repository
2. Ran `docker build --tag=mediapipe .`
	- The repository had a Dockerfile

The following results were obtained after running the last command:

-"debconf: delaying package configuration, since apt-utils is not installed" came up while numerous times during the process
- Got an error while installing tensorflow `pip3 install tensorflow==1.14.0`
	Could not find a version that satisfies the requirement tensorflow==1.14.0 (from versions: )
	No matching distribution found for tensorflow==1.14.0
Possible cause: seems like tensorflow can not be directly installed on aarch64 architecture


3. Commented out the tensorflow installation line from Dockefile and installation was complete

- After running a mediapipe container, bazel version error was encoutered
- Tried to follow the recommended fix, but failed.
