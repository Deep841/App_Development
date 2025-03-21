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
//This ensures that the image fills the entire screen properly.
```

---

# Mutable and Immutable Variables

- `var`: Changeable values used when UI elements update dynamically
- `val`: Fixed values that do not change
- Example:

```kotlin
var a = 9
println(a)
a = 10
println(a) // Instead of printing twice, update the value before displaying
```

---

# State Management in Jetpack Compose

- `mutableStateOf("")`: Holds a mutable state for UI updates
- Example:

```kotlin
var inputEncode by remember { mutableStateOf("") }
TextField(
    value = inputEncode,
    onValueChange = { inputEncode = it },
    label = { Text("Enter a string to encode") }
)
```

---

# Encoding & Decoding Strings

- Convert string to ASCII, shift values by `+2`, then back to string
- Example:

```kotlin
fun encodeString(input: String): String {
    return input.map { char -> (char.code + 2).toChar() }.joinToString("")
}
```

---

# Layouts in Jetpack Compose

- `Column`: Places elements one below another
- `Row`: Places elements side by side
- `Box`: Stacks elements on top of each other

---

# Intent in Android

- **Intent**: Used for actions like sharing content
- Example:

```kotlin
val intent = Intent(Intent.ACTION_SEND)
intent.type = "text/plain"
intent.putExtra(Intent.EXTRA_TEXT, "Hello from my app!")
startActivity(Intent.createChooser(intent, "Share via"))
```

---

# Context in Android

- **Context** provides access to app resources and services

---

This document covers fundamental concepts in Jetpack Compose, state management, encoding techniques, layouts, and Android intents.

