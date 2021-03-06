# Docker Images and .NET Core Content Reference

In order for Docker containers to run dotnet cli commands, the sdk that you use to build your project with locally must match the dotnet sdk version inside your container. If you want a lighter-weight container and don’t need to use the cli tools inside the container, then you can pull the runtime images.

|    Docker Images   2/07/17             |    .NET Core   Runtime version in image   |    .NET Core SDK   version in image    (NOTE: All SDK versions can target all   runtimes)    |    Full SDK   version number    |
|----------------------------------------|-------------------------------------------|----------------------------------------------------------------------------------------------|---------------------------------|
|    1.0.3-runtime                       |    1.0.3                                  |    *None                                                                                     |    *None                        |
|    1.0.3-runtime-nanoserver            |    1.0.3                                  |    *None                                                                                     |    *None                        |
|    1.0.3-runtime-deps                  |    None                                   |    *None                                                                                     |    *None                        |
|    1.0.3-sdk-projectjson               |    1.0.3                                  |    1.0.3-sdk-projectjson                                                                     |    1.0.0-preview2-003156        |
|    1.0.3-sdk-projectjson-nanoserver    |    1.0.3                                  |    1.0.3-sdk-projectjson                                                                     |    1.0.0-preview2-003156        |
|    1.0.3-sdk-msbuild-rc4               |    1.0.3, 1.1.0                           |    1.0.3-sdk-msbuild-rc4                                                                     |    1.0.0-rc4-004771             |
|    1.0.3-sdk-msbuild-rc4-nanoserver    |    1.0.3, 1.1.0                           |    1.0.3-sdk-msbuild-rc4                                                                     |    1.0.0-rc4-004771             |
|    1.1.0-runtime                       |    1.1.0                                  |    *None                                                                                     |    *None                        |
|    1.1.0-runtime-nanoserver            |    1.1.0                                  |    *None                                                                                     |    *None                        |
|    1.1.0-runtime-deps                  |    None                                   |    *None                                                                                     |    *None                        |
|    1.1.0-sdk-projectjson               |    1.1.0                                  |    1.1.0-sdk-projectjson                                                                     |    1.0.0-preview2-1-003177      |
|    1.1.0-sdk-projectjson-nanoserver    |    1.1.0                                  |    1.1.0-sdk-projectjson                                                                     |    1.0.0-preview2-1-003177      |
|    1.1.0-sdk-msbuild-rc4               |    1.0.3, 1.1.0                           |    1.1.0-sdk-msbuild                                                                         |    1.0.0-rc4-004771             |
|    1.1.0-sdk-msbuild-rc4-nanoserver    |    1.0.3, 1.1.0                           |    1.1.0-sdk-msbuild                                                                         |    1.0.0-rc4-004771             |

> **Note:** Edit your project file to target the runtime you wish to use. All SDK versions work with all runtimes though the SDK is not included in the image.

To make your project target a different runtime simply edit the `netcoreapp1.0` in your project file under the framework node. For example, with MSBuild this would be changing `<TargetFramework>netcoreapp1.0</TargetFramework>` to `<TargetFramework>netcoreapp1.1</TargetFramework>` and running `dotnet restore`.
