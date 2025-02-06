# **App_Development**
This repo is all about what i explored in app development

# Kotlin and Jetpack Compose Overview

- **Val and Var in Kotlin**:
  - `val`: Immutable (fixed) value
  - `var`: Mutable (value can be changed)
  - No need to specify data types explicitly
  - No semicolon required

---

# UI Tools in Jetpack Compose

- **Jetpack Compose** is used as the UI tool
- The main screen is typically an `Activity`
- **setContent** is used to define the content for the main screen

---

# Edge-to-Edge Display

- **EdgeToEdge** means the app will display from corner to corner, filling the entire screen including the notch area
- To enable this, just write `enableEdgeToEdge` in Kotlin

---

# Composables and UI Layout

- `@Composable` is used to create UI components in Jetpack Compose, which will be displayed on the screen
- UI elements are stacked one over another using a `Box` container (e.g., for background with text overlay)
- Use **painterResource** to load and display images (similar to using `""` for strings)

---

# Resources in Jetpack Compose

- **Images** should be added to the `drawable` directory in the `res` folder
- Reference images from the `mipmap` folder when used in code
- `R` refers to resources in the app's `res` folder (including images)

---

# Accessibility Features

- **contentDescription** is an accessibility feature for blind users. When tapped, it provides a description of the image.

---

# Code Snippets for Displaying Images

### Example Code for Displaying an Image

```kotlin
fun EncoderDecoder() {
    Box() {
        val bg = painterResource(id = R.mipmap.ic_launcher_foreground)
        Image(
            painter = bg,
            contentDescription = "BackGround Image",
        )
    }
}


This ensures that the image fills the entire screen properly.
