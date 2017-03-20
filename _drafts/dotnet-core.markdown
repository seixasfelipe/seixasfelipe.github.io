---
layout: post
title:  ".NET Core on MacOS"
date:   2017-02-18 23:02:08 -0400
categories: programming dotnet 
---
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
Follow steps of yeoman aspnet generator

```
cd webapp
dotnet restore
dotnet build
dotnet run
```
if you see an error message like:
warn : The folder '<path>/projFolder' does not contain a project to restore.
This happens maybe because you don't have a dotnet sdk version that can read .csproj files (until Preview 2.1 it searches for project.json file)
ref: http://stackoverflow.com/questions/42011846/new-dotnet-core-project-cannot-restore?answertab=active#tab-top

On MacOS, the dotnet sdk is installed in:
```
$ l /usr/local/share/dotnet/sdk/
```

Tutorials
- Your first mac aspnet core applicaton (https://docs.microsoft.com/en-us/aspnet/core/tutorials/your-first-mac-aspnet)



If you want to migrate from DNX to .NET Core CLI
- Explain what .NET Core CLI is.
- Explain diff between DNX and .NET Core CLI.
ref: https://docs.microsoft.com/en-us/dotnet/articles/core/migrating-from-dnx

In my case, my project uses RC1 and many things has changed once RC2 was released (e.g. EntityFramework 7 was renamed to EntityFramework Core).
ref: https://docs.microsoft.com/en-us/ef/core/miscellaneous/rc1-rc2-upgrade

Explain differences between .NET Core versions.
ref: http://blog.tpcware.com/2016/12/multiple-versions-of-net-core-runtimes-and-sdk-tools-sxs-survive-guide/

Problem with System.Net.Mail namespace. It was ported to .NET Core 
https://github.com/dotnet/corefx/tree/master/src/System.Net.Mail
