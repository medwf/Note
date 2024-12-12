Tar : tar -xvzf jdk-21_linux-x64_bin.tar.gz # extract file

To create a `.tar.gz` archive, you can use the `tar` command. Here’s how to do it:

2. **Create the `.tar.gz` Archive**: Use the `tar` command with the `-czvf` options to create a compressed `.tar.gz` file.

   ```bash

   tar -czvf jdk-21.tar.gz jdk-21

   ```

   - `-c`: Create a new archive.

   - `-z`: Compress the archive with gzip.

   - `-v`: Show the progress in the terminal.

   - `-f`: Specify the filename for the archive.

3. **Verify the Archive**: You should now have a file named `jdk-21.tar.gz` in your current directory. To list its contents and verify it was created correctly, you can run:

   ```bash

   tar -tf jdk-21.tar.gz

   ```

This will display the list of files inside the archive, confirming that it was created successfully.