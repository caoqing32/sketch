# ![Logo](https://github.com/xiaopansky/Android-ImageLoader/raw/master/res/drawable-mdpi/ic_launcher.png) Android-ImageLoader

Android-ImageLoader是用在Android上的一个图片加载类库，主要用于从本地或网络加载图片并显示在ImageView上。

##Features

>* 异步加载。采用线程池来处理每一个请求，并且网络加载和本地加载会放在不同的线程池中执行，保证不会因为网络加载而堵塞本地加载。

>* 支持缓存。支持在本地或内存中缓存图片，内存缓存采用Android扩展包中的LruCache来缓存，且最大容量为可用内存的八分之一，本地缓存可定义有效期，和最大容量（超过最大容量时或当前存储不够用时会自动根据活跃度清除不活跃的本地缓存文件）。

>* 强大的自定义功能。通过Configuration类你可以自定义缓存器、解码器以及下载器；通过Options类你可以自定义缓存策略、Bitmap处理器、Bitmap显示器、以及不同状态时的图片。

>* 支持ViewHolder。即使你在ListView中使用了ViewHolder也依然可以使用ImageLoader来加载图片，并且图片显示绝对不会混乱。

>* 重复下载过滤。如果两个请求的图片地址一样的话，第二个就会等待，一直到第一个下载成功后才会继续处理。


##Usage

###1.初始化ImageLoader
你需要在使用之前调用
```java
ImageLoader.getInstance().init(getBaseContext());
```
来初始化ImageLoader，推荐在Application中初始化。

###2.显示图片
你可以在任何地方调用以下代码来显示图片
```java
ImageLoader.getInstance().display(imageUri, imageView);
```
不管你是在Adapter的getView()中调用还是在Activity的onCrate()中调用都不会显示混乱。

##Downloads
**[android-image-loader-2.1.1.jar](https://github.com/xiaopansky/Android-ImageLoader/raw/master/releases/android-image-loader-2.1.1.jar)**

**[android-image-loader-2.1.1-with-src.jar](https://github.com/xiaopansky/Android-ImageLoader/raw/master/releases/android-image-loader-2.1.1-with-src.jar)**

##Extend


##License
```java
/*
 * Copyright 2013 Peng fei Pan
 * 
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at
 * 
 *   http://www.apache.org/licenses/LICENSE-2.0
 * 
 * Unless required by applicable law or agreed to in writing, software
 * distributed under the License is distributed on an "AS IS" BASIS,
 * WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 * See the License for the specific language governing permissions and
 * limitations under the License.
 */
```
