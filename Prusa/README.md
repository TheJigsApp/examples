# Prusa: Buddy Board Mini
## 2024-07-13

+ [Store: Prusa3d](https://www.prusa3d.com/product/original-prusa-mini-semi-assembled-3d-printer-4/)
+ [Company Website](https://www.prusa3d.com)
+ [Source: GitHub](https://github.com/prusa3d/Buddy-board-MINI-PCB)


## Building Input Package
1. Package the manufacturing files
  ```sh
  make -f ../libs/kicad-make/Makefile --directory=Buddy-board-MINI-PCB/rev.1.0.0/ OUTDIR=$(pwd)/testjig PROJECT=BUDDY_v1.0.0 VERSION=1.0.X 
  ```
This will create a zip with the gerbers (and other manufacturing drawings)

2. Export the test-point report
  ```sh
  kicad_testpoints by-fab-setting --pcb Buddy-board-MINI-PCB/rev.1.0.0/BUDDY_v1.0.0.kicad_pcb --out $(pwd)/testjig/testpoint-report.xlsx --drill-center 
  ```

3. Create the design.toml file
  + The web interface will give feedback on these values with visualizaions


4. Create the design-input.xlsx file
  + Paste in the test-point report
  + Add Support pins
  + Assign nets to the connector
