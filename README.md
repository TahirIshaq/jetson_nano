# jetson_nano
Setting up mediapipe library on jetson nano 2gb

# System setup
I just followed the instruction from the official website `https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-2gb-devkit`

1. Flashed the SD card with the latest operaiting system
2. Configured the operating system using serial mode. Used wifi as the default communication method.
	- Was able to connect to the router after several failed attempts despite the correct ssid and password. Connection attempts including manual setup were made.
	- There were no problems when the setup was done using an external screen.

# Install mediapipe using docker on nvidia jetson nano 2gb

System Setup
Fixed docker permission issue. Containers can now run without root permission.

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

# References
- https://github.com/jiuqiant/mediapipe_python_aarch64 : Mediapipe binaries for nano
- https://github.com/google/mediapipe: official mediapipe repo
- https://github.com/PINTO0309/mediapipe-bin: mediapipe binaries for nano
