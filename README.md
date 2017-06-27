# AsyncImageLoader
该工程是对google官方的[DisplayingBitmaps](https://github.com/googlesamples/android-DisplayingBitmaps)部分改动

# DisplayingBitmaps的不足

1、只能给ImageView加载图片，如果一个View设置一个来自网络的图片，这是用DisplayingBitmaps中的异步加载架构就有所限制。

2、可能隐藏的内存泄露，在原来的[ImageWorker](https://github.com/googlesamples/android-DisplayingBitmaps/blob/master/Application/src/main/java/com/example/android/displayingbitmaps/util/ImageWorker.java)中的回调接口和view都传给了AsyncTask，其中只对view做了弱引用的处理，如果回调接口是通过内部类或匿名内部类传如的话可能会导致内存泄露，这里也做了修改。
