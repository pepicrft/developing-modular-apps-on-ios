footer: @pepibumur
slidenumbers: true

# Developing modular apps on iOS
#### NSPresenter Madrid - February 28th
[.footer: ]

### **@pepibumur**

![](images/intro.jpg)

---

# About me

- Production Engineer at Shopify.
- Building tools for mobile developers.
- Born and raised in the ❤️ Murcia.
- Suffering the ☔️ in Berlin.
- 📄 _ppinera.es_
- 🐦 _@pepibumur_
- 📧 _pedro.pinera@shopify.com_

![right](images/team.jpg)

[.footer: ]

---

# What/why/how
### **should I modularize my app?**

---

# What

![](images/what.jpg)

---

> "Modularizing an app consists on organising your app code and resources in multiple modules"

---

# A module can be

- *A library:* If it doesn't have resources.
- *A framework:* If it has them.
- *Static:* If it's linked at compile time.
- *Dynamic:* If it's linked at startup time.

---

### Static linking - **Compilation time**
### Dynamic linking - **Startup time**

---

# Dynamic modules **need to be copied** into the product for dylib to link them

---

# Static modules not properly linked might lead to **duplicated symbols**

---

# **Carthage** & **CocoaPods** are two examples of tools that modularise your dependencies

### Carthage: Dynamic linking
### CocoaPods: Static & dynamic linking

---

# Most of apps are usually built and grown as **monoliths**
### 1 target with the app source
### 1 target with the tests
### _(And maybe some extensions)_

---

# Why

![](images/why.jpg)

---

# If you are a freelancer 👩‍💻👨‍💻
### **You might want to reuse code**

---

# If you have multiple products 💻⌚️📱
### **You might want to reuse code**
### *(e.g. Shopify has 5 iOS apps)*

---

# If you want to write weakly coupled components 🏝
### **You can leverage modules interfaces**
### *(internal by default in Swift)*

---

# If you want to speed up your workflow ⏰
### **And spend less time waiting for the compiler**

---

# The compile time is proportional to the **size of the codebase**

---

# But...

### Apple is improving the Swift compiler
### The compiler builds incrementally *(only clean builds should take more time)*

---

- ⌘ + B (10 minutes)
- Change code + (⌘ + B) (4 Seconds)
- Change something + (⌘ + B) - (Error)
- *⌘ + K (I'm sure this helps)*
- *⌘ + B (10 minutes)*

---

- 30 developers.
- 10 clean builds per day.
- 10 minutes per clean build.

*1000 hours spent per month*
*6.25 engineers*

---

# 😛 **Fortunately**, there's something you can do to avoid this

---

# How

![](images/how.jpg)

---

# This is just **one approach**
### That works in my experience

---

# Layers
# Project
# Downsides

---

# Before anyone asks...

---

# Yes, to avoid the hassle of dealing with versioning or git submodules, **all the modules in the same repository**

---

# Apps are split in modules that represent **features**

---

# Shared components are extracted into **foundation modules**

---

- Search
- Profile
- Orders

- *UI* (shared)
- *Core* (shared)
- *Testing* (shared)

---

- Yes! Everything in one repository.
- Selective continuous integration.
- Slow CI still
