 [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)  [ ![Download](https://api.bintray.com/packages/wordpress-mobile/maven/libaddressinput%3Acommon/images/download.svg) ](https://bintray.com/wordpress-mobile/maven/libaddressinput%3Acommon/_latestVersion)

# libaddressinput:common

Provides offline address localization and formatting for shipping and billing labels.

**Features:**
* Address formats for 200 countries
* Postal formatting
* Data provided by Google's [Address Data Service](https://chromium-i18n.appspot.com/ssl-address)

**Changes from Original Forked Repo:**

This libary is a subset of Google's [libaddressinput](https://github.com/googlei18n/libaddressinput) project. The unused Android module was stripped out due to it being severely outdated and mostly useless. The C++ modules were stripped out because they exist specifically for chromium and wont work for android.

**Important Considerations**

At this time, the data used for address formatting is statically included in the library and will need to be updated manually. The repo this was forked from typically gets a refresh of that data every few months. 

We may want to someday write a script that builds this data mapping in a nightly job instead of relying on periodic manual updates. 

## Use the library in your project

* In your build.gradle:
```groovy
repositories {
    maven { url 'https://a8c-libs.s3.amazonaws.com/android' }
}
dependencies {
    implementation 'org.wordpress:libaddressinput.common:0.0.2'
}
```

## Publish it to S3

When a new version is ready to be published to the remote repository, use the following command to upload it to Bintray:

```shell
$ ./gradlew publishToS3 --tag-name={$VERSION}
```

## License

[Apache 2.0 license](LICENSE)

[1]: https://github.com/wordpress-mobile/libaddressinput/blob/trunk/common/build.gradle#L77
