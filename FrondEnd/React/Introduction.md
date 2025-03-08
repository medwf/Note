# introduction
- `React` : 
	- it's a library helps to build frontend.
	-  build by Facebook.

 ## Setup and Installation
There are a few ways to set up React, and I'll show you two so you get a good idea of how it works.

###  Vite:

#### Init project react with vite:
```bash
npm create vite@latest my-react-app --template react
cd my-react-app
npm install
npm run dev
```

#### Adding dependency babel to project:
``` Shell
npm install --save-dev @babel/core @babel/preset-env @vitejs/plugin-react
# Update Vite Configuration: Modify your vite.config.js to include the Babel plugin:

import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';
export default defineConfig({  
        plugins: [react({  
            babel: {  
                presets: ['@babel/preset-env']  
            }  
        })]  
    });
```

###  Webpack:
```SHELL
npm install -g create-react-app
npx create-react-app my-react-app
cd my-react-app
npm start
```
