# 📱 SMS Messaging Application

A feature-rich Android messaging application built with Java that enables users to send and receive text messages with a clean, intuitive interface. This app demonstrates modern Android development practices including SMS permissions handling, real-time message delivery, and Material Design UI.

![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white)
![Min SDK](https://img.shields.io/badge/Min%20SDK-21-green?style=for-the-badge)

## 📋 Table of Contents
- [Features](#features)
- [Screenshots](#screenshots)
- [Technologies Used](#technologies-used)
- [Requirements](#requirements)
- [Installation](#installation)
- [Permissions](#permissions)
- [Project Structure](#project-structure)
- [Architecture](#architecture)
- [Usage](#usage)
- [Building the App](#building-the-app)
- [Known Issues](#known-issues)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## ✨ Features

### Core Functionality
- 📤 **Send SMS Messages** - Send text messages to any phone number
- 📥 **Receive SMS Messages** - Real-time message reception with notifications
- 💬 **Conversation View** - Organized threaded conversations
- 📝 **Message History** - View complete message history
- 🔔 **Notifications** - Instant notifications for new messages
- 👤 **Contact Integration** - Access and select contacts from phone book

### UI/UX Features
- 🎨 **Material Design** - Modern, clean interface following Material Design guidelines
- 🌙 **Responsive Layout** - Adapts to different screen sizes and orientations
- ⚡ **Fast Performance** - Optimized for smooth scrolling and quick message delivery
- 🔍 **Search Functionality** - Search through messages and conversations
- ✅ **Delivery Reports** - Track message delivery status

### Technical Features
- 🔐 **Runtime Permissions** - Proper handling of Android runtime permissions
- 🔄 **Background Processing** - Efficient message handling in background
- 💾 **Local Storage** - Messages stored locally using SQLite
- 🔔 **Broadcast Receivers** - Real-time message reception using broadcast receivers


## 🛠️ Technologies Used

### Android Development
- **Language:** Java
- **IDE:** Android Studio
- **Build Tool:** Gradle
- **Min SDK:** 21 (Android 5.0 Lollipop)
- **Target SDK:** 33 (Android 13)

### Android Components
- Activities and Fragments
- Broadcast Receivers
- Content Providers (SMS)
- SQLite Database
- RecyclerView
- Material Design Components

### Libraries & Dependencies
```gradle
// Add your actual dependencies here
implementation 'androidx.appcompat:appcompat:1.6.1'
implementation 'com.google.android.material:material:1.9.0'
implementation 'androidx.constraintlayout:constraintlayout:2.1.4'
implementation 'androidx.recyclerview:recyclerview:1.3.1'
```

## 💻 Requirements

### Development Environment
- **Android Studio:** Arctic Fox or later
- **JDK:** 11 or higher
- **Gradle:** 7.0+
- **Android SDK:** API 21 to 33

### Testing Device/Emulator
- Android device running Android 5.0 (API 21) or higher
- Physical device recommended for SMS testing

## 📥 Installation

### Clone the Repository
```bash
git clone https://github.com/therajbali/Mobile_Application-for-Send_and_Receve_Text_Massages.git
cd Mobile_Application-for-Send_and_Receve_Text_Massages
```

### Open in Android Studio
1. Launch Android Studio
2. Select **File > Open**
3. Navigate to the cloned repository folder
4. Click **OK** and wait for Gradle sync

### Build and Run
1. Connect an Android device or start an emulator
2. Click **Run** button or press `Shift + F10`
3. Select your device and click **OK**

## 🔐 Permissions

This app requires the following permissions:

```xml
<!-- Send SMS -->
<uses-permission android:name="android.permission.SEND_SMS" />

<!-- Receive SMS -->
<uses-permission android:name="android.permission.RECEIVE_SMS" />

<!-- Read SMS -->
<uses-permission android:name="android.permission.READ_SMS" />

<!-- Read Contacts -->
<uses-permission android:name="android.permission.READ_CONTACTS" />

<!-- Internet (if using cloud sync) -->
<uses-permission android:name="android.permission.INTERNET" />
```

### Runtime Permissions
The app properly handles Android 6.0+ runtime permissions. Users will be prompted to grant:
- SMS permissions (send, receive, read)
- Contacts access
- Notification permissions (Android 13+)

## 📁 Project Structure

```
Mobile_Application-for-Send_and_Receve_Text_Massages/
│
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/yourpackage/smsapp/
│   │   │   │   ├── activities/
│   │   │   │   │   ├── MainActivity.java
│   │   │   │   │   ├── ConversationActivity.java
│   │   │   │   │   └── SendMessageActivity.java
│   │   │   │   ├── adapters/
│   │   │   │   │   ├── MessageAdapter.java
│   │   │   │   │   └── ConversationAdapter.java
│   │   │   │   ├── models/
│   │   │   │   │   ├── Message.java
│   │   │   │   │   └── Conversation.java
│   │   │   │   ├── receivers/
│   │   │   │   │   └── SmsReceiver.java
│   │   │   │   ├── database/
│   │   │   │   │   ├── DatabaseHelper.java
│   │   │   │   │   └── MessageDao.java
│   │   │   │   └── utils/
│   │   │   │       └── PermissionUtils.java
│   │   │   ├── res/
│   │   │   │   ├── layout/
│   │   │   │   ├── drawable/
│   │   │   │   ├── values/
│   │   │   │   └── menu/
│   │   │   └── AndroidManifest.xml
│   │   └── test/
│   └── build.gradle
├── gradle/
├── screenshots/
├── .gitignore
├── build.gradle
├── settings.gradle
├── README.md
└── LICENSE
```

## 🏗️ Architecture

The app follows **MVC (Model-View-Controller)** architecture pattern:

- **Model:** Data classes (`Message.java`, `Conversation.java`)
- **View:** XML layouts and Activities
- **Controller:** Activities and Adapters handling business logic

### Key Components

**BroadcastReceiver:**
```java
public class SmsReceiver extends BroadcastReceiver {
    @Override
    public void onReceive(Context context, Intent intent) {
        // Handle incoming SMS
    }
}
```

**Database Helper:**
```java
public class DatabaseHelper extends SQLiteOpenHelper {
    // SQLite database for message storage
}
```

## 🚀 Usage

### Sending a Message
1. Launch the app
2. Click the "+" or "New Message" button
3. Select a contact or enter a phone number
4. Type your message
5. Press "Send"

### Viewing Messages
1. Open the app to see conversation list
2. Tap on a conversation to view messages
3. Scroll to view message history

### Managing Permissions
1. First launch will request necessary permissions
2. Go to Settings > Apps > SMS App > Permissions to modify

## 🔨 Building the App

### Debug Build
```bash
./gradlew assembleDebug
```

### Release Build
```bash
./gradlew assembleRelease
```

### Generate APK
```bash
./gradlew build
```
APK location: `app/build/outputs/apk/`

### Install on Device
```bash
./gradlew installDebug
```

## ⚠️ Known Issues

- Some carrier-specific limitations may affect message delivery
- Large MMS messages not yet supported
- Group messaging feature in development

## 🔮 Future Enhancements

- [ ] MMS (Multimedia Message Service) support
- [ ] Group messaging
- [ ] Message scheduling
- [ ] Backup and restore functionality
- [ ] Cloud sync
- [ ] Dark mode theme
- [ ] Custom notification sounds
- [ ] Message encryption
- [ ] Chat bubbles (Android 11+)
- [ ] RCS messaging support
- [ ] Spam filtering
- [ ] Message search enhancement
- [ ] Custom themes and colors

## 🧪 Testing

### Unit Tests
```bash
./gradlew test
```

### Instrumentation Tests
```bash
./gradlew connectedAndroidTest
```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Coding Guidelines
- Follow Java coding conventions
- Write meaningful commit messages
- Add comments for complex logic
- Update documentation as needed
- Test thoroughly before submitting PR

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🐛 Bug Reports

Found a bug? Please open an issue with:
- Device information
- Android version
- Steps to reproduce
- Expected vs actual behavior
- Screenshots if applicable

## 📞 Contact

**Raj Bali**

- GitHub: [@therajbali](https://github.com/therajbali)
- LinkedIn: (https://www.linkedin.com/in/therajbali/)
- Email: rajbaliofficial@gmail.com

## 🙏 Acknowledgments

- Android Developer Documentation
- Material Design Guidelines
- Stack Overflow Community
- Contributors and testers

## 📚 Resources

- [Android SMS Documentation](https://developer.android.com/reference/android/telephony/SmsManager)
- [Material Design Guidelines](https://material.io/design)
- [Android Permissions Guide](https://developer.android.com/guide/topics/permissions/overview)

---

<div align="center">

⭐ **If you found this project helpful, please give it a star!** ⭐

**Made with ❤️ by Rajbali**

</div>
