{% include favicons.html %}

# Modular FTC
The Modular FTC organization aims to improve the FTC robot controller app through easy community involvement and rapid development.

## Why use this?
### Ease of modification
Being able to view all hidden dependencies between components is easy now that transitive dependencies are specified in the `build.gradle` files and generated `pom.xml` files. Additionally, you are able to substitute your own forks or local modifications of the FTC libraries in your team's code by using Gradle's `includeBuild` feature and `exclude module: 'x.y.z:abc:1.2.3'` feature.

### Development performance
Faster deploy time means more time for testing: `.apk` savings with all `lite` dependencies: 18MB -> 8.5MB

### Ease of updating
Modified too much of your `ftc_app` fork and now merging changes is a pain? Don't want to wait 10 minutes for the 300MB repositories clones to a new computer? Just want to change a dependency version and test the robot? Well, this project solves all of those problems. Updating is as simple as changing your dependencies from `3.4` to `3.5` and making sure your code works correctly. The sample repository starts off at a mere 60KB and only grows as your team adds more files.

### Community Involvement
We are always open to pull requests with improvements and we are happy to work through any issues created.

## How do I get started?
That's simple! Just fork or copy our repository [`modular-sample`](https://github.com/modular-ftc/modular-sample) and you're nearly done!

If you import that project using Android Studio it should build and produce an app with two demonstration `OpMode`s. You're then free to customize the project's dependencies in the `TeamCode/build.gradle` file by removing our own [`Common-Code`](https://github.com/Pattonville-Robotics/Common-Code) library or adding your own dependencies such as `'org.apache.commons:commons-math3:3.6.1'` or our no-hassle OpenCV library [`opencv-repackaged`](https://github.com/modular-ftc/opencv-repackaged).

### Technical Details
If you're interested in how everything works behind the scenes, you've come to the right place.

#### Maven repositories used:
- `maven { url "https://jitpack.io" }`
- `maven { url "https://raw.githubusercontent.com/Pattonville-Robotics/ftc-lib-repo/mvn-repo/" }`

#### Repackaged artifacts:
- `com.github.modular-ftc:robotcontroller-repackaged`
- `com.github.modular-ftc:robotcore-repackaged`
- `com.github.modular-ftc:ftc-common-repackaged`
- `com.github.modular-ftc:vuforia-repackaged`
- `com.github.modular-ftc:opencv-repackaged`

#### Unmodified artifacts:
- `org.first.ftc:hardware`
- All other originals are hosted, but deprecated in favor of repackaged versions which fix various inconveniences and correctly specify all transitive dependencies

## Contact info
Have a great idea? Want to help out? Having trouble outside the scope of the core FTC team? Open an issue on the corrisponding repository or email me at <skaggsm333@gmail.com>!
