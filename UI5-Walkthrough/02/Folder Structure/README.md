# UI5 folder structure and important files

Its time to talk about the folder structure and some important files, that you often need to modify for various reasons. UI5 uses a very specific folder structure.

---

#### Folder structure

Starting with the namespace as a project root: You can define it when creating a new UI5-TypeScript project.  
Below that we have the `webapp` folder: Within that folder, there are the most important things for your app, such as the view, controller, etc.  

Despite the importance of the `webapp` folder, there are 3 files that we need to cover first: The `package.json`, `ui5-dist.yaml` and the `ui5.yaml` files.

### `package.json`:
The reason why I mention the `package.json` is, that, you can configure all kinds of npm stuff e.g. the scripts that are being executed when you, for example, type `npm run start` into the terminal. On top of that, it might also become important when you start adding npm dependencies, since they are referenced there. This is important when you run `npm install`, so taht every dependency that should be installed, gets installed.

### `ui5.yaml` and `ui5-dist.yaml`
These two files come into play, once you add more namespaces in your XML-files or your need to configure your connection to the backend of your application. If you add new namespace in your XML e.g. `xmlns:f="sap.f"` it might happen that UI5, can't load the components within that namespace. This is because, they are not defined under the `libraries` section in the `ui5.yaml` as well as the `ui5-dist.yaml`. The backend of your application needs to be configured under the `server` section of those files.

Now let's move on to the `webapp` folder.

### `control`
Inside the `control` folder, you put your custom controls. More information about custom controls, can be found in the according section of the Documentation.

### `controller`
This is a important folder. Inside of the `controller` folder, there are the controller's for the XML views.  
These files have a special naming: ___controllerName___`.controller.ts`

### `i18n`
Inside the `i18n` folder there are files for different languages

### `view`
This is the folder, which the XML-files lie within. These files also follow a naming convention: ___viewName___`.view.xml`

### `manifest.json`
This is one of the most important files. Inside of it, you can configure things like datasources, models, custom-css, routing, etc.

```
project_namespace
└───webapp
│   │   control
│   │   controller
│   │   css
│   |   i18n
|   |   model
|   |   test
|   |   view
|   |   
|   |   index.html
|   |   manifest.json
|      
|   package.json
│   ui5-dist.yaml
└   ui5.yaml
```