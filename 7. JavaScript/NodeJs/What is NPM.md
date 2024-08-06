
`npm` stands for `Node Package Manager`. It's essentially a giant toolbox for `web developers`, 
especially those working with JavaScript. Here's why it's useful:

- **Pre-written Code**: Imagine not having to write every single line of code for your project. npm is a huge library of pre-written, open-source packages that provide common functionalities like routing, animations, or database interactions. You can easily integrate these packages into your project, saving you tons of time and effort.
    
- **Dependency Management**: Many of these packages rely on other packages to function. npm keeps track of these dependencies and automatically installs everything you need to run the package correctly. This saves you from manually installing a bunch of different things and ensures everything works together smoothly.
    
- **Version Control**: npm lets you specify which versions of each package you want to use in your project. This is important because updates can sometimes introduce bugs. By pinning specific versions, you can ensure your project continues to work as expected.

To use npm, you'll first need to install Node.js on your computer, as npm comes bundled with it. Once you have Node.js set up, you can use the command line to interact with npm. Here are some common npm commands:

- `npm init` - This command initializes a new project and creates a file called package. Json which lists your project's dependencies. use `-y` to set as default avoid Question.
    
- `npm install <package-name>` - This installs a specific package from the npm registry.
    
- `npm update <package-name>` - This updates a specific package to the latest version (be careful, updates can sometimes break things).
    
- `npm uninstall <package-name>` - This removes a package from your project.
-  Optional : 
	- `npm list` : to list all package that install.
    

There's a lot more to npm than this, but this should give you a basic understanding of why it's so important for JavaScript developers. There are many resources available online for learning more about npm and how to use it effectively in your projects.

# npm package locally and globally.
1. local : `npm install <package-name>`
2. global: `npm install -g <package-name>`

## package.json file ?
- npm use file <package.json> to install all package in one time. or add all package that you install it to easy for other to reinstall those package. 

