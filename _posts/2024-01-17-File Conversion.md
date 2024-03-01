# How to convert between different file formats in proteomics?
This is a short tutorial on what tools you can use when converting files from .raw into .mzML, .mzXML formats. This tutorial is for converting proteomics mass spectrometry files. Please let me know if you have any comments or suggestions. :) 

## OpenMS 
[Download](https://openms.readthedocs.io/en/latest/index.html) 
This program has many useful tools, including a file parser and converter to mzML and mzXML.

You can run the FileConverter on a local directory with your *.raw files to convert to .mzML uring this small bash script. 
```
#!/bin/bash

# Input and output directories
input_dir="/INPUTPATH" # change to your own folder
output_dir="/OUTPUTPATH"

# Check if the output directory exists, and if not, create it
mkdir -p "$output_dir"

# Iterate over files in the input directory
for input_file in "$input_dir"/*.raw; do
  # Get the base filename (without the path)
  base_filename=$(basename "$input_file")

  # Construct the output filename with .mzML extension
  output_file="$output_dir/${base_filename%.raw}.mzML" 

  # Run the FileConverter command to convert the file
  FileConverter -in "$input_file" -out "$output_file"  # -no_peak_picking

   # Construct the output filename with .mzxML extension
  output_file="$output_dir/${base_filename%.raw}.mzXML" 

  FileConverter -in "$output_file" -out "$output_file_w" -force_MaxQuant_compatibility

  # Print a message indicating the conversion
  echo "Converted $input_file to $output_file"

done
```

## ThermoRawFileParser
Another tool for file conversiong is the ThermoRasFileParser: [Download GUI or command line](http://compomics.github.io/projects/ThermoRawFileParser). There is a full list of [commmands](http://compomics.github.io/projects/ThermoRawFileParser) avaliable as well. 

Which can be ran in the commandline like so. 
```
mono ThermoRawFileParser.exe -i=/home/user/data_input/raw_file.raw # on mac, for windows omit mono
```

Happy parsing! / C 

