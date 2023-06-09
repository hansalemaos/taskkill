# terminating processes on Windows using the taskkill command

## Tested against Windows 10 / Python 3.10 / Anaconda 

### pip install taskkill

taskkill is a Python library that provides utility functions for terminating processes on Windows using the taskkill command. It allows users to easily kill processes by PID, terminate processes along with their child processes, and perform forceful termination if necessary. The library also includes a regex-based search function to find and terminate processes based on specific criteria such as window title, window text, class name, and process path.

### Features

- Kill processes by PID
- Terminate processes along with their child processes
- Forcefully terminate processes
- Search and terminate processes using regex-based criteria
- Dry run option to preview processes without actually terminating them 



```python

from taskkill import taskkill_pid, taskkill_pid_children, taskkill_force_pid, taskkill_force_pid_children, taskkill_regex_rearch

# Kill processes by PID
results = taskkill_pid(pids=(1234, 5678))

# Terminate processes along with their child processes
results = taskkill_pid_children(pids=(1234, 5678))

# Forcefully terminate processes
results = taskkill_force_pid(pids=(1234, 5678))

# Forcefully terminate processes along with their child processes
results = taskkill_force_pid_children(pids=(1234, 5678))

# Search and terminate processes using regex-based criteria
results = taskkill_regex_rearch(
    dryrun=False,
    kill_children=True,
    force_kill=True,
    title=r"\bnotepad$",
    windowtext=".*",
    class_name=".*",
    path="notepad.exe$",
)

# Dry run - Preview processes without terminating them
taskkill_regex_rearch(
    dryrun=True,
    kill_children=True,
    force_kill=True,
    title=r"\bnotepad$",
    flags_title=re.I,
    windowtext=".*",
    flags_windowtext=re.I,
    class_name=".*",
    flags_class_name=re.I,
    path="notepad.exe$",
    flags_path=re.I,
)
```

Contribution
Contributions are welcome! If you encounter any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request on the GitHub repository.

License
This project is licensed under the MIT License.