# react-native-hms-map-demo

# Contents

1. Introduction
2. Installation Guide
3. Function Definitions
4. Configuration & Description
5. Licencing & Terms

## 1. Intruduction

This module enables communication between Huawei Map SDK and React Native platform. It exposes all functionality provided by Huawei Map SDK.

## 2. Installation Guide

- In order to able the library to be used in the demo, the library should be copied under the node_modules folder of the project.

The structure should be like this

            hms-map-demo
                |_ node_modules
                    |_ ...
                        react-native-hms-map
                        ...

- Add following lines into 'android/settings.gradle' file

```gradle
include ':react-native-hms-map'
project(':react-native-hms-map').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-hms-map/android')
```

- Add maven repository address and AppGallery Connect service dependencies into 'android/build.gradle' file.

```groovy
maven {url 'https://developer.huawei.com/repo/'}
```

- Add 'react-native-hms-map' dependency into 'android/app/build.gradle' file.

```groovy
  implementation project(":react-native-hms-map")
```

- Put keystore file under 'android/app' folder. Add signing configuration into 'android/app/build.gradle' file.

```groovy
signingConfigs {
        release {
            storeFile file('<keystore>')
            storePassword '<storePassword>'
            keyAlias '<keyAlias>'
            keyPassword '<keyPassword>'
        }

        debug {
            storeFile file('<keystore>')
            storePassword '<storePassword>'
            keyAlias '<keyAlias>'
            keyPassword '<keyPassword>'
        }
    }
    buildTypes {
        debug {
            signingConfig signingConfigs.debug
        }
        release {
            signingConfig signingConfigs.release
            minifyEnabled enableProguardInReleaseBuilds
            proguardFiles getDefaultProguardFile("proguard-android.txt"), "proguard-rules.pro"
        }
    }
```

- Add 'RNHMSMapPackage' to your application.
  
```java
import com.huawei.hms.rn.map.RNHMSMapPackage;
...
...

@Override
protected List<ReactPackage> getPackages() {
  @SuppressWarnings("UnnecessaryLocalVariable")
  List<ReactPackage> packages = new PackageList(this).getPackages();
  packages.add(new RNHMSMapPackage());
  return packages;
}
```

```bash
react-native run-android
```

## 3. Function Definitions

No

## 4. Confuguration & Description

No.

## 5. Licencing & Terms

Apache 2.0 license.
