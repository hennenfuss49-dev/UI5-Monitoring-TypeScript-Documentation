# Default Controls

Controls are used to define appearance and behavior of parts of the screen.  
It's time to build the first little UI by using the UI5 control `sap/m/Text`.

---

#### Preview:

![](https://sdk.openui5.org/docs/topics/loio30a42d381b9e4388bf7fdc0b941e5381_LowRes.png "The \"Hello World\" text is now displayed by a OpenUI5 control")

---

#### Coding:

In order to display any Control, you need to first create an instance of the Control that you want to display.  
You can pass any the controls options as a TypeScript object to constructor. These options can contain properties, aggregations, events, etc...  
In our case, we want the text control to display the message "Hello World", thus we set the `text`-property accordingly  

To place any control on the screen, you have to chain the constructor with the `placeAt` method. This method is used to position UI5 controls. In the parameters of the `placeAt` method, you can tell UI5, where to put the control. For the following code snipped, we tell UI5 to add the control to the DOM element with the ID of `content`.

```ts
import Text from "sap/m/Text";

new Text({
    text: "Hello World"
}).placeAt("content");
```

All controls of UI5 have a fixed set of properties, aggregations, and associations for configuration. You can find their descriptions in the *[API reference](https://sapui5.hana.ondemand.com/#/api)*. In addition, each control comes with a set of public functions that you can look up in the *[API reference](https://sapui5.hana.ondemand.com/#/api)* as well.  
For a quick check of a control and comfort, you can install the *[VSCode UI5: API Reference](https://marketplace.visualstudio.com/items?itemName=jacek-wozniczak.vscode-ui5-api-reference)* plugin, to quickly look up the properties, functions, aggregations, etc. a control might have.

> 📌 Important:
> Only instances of `sap.ui.core.Control` or their subclasses can be rendered stand-alone and have a `placeAt` function. Each control extends `sap.ui.core.Element` that can only be rendered inside controls. Check the *[API reference](https://sapui5.hana.ondemand.com/#/api)* to learn more about the inheritance hierachy of controls. The API Documentation of each control refers to the directly known subclasses.