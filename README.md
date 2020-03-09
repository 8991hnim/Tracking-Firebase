# Tracking-Firebase

### Add the dependency for the Google Analytics Android library to app/build.gradle
```
implementation 'com.google.firebase:firebase-analytics:17.2.3'
```

### Declare the com.google.firebase.analytics.FirebaseAnalytics object at the top of your activity:
```
private FirebaseAnalytics mFirebaseAnalytics;
```

### Initialize it in the onCreate() method:
```
mFirebaseAnalytics = FirebaseAnalytics.getInstance(this);
```

## LOG EVENT
