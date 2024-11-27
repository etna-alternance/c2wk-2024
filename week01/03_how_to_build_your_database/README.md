# 🎵 Workshop: Building a Relational Database for a Spotify-Like Music Service


## 🏆 **Objective**
Design an efficient relational database model for a music streaming service. This workshop will guide you through defining features, identifying entities and their attributes, and modeling interactions between them.

## **Step 0: Useful websites:**
Some tools that can be helpful for designing your database:

- Lucidchart: A popular diagramming tool.
- Draw.io: Free and open-source for creating ER diagrams


## **Step 1: Identify Key Features**

Here are the core features our Spotify-like service will support:

1. 🎧 **Music Playback**: Users can stream songs.
2. 👤 **User Accounts**: Users can create and manage their profiles.
3. 🔒 **Authentication**: Secure user login.
4. 📜 **Playlists**: Users can create and manage playlists.
5. ❤️ **Likes System**: Users can save favorite songs.
6. 🔍 **Search and Discovery**: Browse music, artists, and albums.
7. 💿 **Albums & Artists**: Songs are grouped under albums and linked to artists.
8. 🕒 **Listening History**: Track recently played songs.


## **Step 2: Define Objects and Attributes**

### 🎶 **1. Song**
Represents an individual track.


### 📋 **2. Playlist**
A user-generated collection of songs.


### 👤 **3. User**
Represents the service’s account holders.


### 💿 **4. Album**
Represents a collection of songs by an artist.


### 🎤 **5. Artist**
Represents an individual artist or a band.


## **Step 3: Model Relationships**

### 💬 **User Interactions with Songs**
- Users can like songs (many-to-many relationship).
- Users can play songs (track playback in listening history).

### 🔗 **Songs in Playlists**
- A playlist contains many songs, and songs can belong to multiple playlists (many-to-many relationship).

### 🎶 **Songs, Albums, and Artists**
- Each song belongs to one album (one-to-many relationship).
- Each song is performed by one artist (one-to-many relationship).
- Albums are created by artists (one-to-many relationship).

