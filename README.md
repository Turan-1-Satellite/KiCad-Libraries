# KiCad Libraries

This repository contains all custom electronic component libraries used in the **Turan-1 Satellite project**.

The library includes:

- Custom schematic symbols
- Custom PCB footprints
- 3D models for components used in the satellite design

These libraries are intended to be used with KiCad for the development of the Turan-1 satellite electronics.

---

## Importing the Library to the project

1. To use this library inside your KiCad project, all you need is adding this repository as a git submodule (more -> https://git-scm.com/book/en/v2/Git-Tools-Submodules). This means that git must track KiCad project to be able to use it as a git submodule. To enable git to track your local KiCad project (if not already tracking), run this command inside your terminal inside project root directory:
```
git init
```

2. After confirming your project is tracked by git, navigate your KiCad project root and run the below command inside your terminal:
```
git submodule add https://github.com/Turan-1-Satellite/KiCad-Libraries.git
```
This creates 
```
root-kicad-project/
├── root-kicad-project.kicad_pro
├── root-kicad-project.kicad_sch
├── KiCad-Libraries/	← git submodule
├    ├─── 3Ds/
├    ├─── Footprints.pretty/
├    ├─── Symbols/	
├    ├─── sym-lib-table
├    ├─── ft-lib-table
├    ├─── README.md
└── .gitmodules
```

3. Before using library, you have to copy ```sym-lib-table``` and ```ft-lib-table``` to project level (**Note COPY not MOVE**). 
After moving project directory looks like this (.gitmodules, sym-lib-table, ft-lib-table is not visible inside KiCad project, but they exist inside project repo and git considers these files):
```
root-kicad-project/
├── root-kicad-project.kicad_pro
├── root-kicad-project.kicad_sch
├── KiCad-Libraries/	← git submodule
├    ├─── 3Ds/
├    ├─── Footprints.pretty/
├    ├─── Symbols/	
├    ├─── sym-lib-table
├    ├─── ft-lib-table
├    ├─── README.md
├─── .gitmodules
├─── sym-lib-table
└─── ft-lib-table
```
Now you can use symbols and footprints of this library under Custom-Symbols and Custom-Footprints section respectively.

---

## Adding Symbols to the Library
1. Open "Symbol Editor" inside your project

2. Navigate to **Custom-Symbols** on the left sidebar.

3. Under **Custom-Symbols/** section, you can see all the symbols inside this library. You can create "New Symbol" or import one under this library.

---

## Adding Footprints to the Library

1. Open "Footprint Editor" inside your project

2. Navigate to **Custom-Footprints** on the left sidebar.

3. Under **Custom-Footprints/** section, you can see all the footprints inside this library. You can create "New Footprint" or import one under this library.

4. If you have 3d connected to this footprint, put it under "/3Ds" folder to share it with others. And put the relative path to step file like:
```${KIPRJMOD}/KiCad-Libraries/3Ds/3d-model.step```

---

Congrats, now you can use this library!

## Note
```KIPRJMOD``` is an default environment variable KiCad uses to navigate the project root directory. **DO NOT** manually add it inside env variables inside KiCad. 
If you do so, it becomes global not project-specific; KiCad assumes that the root project directory is the path you manually assigned in all KiCad projects on your local computer.
As you cannot delete it after putting this env variable, you have to uninstall and reinstall KiCad to remove this variable. 
