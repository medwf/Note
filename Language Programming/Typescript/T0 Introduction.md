# Typescript ?
- Typescript is JavaScript with added syntax for types.

# Install compiler .
1. Within your npm project, run the following command to install the compiler:
	- npm install typescript --save-dev # using typescript in development mode.
	
2. Which should give you an output similar to:
	- added 1 package, and audited 2 packages in 2s  
	- found 0 vulnerabilities

3. The compiler is installed in the `node_modules` directory and can be run with: `npx tsc`.
	- `npx tsc`
	-  Which should give you an output similar to:
		- Version 4.5.5  
		- tsc: The Typescript Compiler - Version 4.5.5

- Followed by a list of all the Common Commands.

# Configuring the compiler
- By default the Typescript compiler will print a help message when run in an empty project.
- The compiler can be configured using a `tsconfig.json` file.

- You can have Typescript create `tsconfig.json` with the recommended settings with:
	- `npx tsc --init`

Which should give you an output similar to:

Created a new tsconfig.json with:  
TS  
  target: es2016  
  module: commonjs  
  strict: true  
  esModuleInterop: true  
  skipLibCheck: true  
  forceConsistentCasingInFileNames: true  
  
You can learn more at https://aka.ms/tsconfig.json

Here is an example of more things you could add to the `tsconfig.json` file:
``` typescript
{  
  "include": ["src"],  
  "compilerOptions": {  
    "outDir": "./build"  
  }
}
```

You can open the file in an editor to add those options. This will configure the TypeScript compiler to transpile TypeScript files located in the `src/` directory of your project, into JavaScript files in the `build/` directory.