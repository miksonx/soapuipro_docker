# SOAPUI PRO & DOCKER

This project was created to aid in the execution of SoapUI PRO tests in container based environments. This is a *work in progress*, and the full feature set found in the SoapUI Testrunner has not been tested on the container version.

This implementation of SoapUI and Docker requires building the project file into the container, and then passing arguments to tailor how this will run outside of the default full project execution. A library of images could then be built/maintained, and pulled in as needed for execution by a pipeline or larger process.

**This is not supported by Smartbear**

------
## REQUIREMENTS & RESTRICTIONS
- Docker 17.09 +
- Valid SoapUI PRO floating license
- License hosted on Protection floating license server and [configured as described in official docs](https://support.smartbear.com/readyapi/docs/general-info/licensing/activate/floating/configure-license-server.html).
- Local project file
- **Currently only supports flat XML projects (default type)**

------
## CLONE REPOSITORY
``` sh
$ git clone https://github.com/nate01776/soapuipro_docker.git
$ cd ./soapui_docker
```

------
## SETUP

- This repository contains 3 folders w/Dockerfiles based off 3 different base images. They are all similar in footprint and run efficiency, but there is a significant build-time savings with the Java image (as it starts with the required dependencies). Once the image is built, the requirements of the included project (if a certain library or process needs to be included) should be used to define which option to build.

## FUTURE
- Support packaged projects instead of XML files - this will allow inclusion of Datasources in some of the standard types, as well as potentially composite projects.
- Support for composite projects on local machine
- Support ability to pull composite project from repository endpoint
- Support for all report types
