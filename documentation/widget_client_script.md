#### Client Script
This is the controller already linked to the widget. Consider every widget to be an Angular directive – you define the controller for that directive here. This is where you handle all the client-side logic and template binding for your widget.
```javascript
function() {	
	var c = this;
	c.update = function() {
		c.data.price = false;
		c.server.get({symbol: c.data.symbol}).then(function(r) {			
			c.data.price = r.data.price;			
		});
	}
}
```

| Property | Description |
| :------ | :----------- |
| `this.server.get([Object])`  | Calls the server and sends custom `input`. Returns `Promise`. |
| `this.server.update()` | Calls the server and `this.data` is automatically send to server side. Returns `Promise`. |
| `this.server.refresh() `   | Calls the server and automatically replaces the current options and data from the server response. Returns `Promise` |


To initialize all of the variables available to the client script, you can pass in the following to the first line of the client script function:
```javascript
function($scope, spUtil, $location, $timeout, $window, $rootScope, $uibModal, spPreference) {
```
(TODO: add table detailing each variable/correct what I'm wrong on)
| Property | Description |
| :------ | :----------- |
| `$scope` | ... |
| `spUtil` | ... |
| `$location` | ... |
| `$timeout` | ... |
| `$window` | ... |
| `$rootScope` | ... |
| `$uidModal` | ... |
| `spPreference` | ... |
