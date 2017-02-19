Getting started, from official web site https://www.microsoft.com/net/core#macos

- Install openssl
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/

- Install latest dotnet core sdk https://github.com/dotnet/core/blob/master/release-notes/
By the time of this writing, the lastest was https://github.com/dotnet/core/blob/master/release-notes/rc4-download.md

- Install VS Code

- Install nodejs, npm

- Install yeoman for app scaffolding
- Install aspnet core generator (https://www.npmjs.com/package/generator-aspnet)
```
npm install -g yo generator-aspnet@0.3.1
yo aspnet
```

```
cd webapp
dotnet restore
dotnet build
```
if you see an error message like:
warn : The folder '<path>/projFolder' does not contain a project to restore.
This happens maybe because you don't have a dotnet sdk version that can read .csproj files (until Preview 2.1 it searches for project.json file)


