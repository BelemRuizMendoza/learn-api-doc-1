# JSON exercise 2: document JSON files
## Step 1: one day's forecast

```json
{
"date": "2015-09-01",
"description": "sunny",
"maxTemp": 22,
"minTemp": 20,
"windSpeed": 12,
"danger": false
}
```
Displays the weather forecast for the specified day.  
|Element|Description|Type|Notes|
|:------|:----------|:--:|:----|
|`date`|The date of the forecast.|string|Format is YYYY-MM-DD.|
|`description`|One-word description of the weather.|string|**Valid values:** "sunny", "overcast", "cloudy", "raining", and "snowing".|
|`maxTemp`|The maximum expected temperature for the day.|number|In degrees Celsius.|
|`minTemp`|The minimum expected temperature for the day.|number|In degrees Celsius.|
|`windSpeed`|The expected speed of the wind for the day.|number|In kilometers per hour.|
|`danger`|The warning is `true` if the weather conditions are dangerous; otherwise, `false`.|boolean||
<br><br>

## Step 2: three-day forecast

```json
{
"longitude": 47.60,
"latitude": 122.33,
"forecasts": [
    {
    "date": "2015-09-01",
    "description": "sunny",
    "maxTemp": 22,
    "minTemp": 20,
    "windSpeed": 12,
    "danger": false
    },
    {
    "date": "2015-09-02",
    "description": "overcast",
    "maxTemp": 21,
    "minTemp": 17,
    "windSpeed": 15,
    "danger": false
    },
    {
    "date": "2015-09-03",
    "description": "raining",
    "maxTemp": 20,
    "minTemp": 18,
    "windSpeed": 13,
    "danger": false
    }
]
}
```
Displays the weather forecast for the specified days.  
|Element|Description|Type|Notes|
|:------|:----------|:--:|:----|
|`longitude`|The longitude of the location where the forecast focuses.|number||
|`latitude`|The longitude of the location where the forecast focuses.|number||
|**`forecasts`**|Top level. The daily forecasts for the specified days.|array of daily forecast objects|The following elements belong to **`forecasts`**: `date`, `description`, `maxTemp`, `minTemp`, `windSpeed`, `danger`.|
|`date`|The date of the forecast.|string|**Format:** YYYY-MM-DD.|
|`description`|One-word description of the weather.|string|**Valid values:** "sunny", "overcast", "cloudy", "raining", and "snowing".|
|`maxTemp`|The maximum expected temperature for the day.|number|In degrees Celsius.|
|`minTemp`|The minimum expected temperature for the day.|number|In degrees Celsius.|
|`windSpeed`|The expected speed of the wind for the day.|number|In kilometers per hour.|
|`danger`|The warning is `true` if the weather conditions are dangerous; otherwise, `false`.|boolean||
<br><br>

## Step 3: meeting request

```json
{
"meeting" : {
    "time": "2015-09-01 10:00",
    "duration": 60,
    "description": "2016 Strategic Planning Meeting",
    "location": "Building 23, Room 206",
    "reminder": 15,
    "invitees": ["michael@example.com", "thelma@example.com",
    "david@example.com", "leon@example.com"]
    }
}
```
Represents a meeting request in a calendar.
|Element|Description|Type|Required|Notes|
|:------|:----------|:--:|:------:|:----|
|`meeting`|Top level.|meeting data object|required||
|`time`|Starting time for the meeting. In GMT timezone.|number|required|**Format:** YYYY-MM-DD HH-MM.|
|`duration`|Planned duration for the meeting. In minutes.|number|required||
|`description`|A description for the meeting.|string|required||
|`location`|Through which platform is the meeting to occur.|string|optional|**Default:** empty string.|
|`reminder`|How many minutes before the meeting a reminder must be sent to the invitee(s) and organizer.|number|optional|**Default:** 10 minutes.|
|`invitees`|A list of email address(es) of the invitee(s) to the meeting.|array of string|optional|The email addresses must be valid. **Default:** empty array.|
<br><br><br>
***
Exercise 2 from this [course].

[course]: https://www.udemy.com/course/api-documentation-1-json-and-xml/