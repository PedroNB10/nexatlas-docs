# NexAtlas Link

- [NexAtlas Link Website](https://nexatlas.com/simulador)


## Getting Started

First, ensure that you have Node.js installed on your machine (version 20.17.0) to guarantee that the project runs correctly.

### Installing the dependencies

To install the dependencies, run the following command:

```bash
npm install
```

### Running the project

To run the project, run the following command:

```bash
npm run start
```

### Generating Executable Files, for Windows, Linux and MacOS

To generate the executable files for your Electron project, run the following command:

**- For Windows**

```bash
npm run package:windows
```

**- For Linux**

```bash
npm run package:linux
```

**- For MacOS**

```bash
npm run package:mac
```

### Executable Files

The executable files will be generated in the `release/build` folder.

**Notes**

- If you are using a Windows machine, the generated executable files will only work on Windows; the same applies for Linux and macOS.
- All the files inside `assets` folder will be copied to the final executable file. So be aware of the files that you are adding to this folder.



### Microsoft Flight Simulator 2020/24 Integration

For this integration, the SimConnect library is used to communicate with the Microsoft Flight Simulator 2020/24 SDK. A Python server built with Flask is created to run in the background, and the Electron app communicates with this server to retrieve data. The server will run on port 5975. If you want to change how this API works, feel free to update the `python-simconnect.py` file located in `assets/servers-sdk-apis/simconnect-adapter-server`. After making changes, you'll need to regenerate the executable file by running the generate-exe.py script, which will automatically update the .exe file.

**Note**: If you want to run the Python script, remember to install the `requirements.txt` from the requirements.txt file located in the same folder.

### Xplane 10 and 11

For this integration, the NASA library XPlaneConnect is used to retrieve data from X-Plane via a plugin, also using Python. The server runs in the background, and Electron acts as the client for this API, which is built with Flask. The server will run on port 4915. If you want to change how this API works, feel free to update the xplane-api-server.py file located in `assets/servers-sdk-apis/xplane-api-server`. After that, you'll need to regenerate the executable file by running the `generate-exe.py` script, which will automatically update the .exe file.



**Note**: If you want to run the python script remember to install the requirements from `requirements.txt` inside the same folder.

  