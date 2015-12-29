## Exploring MyPlugin

Let's take a look at getting started with actually seeing where you can write code for your plugin using the BuildFire SDK. We will start by just opening the areas of the app and making sure we see the "Hello World" placed in the widget and figure out the areas we will be using mostly.

### The Developer Dashboard

When you run the <code>index.html</code> in pluginTester, you will see two main sections of the Developer Dashboard:

#### 1. The Control
The control is where you have the different types of settings and configuration for the plugin.

There are three possible areas for the control:

##### a. Content

##### b. Design

##### c. Settings

It is up to you as the plugin creator, to decide how best to have these configurations organized. You can choose to remove or activate these three sections depending on the type of plugin you are creating.

For example: BuildFire's text plugin only has the "content" area of the configuration enabled as there are not really "settings" or "design" changes you can make to it. It is just about adding the content to the plugin.

Conversely, the media center plugin does have the "design" area enabled as we have several different choices on how to display the data.

These decisions are really a judgement call on your part as to which of the areas you utilize to have as your app configuration. You can make those changes in the <code>plugin.json</code>, which we will touch on a little later in this post

#### 2. The Emulator
The emulator is the preview or 'display' of your plugin and can be updated by the control. Ideally, as your users make changes in the control, the emulator will update to show the changes they have made. You could either do this with a button, or an <code>onUpdate</code> handler.

### The SDK Plugin Folder (../BuildFireSDK/myPlugin)

We have already looked at this folder a little bit in past posts, but let's dive a bit deeper this time. 

#### 1. The Control Folder
The control folder dictates what the user sees on the left-hand side of the dashboard. Using this, the user will configure their unique plugin instance of the plugin you have created. The Control area of the app can have three sections; Content, Design, or Settings. You will find all three corresponding directories in this folder. For each area you use, you will need to write the template for the <code>index.html</code> of that directory.

#### 2. The Resources Folder
The Resource Folder is only for the default plugin icon and default image you may want in the plugin. This folder will not carry over any other resources for the plugin when it is submitted. **Note:** If you do need to add other resources to the plugin which *should* be included when the plugin is submitted, the correct place to do this is in the **Widget folder** or **Control folder**. The resources cannot be shared betweeen the widget and control folders, so it is important to include the resources you need in the correct folder. 

#### 3. The Widget Folder
The widget folder is the actual functionality of the plugin which will live in the app. It displays the configuration of the plugin instance in the emulator on the right hand side of the dashboard and it is also what will actually be seen in the app. 

### 'Plugin.json' file
This file is where you can configure the plugin. It is similar to the <code>package.json</code> file for an npm package or a <code>.gemspec</code> file for bundler. You will have the option to enable or disable the different areas of the control in this file. You will also add the details for the plugin like the author's name, the plugin name, the languages your plugin uses, and features of the plugin.

### Wrapping Up...
This is a basic overview of the different areas of the SDK. To dive further into the SDK, you can always check out the other posts or the [wiki](https://github.com/BuildFire/sdk/wiki) on github.
