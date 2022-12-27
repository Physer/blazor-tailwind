# blazor-tailwind

## Introduction
This project is a small example application that showcases the use of Tailwind CSS with .NET's Blazor (WASM).

## How it works
Since we're using .NET and Blazor, we won't be using NodeJS or NPM.
This means that we prefer to use [the standalone Tailwind CSS CLI](https://tailwindcss.com/blog/standalone-cli).

This CLI can run Tailwind CSS commands without leveraging NodeJS or NPM.

Additionally, an MSBuild action has been created which runs on project build.
This action will execute a Tailwind command to build and minify the CSS from the input `app.css` in the `~/wwwroot/css` folder.

After building the project, a new file called `output.css` is created/updated in the `~/wwwroot/css` folder.

This `output.css` file is linked in the `index.html` file as a stylesheet.

To summarize:
1. The Tailwind CLI is used as a standalone alternative to NodeJS/NPM
2. The CLI uses JIT compilation (by default) to generate the necessary CSS based on any `.razor`, `.html` and `.cshtml` files in the repository
3. Using MSBuild, the previously mentioned CLI step is executed on-build of the project
4. The generated CSS file is linked as a stylesheet
5. Presto, manifesto you've got your Tailwind experience in a Blazor application!

Note: any other installation requirements following [the installation in the getting started guide](https://tailwindcss.com/docs/installation) are also required and have been executed.

## Running the application
Since the application is a Blazor WASM (WebAssembly) application, there is currently no Docker support available yet.
This might be added at a later time.

For now, run the .NET application through the .NET CLI or Visual Studio.

Run the following commands in the root folder of this repository:
```
dotnet build
dotnet run
```

At a later time, instructions for publishing and hosting the app will be added to the README.

## Limitations
* At this point in time, only Windows is supported.
* The Tailwind CSS CLI has to be updated manually
