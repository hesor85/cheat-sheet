# Development
This describes what you need to do to when everything is set up correctly and you need to continue development of the application that both needs to change the Angular web client and the NodeJS web server.

In this case you need 3 terminals:
1. One running the web server and watches for changes. This is also where you can see console.log output.
2. One running the Angular web client and watches for changes.
3. One where you can run commands, for example to use the Angular CLI to generate new components and services.

| Command            | Description                                                                                                          | Where to run                                                             | Prerequisites                   |
|--------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|---------------------------------|
| `nodemon server.js` | Runs the server where server.js is the server file name and restarts the server automatically when changes are made. | In the server folder where your server file is located.                  | Must have nodemon installed     |
| `npm run watch` | Builds the Angular web client in a way where it can be served by your web server and rebuilds when changes are made. | In the Angular web client folder where the package.json file is located. | Must have Angular CLI installed |

# Angular CLI
The Angular CLI can be used to create new Angular projects and to generate new components and services.

| Command                                      | Description                                                                                                                                                                                                                                                             | Example                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| `ng new <project-name> --prefix <your-prefix>` | Creates a new Angular application with a default component. The --prefix option is optional but ensures that all your components will be prefixed with whatever you want. This makes it easier to distinguish your own components from components from other libraries. | `ng new todo-list --prefix abp` |
| `ng g c <component-name>`                      | Creates a new Angular component                                                                                                                                                                                                                                         | `ng g c searchComponent`        |
| `ng g s <service-name>`                        | Create a new Angular service. Per default the service can be injected anywhere.                                                                                                                                                                                         | `ng g s dataService`             |
# Install stuff
This assumes that you are at a point where you have already installed NPM/NodeJS, Angular CLI, and Git
| Command                  | Description                                                                                                 |
|--------------------------|-------------------------------------------------------------------------------------------------------------|
| `npm install -g nodemon` | Installs nodemon globally so it can be used anywhere to start and watch for changes in NodeJS Applications. |

# Guidelines
1. Avoid file/folder names with spaces or special characters (including æ, ø, and å)
2. It is better to create many small Angular components with a limited, but well-defined responsibility. This both helps maintenance, testability, collaboration, debugging, and resuseability.
3. Move code that is not related to showing stuff from components into services. This also helps separating concerns and increases maintenance, testability, collaboration, debugging, and reusability.