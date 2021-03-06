# TimeOff
Use TimeOff to manage holiday bookings in CMAP

## Get TimeOff
* `* GET v1/TimeOff/all` Returns all the time off 

```javascript
[{ 
	"id" : 234234,
	"actualDays" : 2, 
	"booked" : true, 
	"date" : "2015-07-01", 
	"duration" : 2, 
	"code" : "Holiday",
	"codeId" : 0,
	"notes" : "Some notes about the holiday", 
	"rejected" : true, 
	"requested" : true
}]
```

* `* GET v1/TimeOff` Returns all the time off for the logged in user

```javascript
[{ 
	"id" : 234234,
	"actualDays" : 2, 
	"booked" : true, 
	"date" : "2015-07-01", 
	"duration" : 2, 
	"code" : "Holiday",
	"codeId" : 0,
	"notes" : "Some notes about the holiday", 
	"rejected" : true, 
	"requested" : true
}]
```

* `* GET v1/TimeOff/5` Returns all the time off with the matching id

```javascript
[{ 
	"id" : 5,
	"actualDays" : 2, 
	"booked" : true, 
	"date" : "2015-07-01", 
	"duration" : 2, 
	"code" : "Holiday",
	"codeId" : 0,
	"notes" : "Some notes about the holiday", 
	"rejected" : true, 
	"requested" : true
}]
```

* `* GET v1/TimeOff/allowance` Returns the current years holiday allowance for the logged in user

```javascript
{
	"days" : 25,
	"daysRemaining" : 4,
	"carriedForward" : 3,
	"timeInLieu" = 0,
	"allowances" = [{ "allowance":1, "allowanceRemaing" : 0, "code": "Birthday", "codeId" : 3},
					{"allowance":2, "allowanceRemaing" : 2, "code" : "Family Time", "codeId" : 2}]
}
```

* `* POST v1/TimeOff` Create a new holiday

* `* PUT v1/TimeOff/5` Update a holiday's details

* `* DELETE v1/TimeOff/5` Deletes a holiday

* `* POST v1/TimeOffAllowance` Creates a holiday allowance for a user

```javascript
{
	"UserID":"12345" /* who the entitlement is for */
	"Year":"2020" /* When the entitlement is for */
	"HolidayCodeID":"0" /* This has to be 0 for regular CMAP holidays or the ID of the client specific holiday code */
	"Days":"25" /* number of days for the entitlement */
	"CarriedForward":"0" /* number of days, only relevant for CMAP Holidays */
	"InLieu":"0" /* number of days, only relevant for CMAP Holidays */
}
```


* `* PUT v1/TimeOffAllowance` Updates a holiday allowance for a user

```javascript
{
	"UserID":"12345" /* who the entitlement is for */
	"Year":"2020" /* When the entitlement is for */
	"HolidayCodeID":"0" /* This has to be 0 for regular CMAP holidays or the ID of the client specific holiday code */
	"Days":"25" /* number of days for the entitlement */
	"CarriedForward":"0" /* number of days, only relevant for CMAP Holidays */
	"InLieu":"0" /* number of days, only relevant for CMAP Holidays */
}
```
