 [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) 
 
 <a href='https://bintray.com/wordpress-mobile/maven/libaddressinput%3Acommon?source=watch' alt='Get automatic notifications about new "libaddressinput:common" versions'><img src='https://www.bintray.com/docs/images/bintray_badge_color.png'></a>

# libaddressinput:common

Provides offline address localization and formatting for shipping and billing labels.

**Features:**
* Address formats for 200 countries
* Postal formatting
* Data provided by Google's [Address Data Service](https://chromium-i18n.appspot.com/ssl-address)

**Changes from Original Forked Repo:**

This libary is a subset of Google's [libaddressinput](https://github.com/googlei18n/libaddressinput) project. The unused Android module was stripped out due to it being severely outdated and mostly useless. The C++ modules were stripped out because they exist specifically for chromium and wont work for android.

**Important Considerations**

At this time, the data used for address formatting is statically included in the library and will need to be updated manually. The repo this was forked from typically get's a refresh of that data every few months. 

We may want to someday write a script that builds this data mapping in a nightly job instead of relying on periodic manual updates. 

## Use the library in your project

* In your build.gradle:
```groovy
dependencies {
    implementation 'org.wordpress:libaddressinput.common:0.0.1'
}
```

## Publish an updated version to your local maven repository

You can bump the [version name in the main build file: `common/build.gradle`][1]. After updating the build file, you can build, and publish the library to your local maven repo. That will let you try the new version in your app for example.

```shell
$ ./gradlew assemble test publishToMavenLocal
```

## Publish it to Bintray

When a new version is ready to be published to the remote repository, use the following command to upload it to Bintray:

```shell
$ ./gradlew assemble test bintrayUpload -PbintrayUser=FIXME -PbintrayKey=FIXME -PdryRun=false
```

## Apps and libraries using libaddressinput:common

- [woocommerce-android][2]

## License

[Apache 2.0 license](LICENSE)

[1]: https://github.com/wordpress-mobile/libaddressinput/blob/master/common/build.gradle#L77
[2]: https://github.com/woocommerce/woocommerce-android