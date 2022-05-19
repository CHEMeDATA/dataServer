---
title: More Info
permalink: /moreInfo/
---
This repository provides simple access to the files locates in the ./data folder and shows how to make them accessible to NMRium

Example of file located at [https://chemedata.github.io/dataServer/data/Et-16.jdx](https://chemedata.github.io/dataServer/data/Et-16.jdx).

Get the files using:
```
wget https://chemedata.github.io/dataServer/data/Et-16.jdx
```

## Applications

Paste the url of the file after "https://www.nmrium.org/nmrium#?" to open it automatically in NMRium. The full URL looks like this : [https://www.nmrium.org/nmrium#?jcamp=https://chemedata.github.io/dataServer/data/Et-16.jdx](https://www.nmrium.org/nmrium#?jcamp=https://chemedata.github.io/dataServer/data/Et-16.jdx)


### Combine spectrum and molecule manually in NMRium

After drag-drop of the spectrum and the structure, the .nmrium files were stored using "save as..." in [./data/nmrium-data]{./data/nmrium-data} using the two options:

- "Raw Data" includes the spectrum is self-consistent
- "Data source" including a link to the spectrum instead of the spectrum itself, making the file smaller and more appropriate for data versioning.


The nmrium files can be opened as :
- [Data source](https://www.nmrium.org/nmrium#?nmrium=https://chemedata.github.io/dataServer/data/nmrium-data/F6zMXRFW_dataSource.nmrium)
- [Raw Data](https://www.nmrium.org/nmrium#?nmrium=https://chemedata.github.io/dataServer/data/nmrium-data/F6zMXRFWRaw_Data.nmrium)

### Combine spectrum and molecule using json files

This methods allows NMRium to display a list of spectra by pointing to a table-of-content file.
#### 1) Create a table of content in ./data/nmrium-data/index.json:

Structure of the file. A complete example can be found there: [./data/nmrium-data/index.json](./data/nmrium-data/index.json).
```
[
	{
	  "file": "./Et-16.json",
      "title": "1-ethoxybutane",
	   "view": "",
	   "selected": true  
	}
]
```

Only one should have a field `"selected": true` - it will be one that opens by default when landing on the [table-of-content page](https://www.nmrium.org/nmrium#?toc=https://chemedata.github.io/dataServer/data/nmrium-data/index.json).

#### 2) Create the Et-16.json file:

For each spectrum, create the json including a pointer to the spectrum, and the content of the molecular structure file (.mol / .sdf).
```
{
	"spectra": [
		{
			"data": {},
			"id": "0abwvynpah97",
			"source": {
				"original": [],
				"jcamp": null,
				"jcampURL": "../Et-16.jdx"
			},
			"display": {
				"name": "1-ethoxybutane",
				"color": "#C10020"
			}
		}
	],
	"molecules": [
		{
			"molfile": "\r\n  Mnova   05062209502D\r\n\r\n  7  6  0  0  0  0  0  0  0  0999 V2000\r\n  -13.6404  -93.9146    0.0000 C   0  0  0  0  0  0  0  0  0  0  0  0\r\n   -3.1005 -100.0000    0.0000 C   0  0  0  0  0  0  0  0  0  0  0  0\r\n    7.4407  -93.9146    0.0000 C   0  0  0  0  0  0  0  0  0  0  0  0\r\n   17.9807 -100.0000    0.0000 C   0  0  0  0  0  0  0  0  0  0  0  0\r\n   28.5207  -93.9146    0.0000 O   0  0  0  0  0  0  0  0  0  0  0  0\r\n   39.0607 -100.0000    0.0000 C   0  0  0  0  0  0  0  0  0  0  0  0\r\n   49.6019  -93.9146    0.0000 C   0  0  0  0  0  0  0  0  0  0  0  0\r\n  5  6  1  0  0  0  0\r\n  4  5  1  0  0  0  0\r\n  3  4  1  0  0  0  0\r\n  2  3  1  0  0  0  0\r\n  1  2  1  0  0  0  0\r\n  6  7  1  0  0  0  0\r\nM  END\r\n"
		}
	]
}
```
#### 3) Generate the molfile string

In a shell, transform .mol and .sdf files into single-line strings with :
```csh
cat ./data/Et-16.mol | tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g
```
Paste the output as the "molfile" value in the .json files.

### Automation

The generation of mol/sdf files can be done by exporting data from chemical structure editors such as ChemDraw, or Mnova or chemistry software libraries such as oben babel, etc.

The generation of .jdx files can be done by exporting spectra from NMR software such as Topspin, Mnova, or chemistry software libraries or on-line tools.

The whole process could be automatized.
### More information

More details about the format for [NMRium](https://docs.nmrium.org/for-developers/using-nmrium)

Other types of dataset: https://cheminfo.github.io/nmr-dataset3 with generator of table of content.

[Commands to generate data automatically](./details.md)