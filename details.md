```csh

cp ~/Dropbox/Unige_2022/divers/Et-16.mol ./data/
cp ~/Dropbox/Unige_2022/divers/Et-16.jdx ./data/
cp ~/Dropbox/Unige_2022/archive/27* ./data/

cat ./data/Et-16.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g 
cat ./data/27_benzaldehyde.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g 
cat ./data/27_AcCinnamique.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g 
```
