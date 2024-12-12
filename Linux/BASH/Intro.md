Syntax of if else :

In Bash scripts, the syntax for the `if-else` construct is as follows:

```bash

if [ condition ]; then

    # Code to be executed if the condition is true

else

    # Code to be executed if the condition is false

fi

```

Here's an example using a variable as a condition:

```bash

#!/bin/bash

# Example variable

age=20

if [ "$age" -ge 18 ]; then

    echo "You are an adult."

else

    echo "You are a minor."

fi

```

In this example, the condition `[ "$age" -ge 18 ]` checks if the value of the variable `age` is greater than or equal to 18.

Here are some commonly used flags within the square brackets `[ ]` for conditional expressions in Bash:

- `-eq`: Equal

- `-ne`: Not equal

- `-gt`: Greater than

- `-lt`: Less than

- `-ge`: Greater than or equal to

- `-le`: Less than or equal to

Here's a quick reference to their meanings:

- `a -eq b`: True if a is equal to b.

- `a -ne b`: True if a is not equal to b.

- `a -gt b`: True if a is greater than b.

- `a -lt b`: True if a is less than b.

- `a -ge b`: True if a is greater than or equal to b.

- `a -le b`: True if a is less than or equal to b.

Remember to use proper quoting around variables (`"$variable"`) to avoid issues with spaces or empty variables.