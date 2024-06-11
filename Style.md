# Introduction to Styling in React Native

React Native styling shares similarities with web app styling but also has key differences.

### Differences from Web Styling

- **No CSS:** React Native does not use CSS for styling.
- **JavaScript-Based Styling:** You style your app using JavaScript.
- **Naming Conventions:** Styles are named in camelCase (e.g., **backgroundColor** instead of **background-color**).

### Approaches to Styling

**Inline Styles**

- **Usage:** Use the style prop accepted by most core components.
- **Method:** Specify a plain JavaScript object as the value for the style prop.
- **Previous Section:** This approach was explored in the previous section of the course.

**Stylesheet API**

- **Introduction:** React Native provides a StyleSheet API to define multiple styles in one place.
- **Method:** Use the create method to define styles.
  Focus: This section will primarily focus on using the StyleSheet API.

---

Inline Styles

![Inline Styles](/assests/style/inline-style.png)

```
Note:
- Although inline styles work, they are not recommended for React Native.
- Preferred method: Using the StyleSheet API.
```

Using the StyleSheet API

Setup

- Import the **StyleSheet** API from React Native.
- Create a styles object using the **create** method of StyleSheet.
- Define styles as key-value pairs within the object, similar to CSS but in JavaScript.

![StyleSheet API](./assests/style/StyleSheet%20API.png)

Applying Multiple Styles to a Component in React Native

**Combining Styles**

- Combine the common **box** styles with the specific background styles.
- Use an array of styles in the style prop to achieve this:
  - For the light blue box: **[styles.box, styles.lightBlueBackground]**
  - For the light green box: **[styles.box, styles.lightGreenBackground]**

![Multiple style](./assests/style/Multiply%20style.png)

```
Understanding Style Precedence
  * You can specify multiple styles using arrays.
  * The last style in the array takes precedence when merging styles.
```

### Advantages of the StyleSheet API

**Code Readability**

- Moving styles away from the render function makes the code easier to read and understand.
- Naming styles adds meaning to the components in the render function.

**Reusability and Maintenance**

- Organizing styles with the StyleSheet API makes code reusable and easier to maintain.
- Updating styles in one place reflects changes across all components using those styles.

**Consistency**

- Option to create a separate global styles file for consistency across the application.

**Additional Benefits**

- Autocomplete suggestions with the StyleSheet API, which are not available when creating style objects without it.
- Assists with React Native's unique property names.

---

### Understanding the CSS Box Model in React Native

**Overview**

- The video explores the application of CSS Box model properties in React Native components.
- These properties include margins, borders, padding, and the actual content.

---

> Note:
>
> **Unitless Dimensions**
>
> - Dimensions in React Native are **unitless** and represent density-independent pixels.
> - Specific units like **rems** or **pixels** are not required.
>
> **Percentage Values**
>
> - When parent dimensions are defined, child components can use percentage values.

---

**Height and Width Properties**

- Example: A container with flex: 1 can have child components with **_width_** and **_height_** set to 25%.

**Padding Properties**

- Similar to CSS, React Native allows padding specification in all four directions.

  **Directional Padding**

- React Native also supports **_paddingHorizontal_** and **_paddingVertical_** for more control.

**Margin Properties**

- The margin property functions similarly to CSS.

  **Directional Margins**

- React Native supports **_marginHorizontal_** and **_marginVertical_** in addition to the standard margin property.

**Border Properties**

- Unlike web CSS, React Native requires individual specification of border properties.

  **Individual Border Properties**

- Example: **borderWidth: 2**, **borderColor: 'purple'**, **borderStyle: 'solid'**.
- Default border style is **solid**, so it doesn't need explicit mention.

**Border Radius Properties**

- Border radius behaves differently on iOS and Android.

  **Platform Differences**

- Example: **borderRadius** applied to a **Text** component only works on Android.
- To ensure consistent behavior across platforms, wrap **Text** components with a **View** and apply **borderRadius** to the **View**

![box model](./assests/style/Box%20model.png)

---

### Working with Shadows in React Native

**Applying Shadows in iOS**

**Shadow Properties**
- React Native uses four properties to apply shadows:

    - **shadowColor:** Determines the color of the shadow. Example: **#333333.**

    - **shadowOffset:** An object with **width** and **height** properties. Example: **{ width: 6, height: 6 }.**

    - **shadowOpacity:** Sets the transparency of the shadow, ranging from 0 (transparent) to 1 (opaque). Example: 0.6.

    - **shadowRadius:** Sets the blur radius of the shadow. Example: **4**

**Applying Shadows in Android**

**Android Shadow Property**

- Unlike iOS, Android does not support the same shadow properties.
- Use the ***elevation*** property to apply shadows on Android. Example: **elevation: 10.**
- Add a new key to the styles object called **androidShadow** with the **elevation** property.

---
>Note:
>
> Key Points
> - The shadowColor property works on both iOS and Android.
> - No common styles apply shadows on both platforms; **elevation** must be used for Android.
> - Packages exist to support cross-platform shadows, but they are not covered in this video.
---

![shodow property](./assests/style/shadow%20and%20elevation.png)

----

### Inheritance in React Native

React Native's style inheritance is limited compared to CSS

- No Inheritance from View to Text
   - Unlike web CSS, where styles can be inherited by nested elements, React Native does not support inheritance of styles from a **View** component to a **Text** component.

- Inheritance Within Text Components
  - it does support inheritance within text subtrees.

  - Nest another **Text** component inside the original **Text** component, applying only the style from parent **Text** component.

---
# concludes 

- ### Adding styles inline and using the StyleSheet API.

- ### Applying multiple styles using array syntax.

- ### Differences in styling box model properties between web and React Native, and between iOS and Android.

- ### Applying shadows and elevation.

- ### Understanding style inheritance.