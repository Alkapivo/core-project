
### [CORE] PROJECT

GameMaker Studio 2 framework. It contains:
- [**io.alkapivo.core-gml**](https://github.com/Alkapivo/core-gml)
- [**mh-cz.gmtf-gml**](https://github.com/Alkapivo/mh-cz.gmtf-gml)
- [**fyi.odditica.bktGlitch-gml**](https://github.com/Alkapivo/fyi.odditica.bktGlitch-gml)

---


## Setup

Install:
- **[GameMaker Studio 2](https://releases.gamemaker.io/release-notes/2024/14_2)** 
version `2024.14.2.256`
- **[YoYo compiler](https://gamemaker.zendesk.com/hc/en-us/articles/235186048-Setting-Up-For-Windows)** version `VS2022`
- **[gm-cli](https://github.com/Alkapivo/gm-cli)** version `25.12.05^`


Create `gm-cli.env` file and replace values between `{}` with actual data:
```bash
GMS_IGOR_PATH="{PATH_TO_IGOR_EXE}"
GMS_USER_PATH="{PATH_TO_ROAMING_GAMEMAKERSTUDIO2_USER_FOLDER}"
GMS_RUNTIME_PATH="{PATH_TO_RUNTIME_2024.14.2.256}"
GMS_RUNTIME="VM"
GMS_TARGET="windows"
GMS_PROJECT_NAME="core-project"
GMS_PROJECT_PATH="yyp"
```


Setup GameMaker project by executing commands:
```bash
gm-cli install 
gm-cli run setup
gm-cli generate
```
This has to be after changing sources in `gm_modules` or after updating dependencies in `package-gm.json`. Otherwise not all files may sync with GameMaker Studio 2 project.

---


## Build
To generate `core-project.zip` archive built with GameMaker Studio 2 VM execute command:
```bash
gm-cli make
```

To run clean build add `--clean` (short `-c`):
```bash
gm-cli make --clean
```

To just run (zip archive will not be created!) please add argument `--launch` (short `-l`)
```bash
gm-cli make --launch
```

If you dont pass `--launch` then you can specify name of archive with argument `--name` (short `-n`):
```bash
gm-cli make --name=core-project_win_vm
```

You can also use GameMaker Studio 2 YoYo compiler instead by adding `--runtime=YYC` (short `-r YYC`):
```bash
gm-cli make --runtime=YYC
```

You can pass many arguments, e.g.:
```bash
gm-cli make -c -r YYC --name=core_project_win_yyc
```

---

