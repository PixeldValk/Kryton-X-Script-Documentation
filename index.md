# **Kryton X Script Documentation**

## **Introduction**

Welcome to the Kryton X Script Documentation. This document provides a detailed overview of the Kryton X executor, including its API, DLL, and injector. This documentation is designed to help developers understand how to use and integrate Kryton X into their projects for educational and testing purposes.

## **Table of Contents**

1. [Overview](#overview)
2. [API Documentation](#api-documentation)
   - [InitializeExecutor](#initializeexecutor)
   - [ExecuteScript](#executescript)
   - [LoadScriptFromFile](#loadscriptfromfile)
   - [SaveScriptToFile](#savescripttofile)
   - [SetPermissionLevel](#setpermissionlevel)
   - [GetPermissionLevel](#getpermissionlevel)
   - [CommunicateWithDLL](#communicatewithdll)
3. [DLL Documentation](#dll-documentation)
   - [InitializeDLL](#initializedll)
   - [ExecuteScriptInProcess](#executescriptinprocess)
   - [CommunicateWithExecutor](#communicatewithexecutor)
   - [LoadConfiguration](#loadconfiguration)
4. [Injector Documentation](#injector-documentation)
   - [Manual Mapping](#manual-mapping)
   - [HijackThread](#hijackthread)
5. [Best Practices](#best-practices)
6. [Appendices](#appendices)
   - [Glossary](#glossary)
   - [Troubleshooting](#troubleshooting)

---

## **Overview**

Kryton X is a high-performance executor designed for educational purposes and advanced script execution. It includes a powerful API, a secure DLL, and a sophisticated injector, providing a robust platform for script management and execution.

## **API Documentation**

### **InitializeExecutor**

**Description**: Initializes the Kryton X executor environment.

**Syntax**:
```cpp
bool InitializeExecutor();
```

**Parameters**: None

**Returns**: `true` if initialization is successful, otherwise `false`.

**Example**:
```cpp
if (InitializeExecutor()) {
    std::cout << "Executor initialized successfully." << std::endl;
} else {
    std::cerr << "Failed to initialize executor." << std::endl;
}
```

### **ExecuteScript**

**Description**: Executes a script with a specified permission level.

**Syntax**:
```cpp
bool ExecuteScript(const char* scriptCode, int permissionLevel);
```

**Parameters**:
- `scriptCode`: The script code to execute.
- `permissionLevel`: The level of permission required to execute the script.

**Returns**: `true` if the script is executed successfully, otherwise `false`.

**Example**:
```cpp
const char* script = "print('Hello, World!')";
int level = 1; // Example permission level
if (ExecuteScript(script, level)) {
    std::cout << "Script executed successfully." << std::endl;
} else {
    std::cerr << "Failed to execute script." << std::endl;
}
```

### **LoadScriptFromFile**

**Description**: Loads a script from a file and executes it.

**Syntax**:
```cpp
bool LoadScriptFromFile(const char* filePath);
```

**Parameters**:
- `filePath`: The path to the script file.

**Returns**: `true` if the script is loaded and executed successfully, otherwise `false`.

**Example**:
```cpp
if (LoadScriptFromFile("path/to/script.lua")) {
    std::cout << "Script loaded and executed from file." << std::endl;
} else {
    std::cerr << "Failed to load script from file." << std::endl;
}
```

### **SaveScriptToFile**

**Description**: Saves the provided script code to a file.

**Syntax**:
```cpp
bool SaveScriptToFile(const char* filePath, const char* scriptCode);
```

**Parameters**:
- `filePath`: The path where the script will be saved.
- `scriptCode`: The script code to save.

**Returns**: `true` if the script is saved successfully, otherwise `false`.

**Example**:
```cpp
const char* script = "print('Hello, World!')";
if (SaveScriptToFile("path/to/save_script.lua", script)) {
    std::cout << "Script saved successfully." << std::endl;
} else {
    std::cerr << "Failed to save script." << std::endl;
}
```

### **SetPermissionLevel**

**Description**: Sets the current permission level for script execution.

**Syntax**:
```cpp
void SetPermissionLevel(int level);
```

**Parameters**:
- `level`: The permission level to set.

**Example**:
```cpp
SetPermissionLevel(2);
std::cout << "Permission level set to 2." << std::endl;
```

### **GetPermissionLevel**

**Description**: Retrieves the current permission level.

**Syntax**:
```cpp
int GetPermissionLevel();
```

**Returns**: The current permission level.

**Example**:
```cpp
int level = GetPermissionLevel();
std::cout << "Current permission level: " << level << std::endl;
```

### **CommunicateWithDLL**

**Description**: Sends a message to the DLL for communication purposes.

**Syntax**:
```cpp
bool CommunicateWithDLL(const char* message);
```

**Parameters**:
- `message`: The message to send to the DLL.

**Returns**: `true` if communication is successful, otherwise `false`.

**Example**:
```cpp
if (CommunicateWithDLL("Hello from API")) {
    std::cout << "Message sent to DLL." << std::endl;
} else {
    std::cerr << "Failed to send message to DLL." << std::endl;
}
```

## **DLL Documentation**

### **InitializeDLL**

**Description**: Initializes the DLL.

**Syntax**:
```cpp
bool InitializeDLL();
```

**Parameters**: None

**Returns**: `true` if initialization is successful, otherwise `false`.

**Example**:
```cpp
if (InitializeDLL()) {
    std::cout << "DLL initialized successfully." << std::endl;
} else {
    std::cerr << "Failed to initialize DLL." << std::endl;
}
```

### **ExecuteScriptInProcess**

**Description**: Executes a script within the target process.

**Syntax**:
```cpp
bool ExecuteScriptInProcess(const char* scriptCode);
```

**Parameters**:
- `scriptCode`: The script code to execute.

**Returns**: `true` if the script is executed successfully, otherwise `false`.

**Example**:
```cpp
const char* script = "print('Hello from DLL')";
if (ExecuteScriptInProcess(script)) {
    std::cout << "Script executed in process." << std::endl;
} else {
    std::cerr << "Failed to execute script in process." << std::endl;
}
```

### **CommunicateWithExecutor**

**Description**: Communicates with the Kryton X executor.

**Syntax**:
```cpp
bool CommunicateWithExecutor(const char* message);
```

**Parameters**:
- `message`: The message to send to the executor.

**Returns**: `true` if communication is successful, otherwise `false`.

**Example**:
```cpp
if (CommunicateWithExecutor("Hello from DLL")) {
    std::cout << "Message sent to executor." << std::endl;
} else {
    std::cerr << "Failed to send message to executor." << std::endl;
}
```

### **LoadConfiguration**

**Description**: Loads configuration or settings from a file.

**Syntax**:
```cpp
bool LoadConfiguration(const char* configPath);
```

**Parameters**:
- `configPath`: The path to the configuration file.

**Returns**: `true` if the configuration is loaded successfully, otherwise `false`.

**Example**:
```cpp
if (LoadConfiguration("path/to/config.cfg")) {
    std::cout << "Configuration loaded." << std::endl;
} else {
    std::cerr << "Failed to load configuration." << std::endl;
}
```

## **Injector Documentation**

### **Manual Mapping**

**Description**: Injects a DLL into a target process using manual mapping.

**Parameters**:
- `hProcess`: Handle to the target process.
- `dllData`: Data of the DLL to inject.

**Returns**: `true` if injection is successful, otherwise `false`.

**Example**:
```cpp
std::vector<char> dllData; // DLL data loaded here
HANDLE hProcess = OpenProcess(PROCESS_ALL_ACCESS, FALSE, targetProcessId);
if (ManualMapDLL(hProcess, dllData)) {
    std::cout << "DLL injected successfully." << std::endl;
} else {
    std::cerr << "Failed to inject DLL." << std::endl;
}
```

### **HijackThread**

**Description**: Injects code into an existing thread of the target process.

**Parameters**:
- `hProcess`: Handle to the target process.
- `threadId`: ID of the thread to hijack.
- `payload`: Pointer to the code to execute.

**Returns**: `true` if hijacking is successful, otherwise `false`.

**Example**:
```cpp
DWORD threadId = 1234; // Example thread ID
void* payload = ...; // Code to inject
if (HijackThread(hProcess, threadId

, payload)) {
    std::cout << "Thread hijacked successfully." << std::endl;
} else {
    std::cerr << "Failed to hijack thread." << std::endl;
}
```

## **Best Practices**

1. **Security**: Ensure that the DLL and API code are obfuscated and protected against tampering.
2. **Error Handling**: Implement robust error handling and logging to troubleshoot issues.
3. **Documentation**: Keep the documentation up-to-date with any changes to the API or DLL.
4. **Testing**: Thoroughly test the injector and executor in various environments to ensure reliability and stability.

## **Appendices**

### **Glossary**

- **API**: Application Programming Interface, a set of functions that allows interaction with the Kryton X executor.
- **DLL**: Dynamic Link Library, a file containing code and data that can be used by multiple programs simultaneously.
- **Injector**: A tool that injects code or a DLL into a target process.

### **Troubleshooting**

- **Initialization Issues**: Ensure that all dependencies are properly loaded and that the target process is accessible.
- **Script Execution Failures**: Verify the script code and permissions required for execution.
- **DLL Injection Problems**: Check for errors in the manual mapping or thread hijacking process and ensure that the target process is compatible.
