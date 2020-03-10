# Tracking-Firebase
Cách gắn tracking firebase

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
```
mFirebaseAnalytics.logEvent("Tên Event", new Bundle());
```

Có thể truyền thêm thông tin vào bundle để log sự kiện chi tiết hơn (chưa cần dùng đến)
```
Bundle params = new Bundle();
params.putString("image_name", name);
params.putString("full_text", text);
mFirebaseAnalytics.logEvent("Tên Event", params);
```
