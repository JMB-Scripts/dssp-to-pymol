## **DSSP PyMOL Plugin Manual**

### **Introduction**

The DSSP PyMOL Plugin allows users to run `mkdssp` directly within PyMOL and load the resulting secondary structure data from the CIF file into the PyMOL workspace.

### **Installation**

1. **Prerequisites**:
   - Ensure `mkdssp` is installed and accessible from your system's PATH.
         Citation :
         Kabsch W, Sander C. Dictionary of protein secondary structure: pattern recognition of hydrogen-bonded and geometrical features. Biopolymers. 1983 Dec;22(12):2577-637. doi: 10.1002/bip.360221211. PMID: 6667333
   - Have PyMOL installed on your machine.
       Citation :
       (Schrödinger, LLC 2015)
2. **Plugin Installation**:
   - Save the plugin script (`dssp_cif_plugin.py`) to the `$PYMOLPATH/modules/pmg_tk/startup/` directory. Alternatively, you can place it in any directory where PyMOL sources plugins.
   - Start PyMOL. If it's already running, source the plugin using:
     ```pml
     run /path/to/dssp_cif_plugin.py
     ```

### **Usage**

1. **Command**:
   ```pml
   run_dssp_and_load [selection]
   ```
   Replace `[selection]` with the desired protein object or any valid PyMOL selection. If no selection is provided, it defaults to processing all loaded structures.

2. **Output**:
   After execution, a new object named "dssp_output" will be loaded in PyMOL containing the secondary structure information from DSSP.

### **Workflow Example**:

1. Load a protein structure into PyMOL:
   ```pml
   load example.pdb
   ```

2. Use the plugin to run DSSP and load the secondary structure:
   ```pml
   run_dssp_and_load example
   ```

3. Visualize the "dssp_output" structure to see the secondary structure annotations from DSSP.

### **Troubleshooting**:

- **Error while running `mkdssp`**: Ensure `mkdssp` is installed correctly and accessible from the system's PATH.
  
- **Permissions Issue**: The plugin creates temporary files in the `/tmp/` directory. Ensure you have write access to this directory.
