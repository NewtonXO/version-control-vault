# From any directory
Use the **application path** to execute the following command from any directory:
```
start [application_path]
```
Example:
```
$ C:\> start "C:\Program Files\Git\git-bash"
```

# From the app directory
Use the relative path to the executable:
```
$ C:\Program Files\Git> .\git-bash
```

Use the `start` command:
```
$ C:\Program Files\Git> start git-bash
```

# Add the app directory to the system PATH variable
This will allow you to run the executables in the added directory from any Command Prompt window without needing to specify the full path to the executable.

1. Run `sysmd.cpl` on CMD
2. Click on **Environment Variables**
3. Select the **Path** variable on the **System variables** section and click on **Edit**
4. Add the full path of the directory containing the executable files you want to add
5. Restart the CMD terminal
