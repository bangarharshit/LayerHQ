#Installing Atlas Android

##Android Studio
After following this guide, you will have the **Atlas** library, `layer-atlas`, imported as a module in your Android Studio project, along with the optional **Atlas Messenger** module, `layer-atlas-messenger`.  Building and running Messenger will let you verify that the Layer SDK and Atlas integrations work properly. 

### Adding Layer Atlas with Git Submodule
1. Add Layer's GitHub Maven repo to your root `build.gradle` (e.g. `/MyApplication/build.gradle`):

	``` groovy
	allprojects {
    	repositories {
        	maven { url "https://raw.githubusercontent.com/layerhq/releases-android/master/releases/" }
	    }
	}
	```

2. Add `layer-atlas` project reference to your app's `build.gradle` (e.g. `/MyApplication/app/build.gradle`):

	``` groovy
	dependencies {
    	compile project(':layer-atlas')
	}
	```

3. Clone this repo as a submodule in the root of your Android Studio project.

	``` sh
	git submodule add git@github.com:layerhq/Atlas-Android
	```
	
	*Note: If git is not initialized, you may need to `git init`.*

4. Add `:layer-atlas` module to your project's root `settings.gradle` (e.g. `/MyApplication/settings.gradle`):

	``` groovy
	include ':app', ':layer-atlas', ':layer-atlas-messenger'
	project(':layer-atlas').projectDir = new File('Atlas-Android/layer-atlas')
	project(':layer-atlas-messenger').projectDir = new File('Atlas-Android/layer-atlas-messenger')
	```

5. Click "Sync Project with Gradle Files" in Android Studio

###Without Git Submodule
Follow steps 1 and 2 above, clone this repo somewhere, and...

1. Copy `layer-atlas` to the root of your AndroidStudio project:

	``` sh
	/MyApplication/layer-atlas
	```

2. Copy `layer-atlas-messenger` to the root of your AndroidStudio project:

	``` sh
	/MyApplication/layer-atlas-messenger
	```

3. Add `:layer-atlas` and `:layer-atlas-messenger` modules to your project's root `settings.gradle` (e.g. `/MyApplication/settings.gradle`):

	``` groovy
	include ':app', ':layer-atlas', ':layer-atlas-messenger'
	```

4. Click "Sync Project with Gradle Files" in Android Studio
