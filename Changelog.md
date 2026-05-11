# **Changelog**

All notable changes to the **RightClickMe** project will be documented in this file.

## **\[1.0.8\] \- 2026-05-11**

### **Added**

* **Dual-Release Strategy**: The project officially split distribution into two distinct flavors:  
  * **SysAdmin Edition**: RightClickMe.ps1 (Maintained PowerShell Hybrid).  
  * **Standard Edition**: RightClickMe.cs (Maintained Pure C\# Executable).  
* Standard Edition includes a native WindowsPrincipal C\# bootstrapper using ProcessStartInfo.Verb \= "runas", allowing it to manage its own UAC rights securely without PowerShell overhead.  
* Updated documentation (README) to provide explicit csc.exe compilation instructions for standard users.  
* Synchronized version numbers across both platforms to v1.0.8.

## **\[1.0.7\] \- 2026-05-11**

### **Added**

* Implemented a **Tab Control UI**, splitting the layout into "Menu Builder" and "Template Manager".  
* Developed a full MVP **Template Manager**, giving users the ability to easily save their built menus, name them via a dynamic InputBox, and selectively load or delete them from a list. Templates are stored persistently in %APPDATA%\\RightClickMe\\templates.json.  
* Added a **User Manual** form, accessible via Help \-\> User Manual.

## **\[1.0.6\] \- 2026-05-11**

### **Added**

* Added \-DebugMode PowerShell parameter.  
* Added a fail-safe try/catch block inside the C\# MainForm constructor.

### **Fixed**

* Addressed the persistent SplitterDistance layout crash by forcing explicit bounds mapping.

## **\[1.0.5\] \- 2026-05-11**

### **Fixed**

* Further resolved the SplitterDistance crash by applying distance values during Form.Load.

## **\[1.0.4\] \- 2026-05-11**

### **Fixed**

* Ordered initialization logic for the SplitContainer to expand prior to configuring child bounds.

## **\[1.0.3\] \- 2026-05-11**

### **Fixed**

* Resolved The type name 'RightClickMeApp.MenuItemData' already exists error via dynamic Session IDs.

## **\[1.0.2\] \- 2026-05-11**

### **Fixed**

* Replaced absolute coordinate positioning with responsive TableLayoutPanel and FlowLayoutPanel elements in the UI to fix clipping on High-DPI screens.

## **\[1.0.1\] \- 2026-05-11**

### **Fixed**

* Replaced C\# 6.0 string interpolation ($"") with standard string concatenation to ensure compilation compatibility with Windows PowerShell 5.1's default C\# 5.0 compiler.

## **\[1.0.0\] \- 2026-05-11**

### **Added**

* Initial MVP Release.