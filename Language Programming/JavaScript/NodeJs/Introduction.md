# what is NodeJS ?
Node.js is a `JavaScript runtime environment` that allows you to run JavaScript code outside of a web browser. This means you can use JavaScript to build server-side applications and tools.

Here are three ways to install Node.js on Ubuntu 22.04 LTS:

**1. Using the Ubuntu Repositories (Simple and Straightforward):**

This method is the simplest and most straightforward way to install Node.js. However, it may not provide you with the latest version.

- First, update your package lists:

``` Bash
sudo apt update
```

- Install Node.js and npm (Node Package Manager, which comes bundled with Node.js) using the following command:

``` bash
sudo apt install nodejs
```

- Verify the installation by checking the Node.js and npm versions:

``` bash
node -v
npm -v
```

**2. Using NodeSource Repository (For Specific Node.js Versions):**

This method allows you to install a specific version of Node.js from the NodeSource repository.

- Add the NodeSource repository key for the desired Node.js version (check the NodeSource website for available versions [https://nodesource.com/](https://nodesource.com/)). Replace `<version>` with the desired version (e.g., 18.x):

``` shell
curl -sL https://deb.nodesource.com/setup_<version>.x | sudo -E bash -
```

- Update your package lists again:

``` shell 
sudo apt update
```

- Install Node.js and npm:

``` shell 
sudo apt install nodejs
```

- Verify the installation as mentioned in method 1.

**3. Using Node Version Manager (NVM) (For Managing Multiple Node.js Versions):**

`NVM` allows you to `install and manage multiple versions of Node.js on your system`. This can be useful if you need to work on projects that require different Node.js versions.

- Follow the instructions on the official NVM website to install it [https://gist.github.com/llccing/9467ebbdb93466d790713ef12c2afe85](https://gist.github.com/llccing/9467ebbdb93466d790713ef12c2afe85)
- Verify the installation by running the following commands after completing the NVM setup steps mentioned on the website:

``` shell
nvm ls-remote   # Lists available Node.js versions
nvm install node  # Installs the latest LTS version
nvm use node     # Switches to the installed version
node -v          # Verify Node.js version
```

Remember to choose the method that best suits your needs. If you're new to Node.js, the Ubuntu repository method (method 1) is a good starting point. If you need a specific version or want to manage multiple versions, consider using NVM (method 3).
