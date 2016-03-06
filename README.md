<p align="left">
  <img src="https://cloud.githubusercontent.com/assets/4659608/12700433/4276edc0-c7f3-11e5-9f2c-de6bcbb9416d.png" width="600">
</p>
# Media Picker
![](https://img.shields.io/badge/Platform-Android-brightgreen.svg)
![](https://img.shields.io/crates/l/rustc-serialize.svg)
![](https://img.shields.io/badge/version-2.0.0-blue.svg)

------ 
Media Picker is an Android Libary that lets you to select multiple images, video or voice for Android 4.1 (API 16) +.
You can report any issue on issues page. **Note: If you speak Arabic, you can submit issues with Arabic language and I will check them. :)**

# NOTE
----
This build `2.x.x` will break backward compatibility and there are a lot of changes to improve the performance and fix a lot of Leak memory issues, So please read below document carefully.
## Installation
------ 
**Maven**
```xml
<dependency>
<groupId>net.alhazmy13.MediaPicker</groupId>
<artifactId>libary</artifactId>
<version>2.0.0</version>
</dependency>
```


**Gradle**
```gradle
dependencies {
	compile 'net.alhazmy13.MediaPicker:libary:2.0.0'
}
```

# Usage
------ 
## Images
After adding the library, you need to:

1. Create an object from `ImagePicker`
2. Override `onActivityResult` to receive the path of image.



### Create an `ImagePicker`
You will need to create a new instance of `ImagePicker`. Once the instance are configured, you can call `build()`.

```java
        new ImagePicker.Builder(this)
                .build();
```
### Override `onActivityResult `
In order to receive the path of image, you will need to override `onActivityResult ` .

```java
   @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);

        if (requestCode == ImagePicker.IMAGE_PICKER_REQUEST_CODE && resultCode == RESULT_OK) {
            String mPath = data.getStringExtra(ImagePicker.EXTRA_IMAGE_PATH);
            //Your Code
        }
    }
```

### Additional Options
* `mode` to select the mode, you can chose one ot these `CAMERA`,`GALLERY` or `CAMERA_AND_GALLERY`

```java
.mode(ImagePicker.Mode.CAMERA)
```
 
* `extension` You can change the extanion of image to `PNG` or `JPG`

```java
.extension(ImagePicker.Extension.PNG)
```
* `compressLevel` You can change the quality of image with three different levels `HARD`,`MEDIUM`, `SOFT` or `NONE`

```java
.compressLevel(ImagePicker.ComperesLevel.MEDIUM)
```

* `directory` You can pass the storage path, or You can select `Directory.DEFAULT_DIR` to keep the default path.

```java
.directory(ImagePicker.Directory.DEFAULT)

//OR

.directory(Environment.getExternalStorageDirectory()+"/myFolder")

```
------ 

## Video
------ 
######COMAING SOON


## Theme the pickers

You can change the strings be overwriting below resources in your project.

```xml

    <string name="media_picker_select_from">Select From:</string>
    <string name="media_picker_camera">Camera</string>
    <string name="media_picker_gallery">Gallery</string>
```



## License
------ 
    Copyright 2015 alhazmy

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
    

