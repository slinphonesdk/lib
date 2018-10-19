Simple Linphone SDK for android
===============================
* version:<br>
* 1.1.1.9<br>
---------------------
new: 版本回归，优化
---------------------
// 添加依赖<br>
----------------
1.工程gradle.allprojects.repositories添加<br>
```
 maven { url "https://github.com/slinphonesdk/lib/raw/master" }
```
2.项目gradle.dependencies添加<br>
```   
 implementation 'com.android:lib:1.0.7'
```
权限
----
```
 <!-- Permissions for Push Notification -->
    <permission android:name="com.lituo.linphone.permission.C2D_MESSAGE" android:protectionLevel="signature" /> <!-- Change package ! -->
    <uses-permission android:name="com.lituo.linphone.permission.C2D_MESSAGE" />  <!-- Change package ! -->
    <uses-permission android:name="com.google.android.c2dm.permission.RECEIVE" />

    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.RECORD_AUDIO"/>
    <uses-permission android:name="android.permission.READ_CONTACTS"/>
    <uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS"/>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
    <uses-permission android:name="android.permission.WAKE_LOCK"/>
    <uses-permission android:name="android.permission.PROCESS_OUTGOING_CALLS"/>
    <uses-permission android:name="android.permission.CALL_PHONE"/>
    <!-- Needed to allow Linphone to install on tablets, since android.permission.CALL_PHONE implies android.hardware.telephony is required -->
    <uses-feature 	 android:name="android.hardware.telephony" android:required="false" />
    <uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED"/>
    <uses-permission android:name="android.permission.VIBRATE"/>
    <uses-permission android:name="android.permission.CAMERA" />
    <!-- Needed to allow Linphone to install on tablets, since android.permission.CAMERA implies android.hardware.camera and android.hardware.camera.autofocus are required -->
    <uses-feature 	 android:name="android.hardware.camera" android:required="false" />
    <uses-permission android:name="android.permission.READ_PHONE_STATE" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
    <!-- Needed to store received images if the user wants to -->
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
    <!-- Needed to use our own Contact editor -->
    <uses-permission android:name="android.permission.WRITE_CONTACTS"/>
    <!-- Needed to route the audio to the bluetooth headset if available -->
    <uses-permission android:name="android.permission.BLUETOOTH" />
    <uses-permission android:name="android.permission.BROADCAST_STICKY" />
    <!-- Needed to pre fill the wizard email field (only if enabled in custom settings) -->
    <uses-permission android:name="android.permission.GET_ACCOUNTS" />
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
    <uses-permission android:name="android.permission.CHANGE_WIFI_MULTICAST_STATE"/>
    <uses-permission android:name="android.permission.READ_SYNC_SETTINGS"/>
    <uses-permission android:name="android.permission.WRITE_SYNC_SETTINGS"/>
    <uses-permission android:name="android.permission.AUTHENTICATE_ACCOUNTS"/>
    <!-- Needed for in-app purchase -->
    <uses-permission android:name="com.android.vending.BILLING" />
    <!-- Needed for overlay widget -->
    <uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"/>
```
// 示例<br>
----------
```
sLinPhoneSDK = new SLinPhoneSDK(this, ipEt.getText().toString().trim(), 5060, new RLinkPhoneListener() {
            @Override
            public void callState(String from, int state, String s) {
                regMsg = s;
                updateUI();
            }

            @Override
            public void registrationState(String state, String s) {
                stateTv.setText("  注册状态: "+state);
            }
        });
        sLinPhoneSDK.register("100100");
        sLinPhoneSDK.isAutoAnswer(false);
```
