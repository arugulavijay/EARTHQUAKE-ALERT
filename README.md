# EARTHQUAKE-ALERT
ANDROID APPLICATION FOR REAL TIME EARTHQUAKE MONITORING AND NEARBY ALERTS

🌍 Earthquake Alert – Android Application

An Android application built using Kotlin that monitors recent earthquakes worldwide and alerts users about earthquakes occurring within their selected distance from their current location.

The application integrates Firebase Authentication, Google Fused Location Provider, and the USGS Earthquake GeoJSON API to provide real-time earthquake information and nearby earthquake alerts.

🚀 Features

- Firebase Authentication: Secure user registration and login using email and password.
- Worldwide Earthquake Monitoring: Fetch recent earthquake information from the USGS API.
- Current Location Tracking: Get the user's current location using Fused Location Provider.
- Distance Calculation: Calculate the distance between the user and each earthquake using "Location.distanceBetween()".
- Earthquake Information: Display magnitude, location, date, time, and distance.
- Sorting: Sort earthquakes by time, magnitude, or distance.
- Magnitude Filter: Filter earthquakes using a minimum magnitude Slider.
- Nearby Earthquake Alerts: Select a preferred alert radius.
- Nearby Count Banner: Display the number of earthquakes within the selected radius.
- Local Notifications: Notify users when newly detected earthquakes occur within their selected alert radius.
- Earthquake Details: View detailed earthquake information.
- USGS Integration: Open the official earthquake information page using an implicit Android Intent.

🛠️ Technology Stack

Technology| Purpose
Kotlin| Android application development
Android Studio| Development environment
Firebase Authentication| User authentication
Fused Location Provider| Current location tracking
USGS GeoJSON API| Earthquake data
Retrofit| API communication
Gson| JSON parsing
Material Components| User interface
NotificationCompat| Local notifications
PendingIntent| Notification navigation

🌐 API Integration

USGS Earthquake GeoJSON Feed

API Endpoint:

https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_day.geojson

This API provides earthquake information worldwide without requiring an API key.

Earthquake Data

The application extracts:

- Earthquake ID
- Magnitude
- Location / Place
- Timestamp
- Latitude
- Longitude
- USGS Information URL

📍 Distance Calculation

The application uses Android's "Location.distanceBetween()" method to calculate the distance between the user's current location and earthquake coordinates.

val results = FloatArray(1)

Location.distanceBetween(
    userLatitude,
    userLongitude,
    earthquakeLatitude,
    earthquakeLongitude,
    results
)

val distanceKm = results[0] / 1000

Earthquakes within the selected alert radius are highlighted in the application.

🔔 Notification System

The notification system:

1. Checks newly fetched earthquake information.
2. Calculates the distance from the user's location.
3. Compares the distance with the selected alert radius.
4. Sends a local notification for newly detected nearby earthquakes.
5. Prevents duplicate notifications using earthquake IDs.
6. Opens the earthquake details screen when the notification is tapped.

Note: Background notifications require appropriate background execution or scheduled work configuration.

📱 Application Screens

1. Login Screen
2. Registration Screen
3. Earthquake Dashboard
4. Earthquake List
5. Earthquake Details Screen
6. Nearby Earthquake Alert Notification

⚙️ Installation and Setup

Prerequisites

- Android Studio
- JDK compatible with your Android Gradle Plugin
- Kotlin
- Android SDK
- Git and GitHub account
- Firebase account

Step 1: Clone the Repository

git clone https://github.com/YOUR_USERNAME/Earthquake-Alert-Android-App.git

Step 2: Open the Project

1. Open Android Studio.
2. Select Open Project.
3. Choose the cloned project folder.
4. Wait for Gradle synchronization.

Step 3: Firebase Configuration

1. Open Firebase Console.
2. Create a Firebase project.
3. Register your Android application.
4. Download the "google-services.json" configuration file.
5. Place it inside the app directory.
6. Enable Email/Password authentication in Firebase Authentication.

Step 4: Run the Application

1. Connect an Android device or start an emulator.
2. Grant location permissions.
3. Grant notification permissions when requested.
4. Run the application.

🔐 Permissions

The application may require the following permissions:

- "INTERNET"
- "ACCESS_FINE_LOCATION"
- "ACCESS_COARSE_LOCATION"
- "POST_NOTIFICATIONS"

Location and notification permissions are requested at runtime where required.

📂 Project Structure

Earthquake-Alert/
│
├── app/
│   └── src/main/
│       ├── java/
│       │   └── com/example/earthquakealert/
│       │       ├── auth/
│       │       ├── model/
│       │       ├── network/
│       │       ├── repository/
│       │       ├── location/
│       │       ├── adapter/
│       │       ├── notification/
│       │       ├── ui/
│       │       └── utils/
│       │
│       ├── res/
│       └── AndroidManifest.xml
│
├── build.gradle.kts
├── settings.gradle.kts
└── README.md

The folder structure may vary depending on the final implementation.

🎯 Project Objective

The main objective of this project is to develop a location-based earthquake monitoring system that helps users identify nearby earthquakes, understand their magnitude and distance, and receive timely notifications about newly detected earthquake events.

🔮 Future Enhancements

- Interactive earthquake map.
- Historical earthquake analysis.
- Push notifications using Firebase Cloud Messaging.
- Background earthquake monitoring.
- Earthquake statistics and visualization.
- Customizable alert preferences.
- Multi-language support.

👨‍💻 Developer

Project Name: Earthquake Alert

Platform: Android

Language: Kotlin

Category: Disaster Management / Location-Based Application

📜 Data Source

USGS – United States Geological Survey

https://earthquake.usgs.gov/

Earthquake data is provided by the USGS Earthquake Hazards Program.

📄 License

This project is intended for educational and academic purposes. Refer to the USGS data usage guidelines when redistributing earthquake data.

---

⭐ If you find this project useful, consider giving it a star on GitHub!
