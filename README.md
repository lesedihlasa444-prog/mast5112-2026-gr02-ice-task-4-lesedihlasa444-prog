# ICE Task 4 - Weather Dashboard UI

Student Name: Lesedi Hlasa

Student Number: ST10512679

Module Name: Mobile App Scripting

Module Code: MAST5112

Lecture Name: Sookha Jessel





## Introduction
The Weather Dashboard is a React Native mobile app written in TypeScript that lets users view detailed weather conditions for different cities including Johannesburg, Cape Town, and Durban. The app features current weather metrics, a 24-hour hourly forecast, a 5-day daily forecast, and sun and moon information.

## Development Environment
The project was built and tested using the following environment:
- Expo framework with standard TypeScript template
- React Native
- Visual Studio Code
- Institutional Virtual Machine
- BlueStacks 5 emulator with Expo Go

## Error Log

Error 1: City Selector State Bug
- Location: App.tsx in citySelector view
- Problem: The onPress button handler was passing weather.country to setSelectedCity instead of weather.city. This caused state lookups to fail whenever a user clicked a city.
- Error Type: Logic and State Error
- Correction: Updated the onPress callback function to pass weather.city directly to setSelectedCity.

Error 2: City Selector Active Button Styling
- Location: App.tsx in citySelector view
- Problem: The active button styling check was comparing selectedCity against weather.country instead of weather.city, so the selected city button never highlighted correctly.
- Error Type: Styling Logic Error
- Correction: Fixed the condition check to selectedCity === weather.city.

Error 3: Incorrect Data Property Binding
- Location: App.tsx in currentDetails section
- Problem: The humidity detail card was displaying selectedWeather.feelsLike instead of selectedWeather.humidity.
- Error Type: Data Binding Error
- Correction: Changed the value prop to display selectedWeather.humidity percentage.

Error 4: Hourly Forecast Scroll Direction
- Location: App.tsx in 24 Hour Forecast section
- Problem: The ScrollView component was missing the horizontal prop, causing hourly cards to stack vertically down the screen.
- Error Type: Layout Error
- Correction: Added horizontal={true} and set showsHorizontalScrollIndicator={false} to allow smooth side scrolling.

Error 5: Daily Forecast Layout
- Location: App.tsx in 5 Day Forecast section
- Problem: Daily cards were stacking components vertically inside dailyCard due to missing row flex direction.
- Error Type: UI and Layout Error
- Correction: Added flexDirection: 'row', alignItems: 'center', and justifyContent: 'space-between' to the dailyCard style object.

Error 6: WeatherDetail Component Label Rendering
- Location: App.tsx in WeatherDetail function component
- Problem: The component rendered label twice inside both Text tags instead of showing label and value.
- Error Type: Component Rendering Error
- Correction: Corrected the second Text component to display the value prop.

Error 7: Hero Overlay Contrast
- Location: App.tsx in weatherHero section
- Problem: Text over the background image was hard to read due to missing background overlay contrast.
- Error Type: Styling Error
- Correction: Added an overlay container with a dark transparent background color and set text colors to clean white.

## Testing
The corrected app was tested on the BlueStacks 5 emulator:
1. App Launch: Confirmed the app opens smoothly without initial compilation or runtime errors.
2. City Selection: Switched between Johannesburg, Cape Town, and Durban to confirm temperatures, icons, and background images update dynamically.
3. Hourly Forecast: Tested horizontal scrolling on the 24-hour forecast to ensure all times and temperatures display clearly.
4. Daily Forecast: Verified that all 5 forecast days render in clean horizontal rows with high and low temperatures.
5. Sun and Moon: Checked that sunrise, sunset, moonrise, moonset, and moon phase display the correct string data.
6. Overall UI: Scrolled through the full dashboard to verify smooth scrolling and clean spacing.

## Screenshot

<img width="1408" height="768" alt="IMG_4511" src="https://github.com/user-attachments/assets/56066bd8-fc3d-41ae-82d3-6cc1ff5130d3" />

<img width="1408" height="768" alt="IMG_4512" src="https://github.com/user-attachments/assets/5b261c58-2518-401c-b714-2dcca50cd34c" />

<img width="1408" height="768" alt="IMG_4513" src="https://github.com/user-attachments/assets/1ddccbd2-38f6-4396-84ea-ced1c771bba4" />

## Conclusion
Debugging the Weather Dashboard highlighted how important accurate state mapping, flexbox direction properties, and proper prop rendering are in React Native. Fixing these layout and logic bugs resulted in a responsive, easy-to-use mobile dashboard interface.

