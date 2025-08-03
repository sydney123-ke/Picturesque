# Picturesque
A lightweight Android image loading library inspired by Glide, featuring memory and disk caching, image transformations, and a fluent API.

## Features

- 🚀 **Fast Loading**: Efficient memory and disk caching
- 🔄 **Transformations**: Resize, crop, and scale images
- 🎯 **Easy API**: Fluent interface similar to Glide
- 💾 **Smart Caching**: LRU memory cache + disk cache
- 🧵 **Thread Safe**: Background loading with main thread updates
- 📱 **Lightweight**: Minimal dependencies

## Installation

### Using JitPack (Recommended)

Add JitPack repository to your project's `build.gradle`:

```gradle
allprojects {
    repositories {
        google()
        mavenCentral()
        maven { url 'https://jitpack.io' }
    }
}
```

Add the dependency to your app's `build.gradle`:

```gradle
dependencies {
    implementation 'com.github.yourusername:custom-image-loader:1.0.0'
}
```

### Manual Installation

1. Download the latest AAR from [Releases](https://github.com/yourusername/custom-image-loader/releases)
2. Place it in your `app/libs/` folder
3. Add to your `build.gradle`:

```gradle
dependencies {
    implementation files('libs/imageloader-1.0.0.aar')
}
```

## Usage

### Basic Usage

```java
ImageLoader.with(this)
    .load("https://example.com/image.jpg")
    .into(imageView);
```

### Advanced Usage

```java
ImageLoader.with(context)
    .load("https://picsum.photos/800/600")
    .resize(300, 200)
    .centerCrop()
    .placeholder(R.drawable.placeholder)
    .error(R.drawable.error_image)
    .skipMemoryCache(false)
    .skipDiskCache(false)
    .into(imageView);
```

### Transformations

```java
// Center crop
ImageLoader.with(this)
    .load(imageUrl)
    .resize(200, 200)
    .centerCrop()
    .into(imageView);

// Fit center
ImageLoader.with(this)
    .load(imageUrl)
    .resize(200, 200)
    .fitCenter()
    .into(imageView);

// Center inside
ImageLoader.with(this)
    .load(imageUrl)
    .resize(200, 200)
    .centerInside()
    .into(imageView);
```

## API Reference

### RequestBuilder Methods

| Method | Description |
|--------|-------------|
| `load(String url)` | Set image URL to load |
| `resize(int width, int height)` | Resize image to specified dimensions |
| `centerCrop()` | Scale and crop to fill the bounds |
| `centerInside()` | Scale to fit inside bounds |
| `fitCenter()` | Scale to fit and center |
| `placeholder(Drawable/int)` | Set placeholder image |
| `error(Drawable/int)` | Set error image |
| `skipMemoryCache(boolean)` | Skip memory cache |
| `skipDiskCache(boolean)` | Skip disk cache |
| `into(ImageView)` | Load into ImageView |

## Requirements

- Android API 21+
- Internet permission

## License

```
Copyright 2024 Your Name

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

// ========== jitpack.yml (Optional - for JitPack configuration) ==========
jdk:
  - openjdk11
before_install:
  - sdk install java 11.0.10-open
  - sdk use java 11.0.10-open
