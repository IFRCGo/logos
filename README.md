# logos

### National society logo metadata
Each folder should have the following file `national-societies/ISO3_National-Society-Name/README.md` with the following format:
```
## Name of the society in national language
### name of society in English 
Country name - Country iso3 code
URL for national society website

- note
- additional note
```

### Miscellaneous
To auto-generate the national-societies subfolders, I first created a text file with all the variables from existing data as follows:
```plain
AFG,Afghanistan,Afghan-Red-Crescent-Society,Afghan Red Crescent Society
ALB,Albania,Albanian-Red-Cross,Albanian Red Cross
DZA,Algeria,Algerian-Red-Crescent,Algerian Red Crescent
...
```
Then ran:
```bash
OLDIFS=$IFS
IFS=,
while read -r iso country ns1 ns2;do mkdir $iso\_$ns1; echo "## $ns2 \n$country - $iso" > $iso\_$ns1/README.md; done < countries.csv
IFS=$OLDIFS
```