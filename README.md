# MonoGame Compute Fork

This fork adds modern shader features to the [MonoGame](https://github.com/MonoGame/MonoGame) framework.<br>
Nugets are available on [nuget.org](https://www.nuget.org/profiles/cpt-max).

<br>

* Compute, Tessellation, and Geometry Shaders for DirectX and OpenGL
* Structured Buffers for all Shader Stages (including Append and Consume)
* Write directly to Textures or Vertex/Index Buffers from a Compute Shader
* Write directly to Textures and Buffers from Pixel Shaders (DirectX only for now)
* New Shader Compiler based on [ShaderConductor](https://github.com/cpt-max/ShaderConductor) for DesktopGL, as a replacement for MojoShader
* Shader Model 4 and 5 support not only for DirectX, but also for DesktopGL
* Compile Shaders natively on Linux without Wine
* Support for Integer Surface Formats (can be used for per-pixel atomic operations)
* Support for uint Shader Parameters
* Indirect Draw and Indirect Compute (see [Compute Shader Guide](https://github.com/cpt-max/Docs/blob/master/MonoGame%20Compute%20Shader%20Guide.md#indirect-drawing))
* Vertex Texture Fetch also for DesktopGL
* CopyData functions for Textures and Buffers to copy data from one resource to another on the GPU without a shader

<br>
  
* [Shader Samples](https://github.com/cpt-max/MonoGame-Shader-Samples/tree/overview)<br>
* [Compute Shader Guide](https://github.com/cpt-max/Docs/blob/master/MonoGame%20Compute%20Shader%20Guide.md)<br>
* [Build Requirements](https://github.com/cpt-max/Docs/blob/master/Build%20Requirements.md)<br>
* [Shader Migration Guide for OpenGL](https://github.com/cpt-max/Docs/blob/master/Migrating%20shaders%20to%20ShaderConductor.md)<br>
* [Shader Model Support for OpenGL](https://github.com/cpt-max/Docs/blob/master/Shader%20models%20for%20OpenGL.md)<br>
* [Pull Request](https://github.com/MonoGame/MonoGame/pull/7533)<br>

<br>

# MonoGame

MonoGame is a simple and powerful .NET framework for creating games for desktop PCs, video game consoles, and mobile devices using the C# programming language. It has been successfully used to create games such as [Streets of Rage 4](https://store.steampowered.com/app/985890/Streets_of_Rage_4/), [Carrion](https://store.steampowered.com/app/953490/CARRION/), [Celeste](https://store.steampowered.com/app/504230/Celeste/), [Stardew Valley](https://store.steampowered.com/app/413150/Stardew_Valley/), and [many others](https://monogame.net/showcase/).

It is an open-source re-implementation of the discontinued [Microsoft's XNA Framework](https://msdn.microsoft.com/en-us/library/bb200104.aspx).

[![Join the chat at https://discord.gg/monogame](https://img.shields.io/discord/355231098122272778?color=%237289DA&label=MonoGame&logo=discord&logoColor=white)](https://discord.gg/monogame)

* [Build Status](#build-status)
* [Supported Platforms](#supported-platforms)
* [Support and Contributions](#support-and-contributions)
* [Source Code](#source-code)
* [Helpful Links](#helpful-links)
* [License](#license)

## Build Status

We use [GitHub Actions](https://github.com/MonoGame/MonoGame/actions) to automate builds and packages distribution of the latest MonoGame changes. We also rely on a [build server](http://teamcity.monogame.net/?guest=1) to run tests in order to avoid regressions. The table below shows the current build status for the ```develop``` branch.

| Name | Status |
|:---- | ------ |
| Builds | [![Build](https://github.com/MonoGame/MonoGame/actions/workflows/main.yml/badge.svg?branch=develop)](https://github.com/MonoGame/MonoGame/actions/workflows/main.yml) |

## Supported Platforms

We support a growing list of platforms across the desktop, mobile, and console space. If there is a platform we don't support, please [make a request](https://github.com/MonoGame/MonoGame/issues) or [come help us](CONTRIBUTING.md) add it.

* Desktop PCs
  * Windows 8.1 and up (OpenGL & DirectX)
  * Windows Store Apps (UWP)
  * Linux (OpenGL)
  * macOS 10.15 and up (OpenGL)
* Mobile/Tablet Devices
  * Android 6.0 and up (OpenGL)
  * iPhone/iPad 10.0 and up (OpenGL)
* Consoles (for registered developers)
  * PlayStation 4
  * PlayStation 5
  * Xbox One (both UWP and XDK)
  * Nintendo Switch
  * Google Stadia

## Support and Contributions

If you think you have found a bug or have a feature request, use our [issue tracker](https://github.com/MonoGame/MonoGame/issues). Before opening a new issue, please search to see if your problem has already been reported. Try to be as detailed as possible in your issue reports.

If you need help using MonoGame or have other questions we suggest you post on our [community forums](http://community.monogame.net). Please do not use the GitHub issue tracker for personal support requests.

If you are interested in contributing fixes or features to MonoGame, please read our [contributors guide](CONTRIBUTING.md) first.

### Subscription

If you'd like to help the project by supporting us financially, consider supporting us via a subscription for the price of a monthly coffee.

Money goes towards hosting, new hardware and if enough people subscribe a dedicated developer.

There are several options on our [Donation Page](https://monogame.net/donate/).

## Source Code

The full source code is available here from GitHub:

* Clone the source: `git clone https://github.com/MonoGame/MonoGame.git`
* Set up the submodules: `git submodule update --init`
* Open the solution for your target platform to build the game framework.
* Open the Tools solution for your development platform to build the pipeline and content tools.

For the prerequisites for building from source, please look at the [Requirements](REQUIREMENTS.md) file.

A high level breakdown of the components of the framework:

* The game framework is found in [MonoGame.Framework](MonoGame.Framework).
* The content pipeline is located in [MonoGame.Framework.Content.Pipeline](MonoGame.Framework.Content.Pipeline).
* Project templates are in [Templates](Templates).
* See [Tests](Tests) for the framework unit tests.
* See [Tools/Tests](Tools/MonoGame.Tools.Tests) for the content pipeline and other tool tests.
* [mgcb](Tools/MonoGame.Content.Builder) is the command line tool for content processing.
* [mgfxc](Tools/MonoGame.Effect.Compiler) is the command line effect compiler tool.
* The [mgcb-editor](Tools/MonoGame.Content.Builder.Editor) tool is a GUI frontend for content processing.

## Helpful Links

* The official website is [monogame.net](http://www.monogame.net).
* Our [issue tracker](https://github.com/MonoGame/MonoGame/issues) is on GitHub.
* Use our [community forums](http://community.monogame.net/) for support questions.
* You can [join the Discord server](https://discord.gg/monogame) and chat live with the core developers and other users.
* The [official documentation](https://monogame.net/articles/index.html) is on our website.
* Download [release](https://github.com/MonoGame/MonoGame/releases) and [development](https://github.com/orgs/MonoGame/packages) packages.
* Follow [@MonoGameTeam](https://twitter.com/monogameteam) on Twitter.

## License

The MonoGame project is under the [Microsoft Public License](https://opensource.org/licenses/MS-PL) except for a few portions of the code. See the [LICENSE.txt](LICENSE.txt) file for more details. Third-party libraries used by MonoGame are under their own licenses. Please refer to those libraries for details on the license they use.
