
# react-native-hijri-date-picker-android

## This Module version is originally forked from https://www.npmjs.com/package/react-native-hijri-date-picker-android

## Getting started
### Versions
For React Native >= 0.67.x use v2.0.1
   
`$ npm install react-native-hijri-date-picker-android --save`

### Mostly automatic installation

`$ react-native link react-native-hijri-date-picker-android`

### Manual installation

## Usage
```javascript
//first include HijriDatePickerAndroid
import HijriDatePickerAndroid from "react-native-hijri-date-picker-android";


	let options = { date: new Date(), minDate: new Date(new Date().getTime() - (1 * 30 * 24 * 60 * 60 * 1000)), maxDate: new Date(new Date().getTime() + (1 * 30 * 24 * 60 * 60 * 1000)) };
    let stringOptions = { date: "27-7-1438", minDate: "25-6-1438", maxDate: "29-8-1438" };
	//mode:"no_arrows" hide the arrows at the bar of the calendar
	//weekDayLabels, override the default day labels at the calendar
	let moreOptions = { date: "27-7-1438", minDate: "25-6-1438", maxDate: "29-8-1438", mode:"no_arrows", weekDayLabels:["Sun","Mon","Tue","Wed","Thu","Fri","Sat"]};
    //accepts option  dates with date objects or strings in the following format ['dd-MM-yyyy'] 
    HijriDatePickerAndroid.open(stringOptions).then(function (result) {
      if (result.action == HijriDatePickerAndroid.dismissedAction) {
        console.warn("Dismissed");
      } else {
        let { year, day, month } = result;
        console.warn("Hijri Date: " + day + "/" +( month + 1) + "/" + year + "/");
      }
    });
	
	//convert string Hijri date ['dd-MM-yyyy'] to a gregorian timestamp
    HijriDatePickerAndroid.convertHijriDateToGregorianDate("12-7-1438").then(function (result) {
      console.warn("Gregorian Timestamp" + JSON.stringify(result));

    });


    //convert gregorian date object to hijri {year,month,day}
    HijriDatePickerAndroid.convertGregorianDateToHijriDate(new Date()).then(function ({ year, day, month }) {
      console.warn("Hijri Date: " + day + "/" + month + 1 + "/" + year + "/");

```
  
## Credits

[Assem-Hafez](https://github.com/Assem-Hafez) and [Mohamed-Abbas](https://github.com/Mohamed-Abbas)
[Codelabsys](http://www.codelabsys.com/)

And is based on the following projects, [material-hijri-calendarview](https://github.com/eltohamy/material-hijri-calendarview) and [ummalqura-calendar](https://github.com/msarhan/ummalqura-calendar)
