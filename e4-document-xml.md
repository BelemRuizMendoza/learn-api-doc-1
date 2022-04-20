# Exercise 4: document XML files
## Part 1: request to record a TV program
```xml
<recordTV>
    <date>2015-06-01</date>
    <time format="24">18:00</time>
    <duration>1.5</duration>
    <channel>54</channel>
</recordTV>
```
Represents the request to record a television program.  
|Element|Description|Type|Required|Notes|
|:------|:----------|:--:|:------:|:----|
|**`recordTV`**|Top level. Contains data about which station will transmit the program to be recorded and when.|data about the TV program|required|The following elements in the table belong to this top level element.|
|`date`|The date when the program will be transmitted.|string|Optional. **Default:** date of the record request.|**Format:** YYYY-MM-DD.|
|`time`|The time when the transmission of the program will start.|string|required|**Attribute:** `format`, refers to the hour format and its valid values are "12" or "24". **Format:** HH:MM; adds AM or PM to the 12-hours format.|
|`duration`|How many hours the program transmission will last.|number|required||
|`channel`|The channel to record.|number|required||
<br><br>

## Part 2: different TV request
```xml
<recordTV>
    <when date="2015-06-01" time="18:00" format="24"/>
    <duration hours="1.5"/>
    <station channel="54"/>
</recordTV>
```
Represents the request to record a television program.  
|Element|Attribute|Description|Type|Required|Notes|
|:------|:--------|:----------|:--:|:------:|:----|
|**`recordTV`**||Top level. Contains data about which station will transmit the program to be recorded and when.|data about the TV program|required|The following elements in the table belong to this top level element.|
|`when`||The date and time when the program will be transmitted.|Date and time data.|required||
||`date`|The date when the program will be transmitted.|string|Optional. **Default:** date of the record request.|**Format:** YYYY-MM-DD.|
||`time`|The time when the transmission of the program will start.|string|required|**Format:** HH:MM; adds AM or PM to the 12 hours format.|
||`format`|The time format, either 12 or 24 hours format.|number|required|**Valid values:** "12" or "24".|
|`duration`||The program lenght.|number data|required||
||`hours`|How many hours the program transmission will last.|number|required||
|`station`||station data|required||
||`channel`|The channel to record.|number|required||
<br><br>

## Part 3: temperature and humidity
```xml
<dailyData>
    <date>2015-06-01</date>
    <hourlyData>
        <time>10:00</time>
        <device>
            <id>34</id>
            <temperature>70</temperature>
            <humidity>11</humidity>
        </device>
        <device>
            <id>35</id>
            <temperature>72</temperature>
            <humidity>12</humidity>
        </device>
...
    </hourlyData>
    <hourlyData>
       <time>11:00</time>
      <device>
           <id>34</id>
           <temperature>71</temperature>
          <humidity>10</humidity>
       </device>
...
    </hourlyData>
...
</dailyData>
```  
### Top level.
|Element|Description|Type|
|:------|:----------|:--:|
|`dailyData`|Temperature and humidity data for one day.|`dailyData` element.|
<br>

### `dailyData`: Represents temperature and humidity data for one day.
|Element|Description|Type|Notes|
|:------|:----------|:--:|:----|
|`date`|The date when the temperature and humidity data was taken.|string|**Format:** YYYY-MM-DD..|
|`hourlyData`|Temperature and humidity data corresponding to one hour.|`hourlyData` element.||
<br>

### `hourlyData`: Represents temperature and humidity data for one hour.
|Element|Description|Type|Notes|
|:------|:----------|:--:|:----|
|`time`|The local time when the data was taken.|string|**Format:** HH:MM.|
|`device`|One or more device objects with data from each device.|`device` element.||
<br>

### `device`: Contains temperature and humidity data from a device
|Element|Description|Type|
|:------|:----------|:--:|
|`id`|The ID of the device.|number|
|`temperature`|The measured temperature, in degrees Fahrenheit.|number|
|`humidity`|The measured humidity, in percentage.|number|
<br><br><br>

Exercise 4 from this [course].

[course]: https://www.udemy.com/course/api-documentation-1-json-and-xml/