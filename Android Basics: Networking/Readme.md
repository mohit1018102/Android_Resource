# Android Basics: Networking

## Resources

1. places to find APIs include:

2. Programmable Web API Directory: http://www.programmableweb.com/apis/directory

3. Google APIs Explorer: https://developers.google.com/apis-explorer/#p/

4. Data.gov: http://data.gov


# Json Parsing

1. **API: Application Programming Interface :** Application programming interfaces, or APIs, simplify software development and innovation by enabling applications to exchange data and functionality easily and securely.
2. An application programming interface, or API, enables companies to open up their applications’ data and functionality to external     third-party developers, business partners, and internal departments within their companies. 


## Exploring Api : **USGS EarthQuake web Api** : https://earthquake.usgs.gov/fdsnws/event/1/
1. URL : https://earthquake.usgs.gov/fdsnws/event/1/[METHOD[?PARAMETERS]]
2. example: https://earthquake.usgs.gov/fdsnws/event/1/query?starttime=2021-05-02&endtime=2021-05-03&format=geojson&minmagnitude=4.5
3. returns json data.
4. json pretty printer : https://jsonformatter.org/json-pretty-print
5. Parameters
    * mag : magnitude of earthquake.
    * place : where earthquake occurs
    * Time : when earthquake occurs :linux time
    * felt : how strong it felt to people.(survey)
    * tsunami: was there a tsunami alert issued? ->0:no / 1: yes 
    * title : (mag+place)
    * coordinates : where earthquake occurred (log, lat, depth)
