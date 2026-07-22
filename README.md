# Object-Oriented Music Platform (Spotify Clone)

A core Java application simulating a music streaming platform like Spotify. This project is built with a strict adherence to **Object-Oriented Programming (OOP)** principles, demonstrating dynamic state management, secure access control, and robust exception handling.

The system dynamically handles user privileges (Regular vs. Premium) and manages complex relationships between users, audio tracks, and custom playlists.

## 🚀 Key Features

*   **Dynamic Role & State Management:** Implements the State/Strategy design pattern using a `UserBehavior` interface. User capabilities (like play limits and playlist creation) dynamically change at runtime when upgrading from a **Regular** to a **Premium** account, without needing to recreate the user object.
*   **Custom Exception Handling:** Centralized error management using a custom `InvalidOperationException` to safely handle business logic violations (e.g., exceeding play limits, duplicate entities, or weak passwords).
*   **Secure Access Control & Encapsulation:** Strict data hiding and encapsulation. Playlists are password-protected, ensuring that modification methods (add, remove, edit) are exclusively accessible to the playlist owner.
*   **Advanced Search Engine:** Features overloaded search functionalities to query music by exact track title, or by a combination of track title and artist name.
*   **Social & Entity Relationships:** Comprehensive user network management allowing users to follow/unfollow creators, alongside tracking global play/stream counts for individual audio tracks.

## 🛠️ Technical Stack & Concepts

*   **Language:** Java
*   **Core Architecture:** Object-Oriented Programming (Polymorphism, Inheritance, Encapsulation, Abstraction)
*   **Design Patterns:** Strategy / State Pattern (Interface-driven behavior implementation)
*   **Data Structures:** `ArrayList` for dynamic entity management (Users, Followers, Playlists, Tracks)

## 🏗️ System Architecture

*   **`User`**: The central entity managing authentication (strict ≥8 character password validation), social networks (followers/following), and dynamic account behaviors.
*   **`Music` & `Playlist`**: Entities managing audio metadata, stream counts, and ordered collections of tracks with ownership authorization.
*   **`UserBehavior` (Interface)**: The core contract dictating user actions.
    *   *`RegularBehavior`*: Restricts playback to 5 streams and blocks playlist creation.
    *   *`PremiumBehavior`*: Unlocks unlimited streaming, playlist generation, and subscription time tracking.
