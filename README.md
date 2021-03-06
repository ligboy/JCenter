# JCenter

### Example
#### Module build.gradle  
````gradle
apply plugin: 'com.android.library'
ext {
    bintrayRepo = 'maven'
    bintrayName = 'Preference'

    libraryGroupId = 'org.ligboy.library'
    libraryArtifactId = 'preference'
    libraryVersion = '0.1.0'

    libraryName = 'Android Preference Support Extionsion'
    libraryDescription = 'Android Preference Support Extionsion'

    siteUrl = 'https://github.com/ligboy/Preference'
    gitUrl = 'https://github.com/ligboy/Preference.git'

    developerId = 'ligboy'
    developerName = 'Ligboy Liu'
    developerEmail = 'ligboy@gmail.com'

    licenseName = 'The Apache Software License, Version 2.0'
    licenseUrl = 'http://www.apache.org/licenses/LICENSE-2.0.txt'
    allLicenses = ["Apache-2.0"]

    failOnJavadocError = false
}
android {
    compileSdkVersion 23
    buildToolsVersion '23.0.2'

    defaultConfig {
        minSdkVersion 14
        targetSdkVersion 23
        versionCode 1
        versionName libraryVersion
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }
}
ext {
    supportVersion = '23.1.1'
}
dependencies {
    compile fileTree(include: ['*.jar'], dir: 'libs')
    compile "com.android.support:appcompat-v7:${supportVersion}"
    compile "com.android.support:preference-v14:${supportVersion}"
    compile "com.android.support:support-v13:${supportVersion}"
    compile "com.android.support:support-annotations:${supportVersion}"
    testCompile 'junit:junit:4.12'
}

apply from: 'https://raw.githubusercontent.com/ligboy/JCenter/1.0.0/bintray.gradle'      
````  
  
#### Project build.gradle   

````gradle
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:2.0.0-alpha3'
        classpath 'com.github.dcendents:android-maven-gradle-plugin:1.3'
        classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.4'
        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}  
````   

  
  
