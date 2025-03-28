# VSTREAM

This is the backend for a video-sharing platform built using Node.js, Express, and MongoDB. It provides APIs for user authentication, video management, subscriptions, playlists, likes, comments, and more.

## Features

- **User Authentication**: Register, login, logout, and token-based authentication.
- **Video Management**: Upload, update, delete, and fetch videos.
- **Subscriptions**: Subscribe to channels and manage subscriptions.
- **Playlists**: Create, update, and manage playlists.
- **Likes**: Like videos, comments, and tweets.
- **Comments**: Add, update, and delete comments on videos.
- **Tweets**: Post, update, and delete tweets.
- **Dashboard**: Fetch channel statistics and videos.
- **Healthcheck**: API to check server health.

## Tech Stack

- **Backend**: Node.js, Express.js
- **Database**: MongoDB with Mongoose
- **File Uploads**: Cloudinary
- **Authentication**: JWT (JSON Web Tokens)
- **Middleware**: Multer for file uploads, Cookie-Parser for cookies
- **Utilities**: Async error handling, custom error and response classes

## Installation

1. Clone the repository:

   ```bash
   git clone <repository-url>
   cd chai-backend
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory and configure the following variables:

   ```env
   PORT=8000
   MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/
   CORS_ORIGIN=*
   ACCESS_TOKEN_SECRET=<your-access-token-secret>
   ACCESS_TOKEN_EXPIRY=1d
   REFRESH_TOKEN_SECRET=<your-refresh-token-secret>
   REFRESH_TOKEN_EXPIRY=10d
   CLOUDINARY_CLOUD_NAME=<your-cloudinary-cloud-name>
   CLOUDINARY_API_KEY=<your-cloudinary-api-key>
   CLOUDINARY_API_SECRET=<your-cloudinary-api-secret>
   ```

4. Start the development server:

   ```bash
   npm run dev
   ```

5. The server will run at `http://localhost:8000`.

## API Endpoints

### User Routes

- `POST /api/v1/users/register`: Register a new user.
- `POST /api/v1/users/login`: Login a user.
- `POST /api/v1/users/logout`: Logout a user.
- `GET /api/v1/users/current-user`: Get the current logged-in user.

### Video Routes

- `GET /api/v1/videos`: Fetch all videos.
- `POST /api/v1/videos`: Upload a new video.
- `PATCH /api/v1/videos/:videoId`: Update video details.
- `DELETE /api/v1/videos/:videoId`: Delete a video.

### Subscription Routes

- `POST /api/v1/subscriptions/c/:channelId`: Subscribe to a channel.
- `GET /api/v1/subscriptions/u/:subscriberId`: Get subscribed channels.

### Playlist Routes

- `POST /api/v1/playlist`: Create a new playlist.
- `PATCH /api/v1/playlist/:playlistId`: Update a playlist.
- `DELETE /api/v1/playlist/:playlistId`: Delete a playlist.

### Like Routes

- `POST /api/v1/likes/toggle/v/:videoId`: Toggle like on a video.
- `GET /api/v1/likes/videos`: Get all liked videos.

### Comment Routes

- `GET /api/v1/comments/:videoId`: Get comments for a video.
- `POST /api/v1/comments/:videoId`: Add a comment to a video.

### Healthcheck

- `GET /api/v1/healthcheck`: Check server health.

## Folder Structure

```

├── src/
│   ├── controllers/       # API controllers
│   ├── db/                # Database connection
│   ├── middlewares/       # Custom middlewares
│   ├── models/            # Mongoose models
│   ├── routes/            # API routes
│   ├── utils/             # Utility functions
│   ├── app.js             # Express app setup
│   └── index.js           # Entry point
├── public/                # Static files
├── .env                   # Environment variables
├── .gitignore             # Git ignore file
├── package.json           # Project metadata and dependencies
└── Readme.md              # Project documentation
```

## License

This project is licensed under the ISC License.

## Author

Developed by **Mayank Sengar**.
