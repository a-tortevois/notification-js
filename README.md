# notification.js

Notifications are often used as tooltips/popups to show a message on the screen.
notification.js is the easiest and lightest notification handler to do this.

1. To make Notification.js work, you must call for a new notification handler. Attach this handler preferably to the main container of your app:
```js
const notification = new Notification().appendTo('#container');
```

2. Now the handler is set, you can call for new notifications anywhere, at any time using the following calls:
```js
notification.add(Notification.INFO, 'Notification info example', 2500);
notification.add(Notification.ERROR, 'Notification error example', 2500);
notification.add(Notification.SUCCESS, 'Notification success example', 2500);
notification.add(Notification.WARNING, 'Notification warning example', 2500);
```
Notification will disappear automatically with an internal timeout (the third parameter).

3. Notification should also will be removed by an external event:
```js
const info = notification.add(Notification.INFO, 'Notification info example');
setTimeout(() => {
    notification.remove(info);
}, 2500);
```