# Add C++ `bits/stdc++.h` Header Files on macOS (VS Code)

If you're using macOS and want to use the `#include<bits/stdc++.h>` header in your C++ projects with VS Code, follow the steps below to manually set it up.

---

## Step-by-Step Instructions

### 1. Check System Include Paths

Open your terminal and run the following command:

```bash
echo | g++ -v -x c++ -E -
```

After some scroll This will print the include paths used by `g++`. Look for lines like the following:

```
 /usr/local/include
 /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include/c++/v1
 /Library/Developer/CommandLineTools/usr/lib/clang/17/include
 /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include
 /Library/Developer/CommandLineTools/usr/include
 /Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/System/Library/Frameworks (framework directory)
```

---

### 2. Navigate to the Include Directory

1. In the terminal output, locate this path:

```
/Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include

```

2. **Command + Click** on the path in the terminal to open it in Finder.

3. Inside this folder, locate the `atm` subfolder.

4. **Right-click on `atm`** → **Select "Reveal in Finder"**.

5. Now, clone repository the using this command

```bash
git clone https://github.com/shariarhossain17/macos-cpp-bits-setup_step_by_step.git
```

Or,
download the repository as a ZIP file by following these steps:

Click the Code button on the GitHub page.

- Select Download ZIP.

- Unzip the downloaded folder.

**After cloning or downloading, follow these steps:**

- Open the folder named macos-cpp-bits-setup_step_by_step.

- Inside this folder, locate and open the bits folder.

- If you see a file named .DS_Store, delete it. If you don’t see this file, you ignore this step.

- Finally, copy the entire bits folder for your use.

6. **Paste** the `bits` folder into the `atm` folder.

---

### 3. Add `bits` to the C++ Standard Library Folder

1. In the terminal output again, locate this path:

```
/Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include/c++/v1
```

2. **Command + Click** to open this in Finder.

> **Note**: If you don't see it, re-run:
>
> ```bash
> echo | g++ -v -x c++ -E -
> ```

3. Inside this folder, find the `__concepts` directory.

4. **Right-click on `__concepts`** → **Select "Reveal in Finder"**.

5. **Paste** the `bits` folder into the `__concepts` folder as well.

---

### 4. Add `bits` to Clang's Include Folder

1. Locate this path from the terminal output:

```
/Library/Developer/CommandLineTools/usr/lib/clang/17/include
```

2. **Command + Click** to open it in Finder.

> Again, if you don’t see it, re-run the command:
>
> ```bash
> echo | g++ -v -x c++ -E -
> ```

3. Inside this folder, find the `sanitizer` directory.

4. **Right-click on `sanitizer`** → **Select "Reveal in Finder"**.

5. **Paste** the `bits` folder into the `sanitizer` directory.

---

## Done!

You can now use:

```cpp
#include<bits/stdc++.h>
```

in your C++ files without errors in VS Code on macOS.

---

## ⚠️ Notes

- Make sure you have **Command Line Tools for Xcode** installed.
- These changes might get overwritten with a future Xcode or macOS update, so keep a backup of your `bits` folder.
- This method manually places the `bits` headers in directories searched by the compiler. It is a workaround, as `bits/stdc++.h` is a GNU-specific header and not officially supported on non-Linux systems.
