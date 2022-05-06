This repository provides simple access to the files locates in the ./data folder and shows how to make them accessible to NMRium

Example of file located at [https://chemedata.github.io/dataServer/data/Et-16.jdx](https://chemedata.github.io/dataServer/data/Et-16.jdx).


Get the files using:
```
wget https://chemedata.github.io/dataServer/data/Et-16.jdx
```

## Applications

Paste the url of the file after "https://www.nmrium.org/nmrium#?" to open it with automatically in NMRium : [https://www.nmrium.org/nmrium#?jcamp=https://chemedata.github.io/dataServer/data/Et-16.jdx](https://www.nmrium.org/nmrium#?jcamp=https://chemedata.github.io/dataServer/data/Et-16.jdx)


### Combine spectrum and molecule manually in NMRium

After drag-drop of the spectrum and the structure, the .nmrium files were stored using "save as..." in [./data/nmrium-data]{./data/nmrium-data} using the twp options:

- "Raw Data" includes the spectrum is self-consistent
- "Data source" including a link to the spectrum instead of the spectrum itself, making the file smaller and more appropriate for data versioning.


The nmrium files can be opened as :
- [Raw Data](https://www.nmrium.org/nmrium#?nmrium=https://chemedata.github.io/dataServer/data/nmrium-data/F6zMXRFW_dataSource.nmrium)
- [Data source](https://www.nmrium.org/nmrium#?nmrium=https://chemedata.github.io/dataServer/data/nmrium-data/F6zMXRFWRaw_Data.nmrium)

### Combine spectrum and molecule using json files

#### 1) Create a table of content in ./data/nmrium-data/index.json:
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
where more spectra can be follow the braces. Only one should have `"selected": true`.

#### 2) Create the Et-16.json file:
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

#### 3) Transform .mol and .sdf files into single-line string using:
```csh
cat ./data/Et-16.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g
```
and paste it as the "molfile" in the json above.


[Open the table of content in NMRium](https://www.nmrium.org/nmrium#?toc=https://chemedata.github.io/dataServer/data/nmrium-data/index.json)

All this could be automatized...
### More information

More details about the format in [https://docs.nmrium.org/for-developers/using-nmrium]{https://docs.nmrium.org/for-developers/using-nmrium}

