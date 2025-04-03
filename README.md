GeoIP
=====

Dependencies
---------------
* PrettyTable - https://code.google.com/p/prettytable
* MaxMind GeoIP - https://github.com/maxmind/geoip-api-python

Install Dependencies
---------------
```
apt install libgeoip-dev
pip install setuptools
pip install prettytable
wget https://github.com/maxmind/geoip-api-python/archive/refs/heads/main.zip
unzip main.zip
cd ./geoip-api-python-main/
python setup.py build
python setup.py install
```

Usage
-----
Single IP Lookup: 
```
$ python geoip.py 192.30.252.128
IP Address: 192.30.252.128
AS Number: 36459
AS Name: GitHub, Inc.
City: San Francisco
Region: California
Country: United States
Country Code: US
Latitude: 37.7696990967
Longitude: -122.393302917
```
Multiple IP Lookup (Table or CSV):
```
$ python geoip.py -f iplist.txt -t
+----------------+-----------+--------------+---------------+------------+---------------+--------------+---------------+----------------+
|   IP Address   | AS Number |   AS Name    |      City     |   Region   |    Country    | Country Code |    Latitude   |   Longitude    |
+----------------+-----------+--------------+---------------+------------+---------------+--------------+---------------+----------------+
| 192.30.252.128 |   36459   | GitHub, Inc. | San Francisco | California | United States |      US      | 37.7696990967 | -122.393302917 |
| 74.125.239.131 |   15169   | Google Inc.  | Mountain View | California | United States |      US      | 37.4192008972 | -122.057403564 |
| 98.139.183.24  |   26101   |    Yahoo!    |   Sunnyvale   | California | United States |      US      | 37.4249000549 | -122.007400513 |
+----------------+-----------+--------------+---------------+------------+---------------+--------------+---------------+----------------+
```
```
$ python geoip.py -f iplist.txt -c
IP Address,AS Number,AS Name,City,Region,Country,Country Code,Latitude,Longitude
192.30.252.128,36459,GitHub, Inc.,San Francisco,California,United States,US,37.7696990967,-122.393302917
74.125.239.131,15169,Google Inc.,Mountain View,California,United States,US,37.4192008972,-122.057403564
98.139.183.24,26101,Yahoo!,Sunnyvale,California,United States,US,37.4249000549,-122.007400513
```
