# StinkyEngine
StinkyEngine is a semi-lowend game engine. It has a very powerful entity/Ui hybrid ECS. It will take seconds to create your custom entities. StinkyEngine has a full set of systems to make game making easier & not be forced to be done in a certain way but gives freedom on how you should use those systems.

_**I haven't uploaded StinkyEngine to GitHub yet but can still try out our Framework here:**_ [StinkyEngine Package](https://www.nuget.org/packages/StinkyEngine)

I haven't uploaded StinkyEngine to GitHub yet but can still try out our Framework here: StinkyEngine Package

> # To create a new Project?

1. Create a Console app OR create a monogame project.
2. If you created a monogame project, remove "MonoGame.Framework.DesktopGL" package and add StinkyEngine instead, and skip step 3.
3. Since monogame changed how content manager is handled, this step is required. Create a folder, in your project, called ".config". Inside that folder, create a file called "dotnet-tools.json". Copy the following code:

```
{
	"version": 1,
	"isRoot": true,
	"tools": {
	  "dotnet-mgcb": {
		"version": "3.8.1.303",
		"commands": [
		  "mgcb"
		]
	  },
	  "dotnet-mgcb-editor": {
		"version": "3.8.1.303",
		"commands": [
		  "mgcb-editor"
		]
	  },
	  "dotnet-mgcb-editor-linux": {
		"version": "3.8.1.303",
		"commands": [
		  "mgcb-editor-linux"
		]
	  },
	  "dotnet-mgcb-editor-windows": {
		"version": "3.8.1.303",
		"commands": [
		  "mgcb-editor-windows"
		]
	  },
	  "dotnet-mgcb-editor-mac": {
		"version": "3.8.1.303",
		"commands": [
		  "mgcb-editor-mac"
		]
	  }
	}
  }
```

 4. Change your program.cs run method to this:
```
using var game = new Engine(new());

game.Run();
```

5. (optional) Inside program.cs, the engine has a ton of options for starting your first scene, viewport size, window size, so on. Optionally, can tell the engine settings, what scene should start when the engine is finishing loading its content.

To tell the engine what scene to load, add the following "scene" to your engine settings below:
```
using var game = new Engine(new()
{
	scene = new BootScene()
});

game.Run();
```
