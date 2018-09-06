Simple Linphone SDK for android
===============================
* version:<br>
* 1.1.1.4<br>
---------------------
new: 删除UI文件
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
