---
title: Details
permalink: /details/
---
```csh

cp ~/Dropbox/Unige_2022/divers/Et-16.mol ./data/
cp ~/Dropbox/Unige_2022/divers/Et-16.jdx ./data/
cp ~/Dropbox/Unige_2022/archive/27* ./data/
cp ~/Dropbox/Unige_2022/archive/p19.jdx ./data/
cp ~/Dropbox/Unige_2022/archive/p19.mol ./data/
cp ~/Dropbox/Unige_2022/archive/p21.mol ./data/
cp ~/Dropbox/Unige_2022/archive/p21.jdx ./data/

cat ./data/Et-16.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g 
cat ./data/27_benzaldehyde.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g 
cat ./data/27_AcCinnamique.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g 
cat ./data/p19.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g 
cat ./data/p21.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g 

cp ./data/nmrium-data/27_benzaldehyde.json ./data/nmrium-data/19_anhydrideDimethylTetrahydrophtalique.json
cp ./data/nmrium-data/27_benzaldehyde.json ./data/nmrium-data/21_ethylBenzene.json

```
