# **RightClickMe \- The Context Menu Builder**

**Slogan:** The Context Menu Builder

**Author:** Joshua Dwight

**Version:** 1.0.8 (Dual Edition)

## **📖 Overview**

RightClickMe is a powerful super admin tool designed to help system administrators and power users create, modify, and manage Windows right-click context menus.

We officially maintain **two distinct versions** of the tool to accommodate different workflow needs. They are identical in features, UI, and functionality:

1. **SysAdmin Edition (RightClickMe.ps1)**: A highly portable PowerShell \+ C\# hybrid script. Perfect for administrators who want to move the tool around without triggering anti-virus concerns associated with random .exe files, and who don't want to install anything.  
2. **Standard Edition (RightClickMe.cs → .exe)**: A pure C\# source file that can be compiled into a standalone executable. Perfect for standard users who just want to double click a program without interacting with PowerShell terminals.

## **✨ Features**

* **Hierarchy Support**: Create root menus and nested cascading submenus natively supported by Windows 10 and 11\.  
* **Context Targets**: Apply right-click options specifically to:  
  * Files (All file extensions \*)  
  * Folders (Directory tree)  
  * Background (Inside a folder / desktop background)  
* **Command execution Types**:  
  * PowerShell (Executes quietly in the background).  
  * CMD (Executes via command prompt).  
  * EXE (Launch standard executables).  
* **Elevation**: Integrated Run as Administrator checkbox that adds the UAC shield to the context menu and executes commands elevated.  
* **Template Manager**: Easily save, load, and manage customized templates inside the application's Template Manager tab. Templates are seamlessly stored locally.  
* **User Manual**: A built-in user guide accessible via the Help menu, offering tips, explanations on variables (%1, %V), and architectural behavior.

## **🚀 How to Run (SysAdmin Edition \- PowerShell)**

1. Right-click the RightClickMe.ps1 file and select **Run with PowerShell**.  
2. If you are not running as Administrator, the script will prompt UAC and self-elevate.  
3. Use the interface to build your menu structure, then click **Apply to Registry**.

*Debug Mode:* To see verbose logs, run .\\RightClickMe.ps1 \-DebugMode from a terminal.

## **🛠️ How to Compile & Run (Standard Edition \- C\#)**

Because this is a pure C\# file utilizing built-in .NET frameworks, you do not need Visual Studio to build it. You can compile it directly using the built-in Windows C\# compiler (csc.exe).

1. Open your Command Prompt or PowerShell.  
2. Run the following command against the downloaded file:  
   C:\\Windows\\Microsoft.NET\\Framework64\\v4.0.30319\\csc.exe /target:winexe /reference:System.Web.Extensions.dll /out:RightClickMe.exe RightClickMe.cs

3. This generates RightClickMe.exe.  
4. Double-click the generated .exe. It has an embedded bootstrapper that will automatically ask for Administrator permissions.

## **⚠️ Notes for Windows 11 Users**

Windows 11 introduced a "Modern" context menu. Custom registry keys applied by this tool will appear under the **"Show more options"** (Shift+F10) legacy context menu, guaranteeing stability and broad compatibility without needing to compile complex IExplorerCommand COM shell extensions.