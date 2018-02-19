# logos
*The process of uploading available logos is still a work in progress. Thank you for your patience.*

## Finding a logo

National society logos are contained within the `national-societies` folder inside folders named using the country's iso3 code and English version of their society name. For example `national-societies/AFG_Afghan-Red-Crescent-Society/`. Each folder has a `README.md` file that will contain any available information about the provided logo(s).

You can also search using the box in the top left of the browser window. Your search will likely return a README file.

<img width="600" alt="search-result" src="https://raw.githubusercontent.com/IFRCGo/logos/master/readme-imgs/search-result.png">

When you click the link, it will take you to the file itself. In the navigation links click the link to the folder itself that is the left of `/README.md`. In the screen shot below you would click the `ITA_Italian-Red-Cross` link.

<img width="600" alt="readme-file" src="https://raw.githubusercontent.com/IFRCGo/logos/master/readme-imgs/readme-file.png">

This will take you to the folder itself. Eventually we hope to have both raster (`.jpg`, `.jpeg`, `.png`, etc.) and vector versions (`.svg`, `.eps`, `.ai`) of all the logos. In the screen shot below the only available logo file is `Croce Rossa Italiana.eps`. 

<img width="600" alt="logo-folder" src="https://raw.githubusercontent.com/IFRCGo/logos/master/readme-imgs/logo-folder.png">

Click the desired file and then look for the "Download" button.

<img width="450" alt="download-button" src="https://raw.githubusercontent.com/IFRCGo/logos/master/readme-imgs/download-button.png">

You can also download the entire resource by clicking the green "Clone or download" button on this page and choosing the "[Download ZIP](https://github.com/IFRCGo/logos/archive/master.zip)" option.

<img width="450" alt="download-zip" src="https://raw.githubusercontent.com/IFRCGo/logos/master/readme-imgs/download-zip.png">


## Contributing

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
