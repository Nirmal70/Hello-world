# Hello-world
Hi  evryone!!
i'm here for learing code and I'm more familiar with JAVA and PYTHON.

    apply plugin:'com.android.application'
    apply plugin:'kotlin-android'
    apply plugin:'kotlin-kapt'
    apply plugin: 'kotlin-android-extensions'



android {
    compileSdk 32

    defaultConfig {
        applicationId "com.example.notes"
        minSdk 26
        targetSdk 32
        versionCode 1
        versionName "1.0"

        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
    kotlinOptions {
        jvmTarget = '1.8'
    }
    packagingOptions {
                exclude 'META-INF/atomicfu.kotlin_module'
            }

}
dependencies {
// Room components
    implementation "androidx.room:room-runtime:$rootProject.roomVersion"
    implementation "androidx.room:room-ktx:$rootProject.roomVersion"
    implementation 'androidx.constraintlayout:constraintlayout:2.1.3'
    kapt "androidx.room:room-compiler:$rootProject.roomVersion"
    androidTestImplementation "androidx.room:room-testing:$rootProject.roomVersion"

// Lifecycle components
    implementation "androidx.lifecycle:lifecycle-extensions:$rootProject.archLifecycleVersion"
    kapt "androidx.lifecycle:lifecycle-compiler:$rootProject.archLifecycleVersion"
    androidTestImplementation "androidx.arch.core:core-testing:$rootProject.androidxArchVersion"

// ViewModel Kotlin support
    implementation "androidx.lifecycle:lifecycle-viewmodel-ktx:$rootProject.archLifecycleVersion"

// Coroutines
    api "org.jetbrains.kotlinx:kotlinx-coroutines-android:$rootProject.coroutines"

// UI
    implementation "com.google.android.material:material:$rootProject.materialVersion"

// Testing
    androidTestImplementation "androidx.arch.core:core-testing:$rootProject.coreTestingVersion"

    implementation("androidx.recyclerview:recyclerview:1.2.1")
    // For control over item selection of both touch and mouse driven selection
    implementation("androidx.recyclerview:recyclerview-selection:1.1.0")
}
