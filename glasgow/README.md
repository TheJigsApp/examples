# GlasgowEmbedded: Glasgow
## 2024-07-13

## Building Input Package
1. Package the manufacturing files
  ```sh
  make -f ../libs/kicad-make/Makefile --directory=glasgow/hardware/boards/glasgow OUTDIR=$(pwd)/testjig PROJECT=glasgow VERSION=C.1.X 
  ```
This will create a zip with the gerbers (and other manufacturing drawings)

2. Export the test-point report
  ```sh
  kicad_testpoints by-fab-setting --pcb glasgow/hardware/boards/glasgow/glasgow.kicad_pcb  --out $(pwd)/testjig/testpoint-report.xlsx --drill-center 
  ```

3. Create the design.toml file
  + The web interface will give feedback on these values with visualizaions


4. Create the design-input.xlsx file
  + Paste in the test-point report
  + Add Support pins
  + Assign nets to the connector
