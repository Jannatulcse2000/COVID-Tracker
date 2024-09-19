# COVID-Tracker

COVID Tracker is an Android app designed to track COVID-19 positive patients within a 100-meter radius of the current user. The app monitors users' real-time locations and displays these on a map. For COVID-positive users, their location data (latitude and longitude) is sent to Firebase Real-Time Database. The app retrieves and displays all COVID-positive users' locations on the map, and notifies the current user of how many COVID-positive users are within 100 meters.

## Features

### 0. Starting Page
The user is presented with two options: **Start** and **Help**. The **Help** option provides guidelines on how to use the app, while **Start** initiates the tracking.

### 1. Sign Up
New users can create an account by providing their name, email, password, and COVID-19 status (Positive/Negative). The user data is stored in Google Firebase Real-Time Database. Existing users cannot sign up again.

### 2. Verify Email
After successfully registering, a verification email is sent to the user’s email address. Users must verify their email before proceeding.

### 3. Login
The app allows only authorized users to log in. It validates the email and password combination. Users must verify their email before they can log in.

### 4. Forgotten Password
If a user forgets their password, they can reset it via the login page.

### 5. Home Page
#### i. Location Permission
If location services are disabled, the app will prompt the user to enable them.

#### ii. Google Map with Markers
A Google map displays markers representing COVID-positive users' locations, except for the current user, whose location is always shown, regardless of status. The current user's location is highlighted with a marker that shows their city, locality, and other known details. Every 20 seconds, the location data is updated, and COVID-positive users' locations are pushed to Firebase Real-Time Database. The app checks how many COVID-positive users are within 100 meters of the current user and provides a notification.

#### iii. Navigation Drawer
   - **Navigation Header**: Displays the current user's name, email, and COVID status.
   - **COVID Hotline**: Provides COVID hotline numbers for Bangladesh. Tapping a number opens the dial pad for easy access.
   - **COVID Lab Test Info**: Lists COVID lab test hotline numbers, categorized by division in Bangladesh.
   - **COVID Hospital List**: Lists the names and contact details of COVID hospitals in Bangladesh. Tapping a contact number opens the dial pad.
   - **BD COVID Update**: Shows updated COVID statistics, including new cases and deaths in Bangladesh.
   - **Ambulance Info**: Provides ambulance hotline numbers categorized by division in Bangladesh.
   - **Change My COVID Status**: Allows users to update their COVID status between positive and negative.
   - **Sign Out**: Logs the user out. Users must log back in to access the app again.
   - **Delete Account**: Allows users to delete their account.
   - **Feedback**: Users can send feedback to the admin.

## How the Location Tracking Works

1. Users' devices receive continuous location updates via GPS and network services.
2. Latitude and longitude data for COVID-positive users are written to and updated in Firebase Real-Time Database.
3. All users' devices retrieve the data from Firebase and display the locations on a map with markers. The current user's location is always shown, even if they are COVID-negative.

## Installation

### Permissions
Add the following permissions to your `AndroidManifest.xml` file:
```xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="com.vogella.android.locationapi.maps.permission.MAPS_RECEIVE" />
<uses-permission android:name="com.google.android.providers.gsf.permission.READ_GSERVICES" />
<uses-permission android:name="android.permission.INTERNET" />
