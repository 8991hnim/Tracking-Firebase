# Tracking-Firebase
Cách gắn tracking firebase

### Copy file google-services.json (bên MKT sẽ cung cấp) vào package app
Ví dụ với app có tên HighlightStory thì đường dẫn sẽ như sau <br>
E:\AndroidStudioProjects\HighlightStory\app

### Setup firebase
#### Trong build.gradle(project)
```
buildscript {

  repositories {
    // Kiểm tra xem có dòng này chưa, nếu chưa thêm vào
    google()  // Google's Maven repository
  }

  dependencies {
    // ...

    // Thêm dòng này
    classpath 'com.google.gms:google-services:4.3.3'  // Google Services plugin
  }
}

allprojects {
  // ...

  repositories {
    // Kiểm tra xem có dòng này chưa, nếu chưa thêm vào
    google()  // Google's Maven repository
    // ...
  }
}
```
#### Trong build.gradle(app)
```
apply plugin: 'com.android.application'
// Thêm dòng này:
apply plugin: 'com.google.gms.google-services'  // Google Services plugin

android {
  // ...
}
```

### Thêm dependency Google Analytics Android vào app/build.gradle
```
implementation 'com.google.firebase:firebase-analytics:17.2.3'
```

### Khai báo com.google.firebase.analytics.FirebaseAnalytics:
```
private FirebaseAnalytics mFirebaseAnalytics;
```

### Khởi tạo nó bên trong the onCreate() method:
```
mFirebaseAnalytics = FirebaseAnalytics.getInstance(this);
```

## LOG EVENT
Lưu ý: Tên event phải < 40 kí tự

```
mFirebaseAnalytics.logEvent("Tên Event", new Bundle());
```

Có thể truyền thêm thông tin vào bundle để log sự kiện chi tiết hơn (chưa cần dùng đến, đang test lại)
```
Bundle params = new Bundle();
params.putString("image_name", name);
params.putString("full_text", text);
mFirebaseAnalytics.logEvent("Tên Event", params);
```
