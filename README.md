# 🖥️ FPGA-Based Text & Graphics Editors

This repository contains two digital systems developed in VHDL and deployed on an FPGA board (Altera DE2):  
a **Text Editor** and a **Graphics Editor**, both rendered on a VGA display and controlled via keyboard or mouse.

<img width="316" alt="Captura de ecrã 2025-07-05 111201" src="https://github.com/user-attachments/assets/7ccc7a73-f4c5-4d88-8ff8-e72efe6417e4" />
<img width="308" alt="Captura de ecrã 2025-07-05 111303" src="https://github.com/user-attachments/assets/1376fac6-1fd7-44c2-b3c5-2783c061f68c" />


> 📚 **Course**: Digital Systems Design 
> 🏫 **Institution**: Universidade de Coimbra – DEEC  
> 📅 **Year**: 2023/2024  
> 👥 **Authors**: Gonçalo Bastos - eusoudebastos@gmail.com , Leonardo Cordeiro - leoleocordeiro@gmail.com

---

## 🧩 Project Structure
  - README.md
  - docs:
    - PSD_Report_Editor_Texto.pdf  # Text Editor report
    - PSD_Report_Editor_Grafico.pdf  # Graphics Editor report
    - PSD_Project.pdf  # Project prompt
  - text_editor:
    - top_level.png  # Top-level view (from report)
    - ... .png # Other images
    - text_editor.zip  # QuartusII project files
  - graphics_editor:
    - top_level.png  # Top-level view (from report)
    - ... .png # Other images
    - graphics_editor.zip  # QuartusII project files
  - demo_video:
    - MiniProjetos_PSD.mp4 # Demonstration Video of both projects 

---

## 🧠 Text Editor Overview

The text editor emulates a terminal with basic line editing, enabling:

- Character input via PS/2 keyboard
- Handling of ENTER, BACKSPACE and arrow keys
- VGA rendering of characters using a CHAR ROM
- Cursor movement and screen updates via RAM and sync control

### 🛠️ Key Modules
- `KeyboardController.vhd`: Scancode parsing
- `CharDecoder.vhd`: PS2 to CHAR ROM address conversion
- `CursorControl.vhd`: Position tracking and cursor behavior
- `RAM.vhd`: Stores character grid for VGA output
- `TopLevel.vhd`: Integrates all modules

---

## 🎨 Graphics Editor Overview

This system allows freehand drawing using a PS/2 mouse on VGA display, supporting:

- A visible 4x4 pixel cursor
- Drawing and erasing with mouse buttons
- Selection between 8 different colors
- Full-screen clearing via hardware button

### 🛠️ Key Modules
- `PaintControl.vhd`: Color & draw logic from switches/buttons
- `Cursor.vhd`: Determines cursor location and pixel rendering
- `MouseInterface.vhd`: Interfaces with PS/2 mouse input
- `RAM.vhd`: Stores pixel color values for drawing
- `TopLevel.vhd`: High-level schematic

---

## 🖼️ System Diagrams

Each project includes a top-level view image in its respective folder (from the report), showing module interconnections and data flow.

---

## 🎥 Demos

Demo videos demonstrating editor functionality are available in the `/demo_video` folder:
- `MiniProjetos_PSD.mp4`: Text input, backspace, enter and cursor movements & Freehand drawing and color switching
---

## 📌 Notes

- All VHDL code was synthesized and tested using **Quartus II**
- RAM modules created using Altera Megafunctions (`lpm_ram_dp`)
- Interfaces strictly use VGA + PS/2 protocols
- This project was part of the final lab assignment for PSD (Projeto de Sistemas Digitais)

---

## 🔐 License

This repository is for academic use only and was developed within the scope of the **Digital Systems Project** course at the **University of Coimbra**.

