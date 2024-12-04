Run Tiled Map Editor in GitHub Codespaces
This repository provides instructions to set up and run Tiled Map Editor in GitHub Codespaces as a web app. Tiled is an open-source, flexible, and powerful map editor for creating tile-based maps for games. By following these instructions, you can run Tiled directly in the browser via WebAssembly.

Prerequisites
GitHub Account: You need a GitHub account to use GitHub Codespaces.

GitHub Codespaces: This setup is designed to be used with GitHub Codespaces.

# Steps:
Follow these instructions to build and run Tiled in GitHub Codespaces:

## 1. Create a New GitHub Repository
Go to GitHub and create a new repository where you want to configure the Codespace.

## 3. Set Up Your GitHub Codespace
Open your newly created repository on GitHub.

Click the Code button and select Open with Codespaces.
Create a new Codespace. This will set up a cloud-based development environment.

## 5. Install Dependencies
To build Tiled from source, you’ll need to install some required dependencies. Run the following commands in the Codespaces terminal:

```
sudo apt update
sudo apt install build-essential cmake qt5-qmake qtbase5-dev qtchooser qt5-qmake-bin qtbase5-dev-tools
These packages are necessary for building Tiled with Qt5.

```

## 4. Clone the Tiled Repository
Clone the Tiled source code from GitHub:

```
git clone https://github.com/mapeditor/tiled.git
cd tiled
```

## 5. Build Tiled for WebAssembly (WASM)
To run Tiled in the browser, you’ll need to compile it using Emscripten.

### Install Emscripten:

```
sudo apt install emscripten
```

### Configure and Build Tiled for WebAssembly:

Run the following commands to configure the build system and compile Tiled for the web:

```
emcmake cmake .
emmake make
```

This will compile the Tiled Map Editor into a WebAssembly-compatible version.

## 6. Serve Tiled as a Web App
After building Tiled for WebAssembly, you need to serve it via a simple HTTP server. Follow these steps:

Install HTTP Server:

```
npm install -g http-server
```

### Start the HTTP Server (You can use any port of your choice!):
```
http-server -p 8080
This will make Tiled accessible in the browser.

```
### Navigate to the directory where Tiled was built and run the following command to start the server on port 8080:

```
npm install -g http-server

```

## 7. Access Tiled in Your Browser
Once the server is running, open the following URL in your browser to access the Tiled Map Editor:


```
https://<your-codespace-url>/8080
Replace <your-codespace-url> with the actual URL provided by GitHub Codespaces.

```

## 8. Work on Your Maps
You can now start designing tile-based maps directly in the browser using Tiled. The maps can be exported as JSON or XML files and used in whatever you want to do with it.

# Notes
Performance: Running Tiled in GitHub Codespaces may not be as fast as running it locally, especially for large projects.
Persistence: GitHub Codespaces is an ephemeral environment. Make sure to commit and push your changes to GitHub if you want to save your work. You could also use VSCode or any other IDE and Code Editor of your choice.


Happy Tile Making!


# License
This project is licensed under the UNILICENSE. You can freely modify, distribute, and use the software for any purpose, without any warranty.
