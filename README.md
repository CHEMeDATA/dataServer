# dataServer
Mini file server

https://chemedata.github.io/dataServer

The repository provides simple access to the files in the data folder.

Example of file located at https://chemedata.github.io/dataServer/data/Et-16.jdx. 
Get the files using:
```
wget https://chemedata.github.io/dataServer/data/Et-16.jdx
wget https://chemedata.github.io/dataServer/data/Et-16.mol
```

# Applications

Give access to a file : [https://chemedata.github.io/dataServer/data/Et-16.jdx](jcamp=https://chemedata.github.io/dataServer/data/Et-16.jdx)

Open it [in NMRium](https://www.nmrium.org/nmrium#?jcamp=https://chemedata.github.io/dataServer/data/Et-16.jdx)
# Combine spectrum and molecule in NMRium

After drag-drop of the structure and saving in diverse format stored in [./data/nmrium-data]{./data/nmrium-data}

They can be opened with :
- [data source export](https://www.nmrium.org/nmrium#?nmrium=https://chemedata.github.io/dataServer/data/nmrium-data/F6zMXRFW_dataSource.nmrium)

- [Raw data export](https://www.nmrium.org/nmrium#?nmrium=https://chemedata.github.io/dataServer/data/nmrium-data/F6zMXRFWRaw_Data.nmrium)

# Combine spectrum and molecule using json files

1) create a toc json file:
```
[
	{
	  "file": "./data/nmrium-data/Et-16.json",
      "title": "artemisin",
	   "view": "",
	   "selected": true  
	}
]
```

2) create the Et-16.json file:
```
[
	{
	  "file": "./data/nmrium-data/Et-16.json",
      "title": "artemisin",
	   "view": "",
	   "selected": true  
	}
]
```

access using : 

They can be opened with [remote link](https://www.nmrium.org/nmrium#?toc=https://chemedata.github.io/dataServer/data/nmrium-data/Et.json)

They can be opened with [local link](https://www.nmrium.org/nmrium#?toc=./data/nmrium-data/Et.json)

more details in  [https://docs.nmrium.org/for-developers/using-nmrium]{https://docs.nmrium.org/for-developers/using-nmrium}


```csh
cat ./data/Et-16.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g
```