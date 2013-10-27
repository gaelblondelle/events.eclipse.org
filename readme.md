# Eclipse Events Page

The code implements the [Eclipse Foundation events](http//events.eclipse.org)

Author: Angelika Wittek, Konteno <br>
inspired by work from Christoper Guindon, Eclipse Foundation

Published under the EPL

Requirements: Ralph Mueller, Eclipse Foundation

Prereqs:<br>
* eclipse.org-commons
* Eclipse page boilerplate

Uses external libraries: <br>
* leafletjs
* jQuery

## How-to

### Download content to your local machine

    $ git clone https://(yourname)@git.eclipse.org/r/websites/events.eclipse.org

### Using git on your local machine

make your changes and commit <br>

    $ vi data/EclipseEvents.json
    $ git add .
    $ git commit -m"commit comments"

### Push changes to Eclipse Foundation git/Gerrit

    git push https://(rmueller)yourname)@git.eclipse.org/r/websites/events.eclipse.org HEAD:refs/for/master

Once you have pushed your changes to Gerrit, they will get reviewed and eventually pushed to the site. 

## Copy and edit template for new event entries in the Jason File

file location: data/EclipseEvents.json

Copy text below and insert into JSON file 
If you insert the last entry in the file, ommit the trailing comma

Replace the second part of each pair with the appropriate information, 

Look up the geo data (longitude and latitude) based on the address. You can use for example this [geocoder](http://www.gpsvisualizer.com/geocode)

The order of appearance in the listing is currently based on the position in the file. In the near future, we will add functionality to automatically sort events and ommit past events. <br>
To help us, please use the "MMM DD, YYYY" format for the "date" fields. Example: "Nov 3, 2013" will work just fine! <br>
We hope to find a more general solution in the future.We are not using the time for anything (yet), so feel free to add the time in any fomrat that is appropriate.


    {
        "type":"dc",
	    "title":"title",
        "date":"date",
        "time":"time",
        "locationName":"location",
        "registration":"reglink",
        "infoLink":"infolink",
        "description":"description",
        "address":{
            "street":"street",
            "zip":"zip",
            "city":"citiy",
            "country": "country",
            "geoLoc":{
                "lat":"00",
                "lon":"00"
            }
        }
    },