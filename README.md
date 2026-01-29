# KiCad Project Template

A professional KiCad project template for rapid prototyping with PCBWay-compatible design rules, hierarchical schematics, and pre-configured netclasses.

## Features

- **Hierarchical Schematic Structure** - Organized with Block Diagram, Mechanical, and Revision History sheets
- **PCBWay-Compatible Design Rules** - Ready for low-cost PCB manufacturing
- **Pre-defined Netclasses** - Color-coded net categories (PWR, GND, USB, UART, GPIO, ADC, etc.)
- **Title Block Template** - Professional documentation with configurable variables
- **Plugin Support** - Pre-configured for board2pdf and Interactive BOM (ibom)
- **Altium-Style Color Theme** - Optional alternative color scheme

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/aqsnyder/kicad-toolkit.git
```

### 2. Configure KiCad Template Path

1. Open KiCad and navigate to **Preferences → Configure Paths**
2. Create an environment variable: `KICAD_USER_TEMPLATE_DIR`
3. Set it to the path of the `template/` folder from this repo

### 3. Create a New Project from Template

1. In KiCad, go to **File → New Project From Template**
2. Under "User Templates", select the folder where you cloned this repo
3. Choose the template and click 'OK'
4. **Important:** Save the new project to a *different location*, not inside the template folder!

## Project Structure

```
your_new_project/
├── project_template.kicad_pro     # Project file with design rules & netclasses
├── project_template.kicad_sch     # Root schematic with page index
├── project_template.kicad_pcb     # PCB with pre-configured DRC rules
├── project_template.kicad_dru     # Design rules (PCBWay compatible)
├── Block Diagram.kicad_sch        # System overview sheet
├── Mechanical.kicad_sch           # Mechanical/enclosure sheet
├── Revision History.kicad_sch     # Revision tracking sheet
├── Templates/                     # Title block templates
├── Manufacturing/                 # Gerber/drill output folder
├── DXF_SVG/                       # Export files
├── Images/                        # Screenshots, renders
└── STEP/                          # 3D model exports
```

## Pre-configured Netclasses

| Netclass    | Color  | Track Width | Use Case               |
| ----------- | ------ | ----------- | ---------------------- |
| Default     | -      | 0.3mm       | General signals        |
| PWR         | Red    | 0.5mm       | Power rails            |
| GND         | Green  | 0.5mm       | Ground                 |
| USB         | Cyan   | 0.2mm       | USB differential pairs |
| UART        | Purple | 0.3mm       | Serial communication   |
| GPIO        | Blue   | 0.3mm       | General I/O            |
| ADC         | Orange | 0.3mm       | Analog signals         |
| TRACE/DEBUG | Yellow | 0.25mm      | Debug interfaces       |

## Text Variables

The template includes configurable text variables for your title block:

- `${COMPANY}` - Your company/personal name
- `${DESIGNER}` - Designer name
- `${REVIEWER}` - Reviewer name
- `${PROJECT_NAME}` - Project name
- `${BOARD_NAME}` - Board/assembly name
- `${REVISION}` - Current revision
- `${VARIANT}` - Hardware variant
- `${RELEASE_DATE}` - Release date

Set these in **File → Schematic Setup → Project → Text Variables**

## Color Theme (Optional)

An Altium-style color theme is included in `color_themes/`:

1. Copy `Altium_Theme.json` to your KiCad colors folder:
   - Windows: `%APPDATA%\kicad\9.0\colors\`
   - Linux: `~/.config/kicad/9.0/colors/`
   - macOS: `~/Library/Preferences/kicad/9.0/colors/`
2. In KiCad: **Preferences → Preferences → Colors → Select "Altium_Theme"**

## Manufacturing

Use the official [PCBWay KiCad Plugin](https://www.pcbway.com/blog/News/PCBWay_Plug_In_for_KiCad_3ea6219c.html) to export manufacturing data directly.

## Using with kicad-library

For component management, use the companion [kicad-library](https://github.com/aqsnyder/kicad-library) repository:

```bash
# Add as submodule to your project
git submodule add https://github.com/aqsnyder/kicad-library.git lib
git submodule update --init --recursive
```

Then configure library paths in your project's sym-lib-table and fp-lib-table.

## Credits

- Template structure based on [nguyen-v/KiCAD_Templates](https://github.com/nguyen-v/KiCAD_Templates)
- Design rules adapted from [PCBWay specifications](https://www.pcbway.com/pcb_prototype/PCB_Design_Rule_Check.html)

## License

MIT License - see [LICENSE](LICENSE)

---

**Author:** [aqsnyder](https://github.com/aqsnyder)
