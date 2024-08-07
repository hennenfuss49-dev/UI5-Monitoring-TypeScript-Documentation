# Controllers
In this section, you will learn how to replace the text with a button and show the "Hello World" message when the button is pressed. The handling of the button's `press` event is implemented in the controller of the view.

---

#### Preview


![](https://sdk.openui5.org/docs/topics/loiocedfdf89b30643ddbfcab1fe50bfa892_LowRes.png "A Say Hello button is added")

#### Coding

#### webapp/controller/App.controller.ts

First of all, you need a controller for your app view that defines how the view should react to user inputs, such as a button press event.

You define the app controller in its own file by extending the `BaseController` which should have been generated for you already. In the beginning, it holds only a single function called `onShowHello` that shows an alert with the static text "Hello World". Kepp in mind that you also need to define the namespace of your own controller by using the `@namespace`.

```ts
import BaseController from "./BaseController";

/**
 * @namespace example.namespace.controller
 */

export default class AppController extends BaseController {
    onShowHello(): void {
        // show a native JavaScript alert
        alert("Hello World");
    }
};
```

---

#### webapp/view/App.view.xml

To connect your controller with the view, you need to specify the name of your controller in the `controllerName` attribute of the root node. This allows you to access the event handlers and other functionalites defined in the controller. The name should be a module path, which is the location of the controller file.

In addition, you replace the `<text>` tag with a `<button>` tag. We set the `<text>` attribute of the button to the static value "Say Hello" and assign the `onShowHello` event from our app controller to the `press` attribute of the button. To indicate that the press event handler is located in the controller of the view and not in the global namespace, we prefix the handler name with a dot(`.`) character.

```xml
<mvc:View
   controllerName="ui5.walkthrough.controller.App"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Button
      text="Say Hello"
      press=".onShowHello"/>
</mvc:View>
```

A view does not necessarily need an explicitly assigned controller. You do not have to create a controller if the view is just displaying information and no additional functionality is required. If a controller is specified, it is instantiated after the view is loaded.

---

#### Conventions
 - Controller names are capitalized

 - All controllers are stored in the `controller` folder

 - Controllers carry the same name as the related view (if there is a 1:1 relationship)

 - Event handlers are prefixed with `on`

 - Controller names always end with `*.controller.ts`