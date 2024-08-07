# XML Views

Now, its time to start using XML to display our controls, instead of using TypeScript.  

When working with UI5, its recommended to use XML views, as this produces the most readable code and will force your to separate the view declaration from the controller logic. Yet the look our UI will not change.

---

#### Preview:

![](https://sdk.openui5.org/docs/topics/loio30a42d381b9e4388bf7fdc0b941e5381_LowRes.png "The \"Hello World\" text is now displayed by a OpenUI5 control")

---

#### Coding

#### webapp/view/App.view.xml
As you learn in the previous section, views should be put into the `view` folder. Inside the `view` folder, you now need to create a file called `App.view.xml`. In UI5, the root node of an XML view is the `<mvc:View>` tag. To use this tag, you need to declare the XML namespace mvc, which corresponds to the `sap.ui.core.mvc` namespace. This namespace provides classes for creating and working with views and other _Model-View_Controller_ (MVC) assets. Additionally, you need to declare the default XML namespace to the `sap.m` namespace. This namespace contains the majorty of UI5's UI assets, including the `Text` control that you have to use with your view.   

Please keep in mind, as mentioned in the previous section, that you might need to add a newly added namespace in the `ui5.yaml` as well as the `ui5-dist.yaml` file under the libraries section.

Inside the `<mvc:View>` tag, you need to add the `<Text>` tag from the default XML namespace. This `<Text>` tag represents the text control that will be displayed on the view. You need to set the `text` attribute to "Hello World". This will display the text "Hello World" on the view.

```xml
<mvc:View
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Text text="Hello World"/>
</mvc:View>
```
>💡 Tip:
 XML tags are mapped to UI controls, and attributes are mapped to the properties of the control. In this case, the `<Text>` tag represents the `Text` control in the `sap.m` library, and the `text` attribute sets the `text` property of the control.

> 📝 Note:
The namespace identifies all resources of the project and has to be unique. If you develop your own application code or library, you cannot use the namespace prefix `sap`, because this namespace is reserved for SAP resources. Instead, simply define your own unique namespace (for example, `myCompany.myApp`).