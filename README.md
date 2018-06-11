Simple Linphone SDK for android
===============================
version:<br>
1.0.2<br>
1.0.3<br>
// 添加依赖<br>
----------------
1.工程gradle.allprojects.repositories添加<br>
```
 maven { url "https://github.com/slinphonesdk/lib/raw/master" }
```
2.项目gradle.dependencies添加<br>
```   
 implementation 'com.android:lib:1.0.3'
```
// 示例<br>
----------
```
SLinphoneSDK.init(this,"192.168.88.253", "5060");
SLinphoneSDK.getInstance().addSDKListener(new SLinphoneSDKListener() {
            @Override
            public void serviceIsReady() {
                SLinphoneSDK.register("199998");
            }

            @Override
            public void callState(String s, String s1, String s2) {

            }

            @Override
            public void registrationState(String s, String s1) {

            }
        });
        
        SLinphoneSDK.callOutgoing("19999");//拔打电话
        SLinphoneSDK.acceptCall();//接听电话
        SLinphoneSDK.hangup();//挂断电话
```
