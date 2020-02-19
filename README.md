# notification_handler

Handle event notifications and provide state for Flutter app.

## Description

Futter provides a mechanism `Notification` to propagate the event
through the widget tree.

Typically, there is a `ScrollNotification` to signal that scrolling has
taken place.

This library provides a way to handle event `Notification`s.

This consolidates business logic and makes it easier to design in
accordance with the BLoC architecture.

## Usage

```dart
int counter = 0;

NotificationHandler<MyNotification, int>(
  initialState: counter,
  builder: (BuildContext context, int state, Widget child) {
    return Text("${state}");
  },
  onEvent: (BuildContext context, MyNotification event) async* {
    counter += 1;
    yield* counter;
  },
);
```
