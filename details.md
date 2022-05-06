```csh

cp ~/Dropbox/Unige_2022/divers/Et-16.mol ./data/
cp ~/Dropbox/Unige_2022/divers/Et-16.jdx ./data/

cat ./data/Et-16.mol |tr  '\r\n' '__' | sed s/"__"/'\\r\\n'/g 
```
