# dataServer
Mini file server

The repository provides simple access to the files in the data folder.

Example of file located at https://chemedata.github.io/dataServer/data/Et-16.jdx:
```
wget https://chemedata.github.io/dataServer/data/Et-16.jdx
wget https://chemedata.github.io/dataServer/data/Et-16.mol
```

# Applications

Give access to NMRium files:

https://www.nmrium.org/nmrium#?jcamp=https://chemedata.github.io/dataServer/data/Et-16.jdx

After drag-drop of the structure and saving in diverse format stored in ./data/nmrium-data
https://github.com/CHEMeDATA/dataServer/blob/main/data/nmrium-data/F6zMXRFW_default_save.nmrium
They can be opened with

https://www.nmrium.org/nmrium#?nmrium=https://chemedata.github.io/dataServer/data/nmrium-data/F6zMXRFW_default_save.nmrium