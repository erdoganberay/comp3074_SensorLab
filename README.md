## Reflection Questions

1. Why must `getDefaultSensor()` be treated as potentially returning `null`?

   **Answer:** Not every device has every sensor, so getDefaultSensor() returns null when one is missing. Using it without a check would crash the app.

2. Why should sensor listeners be unregistered when the activity is paused?

   **Answer:** To save battery and CPU. The sensors keep running while a listener is registered, even when the app isn’t visible.

3. What is the difference between gyroscope angular velocity and device orientation?

   **Answer:** Angular velocity is how fast the phone is rotating. Orientation is which way it’s pointing. A phone held still reads 0 on the gyroscope at any angle

4. What units are used for the gyroscope values in this lab?

   **Answer:** Radians per second (rad/s).

5. Why is battery temperature not a valid replacement for `TYPE_AMBIENT_TEMPERATURE`?

   **Answer:** It measures the battery inside the phone, which is heated by charging and use, not the surrounding air.

6. How does `mutableStateOf` allow a `SensorEvent` callback to update the Compose UI?

   **Answer:** Compose tracks which composables read the state. When onSensorChanged() changes the value, those composables recompose automatically.
