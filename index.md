## Welcome to SCE Green Button Parser

This python program will parse SCE Green Button csv files.
Green button data from utilities is not always the same format so this is tuned to SCE's net metering format.  Yes, Even SCE has several formats based on customer plan.
If someone provides sample data for other green button formats (including SCE non Net Metering) I will incorporate.  

Looking for contributors that want to change the parsing function to parse their format of data.  Will add a command line option to set which format to parse to. 

## Still in progress - here is what is completed and works

Features
- [X] Parse SCE NetMetering version of Green Button CSV file - Solar
- [X] Send data to influxdb (v1, non-ssl) - should be on private network and not public accessible due to no SSL
- [ ] Grafana dashboard to analyze Energy Delivery and Generation
- [X] Create formatted text file for use in other programs (Formatted for Influxdb)
- [ ] Create simple parsed CSV file for use in excel or other database
- [ ] Add SSL support
- [ ] Add support for influxdb2

## Program Setup 
- python3
- make sure the following libraries are install using pip3 or homebrew
  - influxdb
  - json
  - gzip
  - argparse
- Run the program

## Usage
### usage: sceinfluxdb.py [-h] [--version] -f FILE [-n HOSTNAME] [-v] [-q] [-P PORT] [-o] [-b BATCHSIZE]
###                      [--dbname [DBNAME]] [-u [USER]] [-p [PASSWORD]] [-tz TIMEZONE] [--createdb]

Loads SCE Green Button csv file and send formatted results to influxdb.Used for Net Metering format only (solar)

optional arguments:
<br>  -h, --help            show this help message and exit
<br>   --version             display version number
<br>   -f FILE, --file FILE  filename of the sce greenbutton data
<br>   -n HOSTNAME, --hostname HOSTNAME
                        the influxdb host name, no port or http example --host influxdb.mydomain.com
<br>   -v, --verbose         verbose output - send copy of each line to stdout
<br>   -q, --quiet           do not print totals output
<br>   -P PORT, --port PORT  port of the influxdb, if not provided it will default to 8086
<br>   -o, --csvout          sends parsed data to a csvfile. -p can be used or omitted with -o
<br>   -b BATCHSIZE, --batchsize BATCHSIZE
                        Batch size. Default: 5000.
<br>   --dbname [DBNAME]     Database name. Required if -n and -p used
<br>   -u [USER], --user [USER]
                        influxdb userid
<br>   -p [PASSWORD], --password [PASSWORD]
                        Influxdb password
<br>   -tz TIMEZONE, --timezone TIMEZONE
                        Timezone of supplied data. Default: UTC
<br>   --createdb            Drop database and create a new one.

### Support or Contact
Please go to the Github site and post an issue (Feature Requests or bugs) or use the discussion page to ask questions.
    https://github.com/gauthig/sce-greenbutton
