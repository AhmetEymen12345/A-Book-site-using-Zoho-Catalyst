# 📖 Novel November - Interactive Web Novel Platform

A full-stack interactive novel reading experience built with modern web technologies, featuring user authentication, real-time ratings, chapter discussions, and an immersive flipbook interface.

## ✨ Features

### 📱 Dual Interface
- **Desktop**: Beautiful flipbook interface with page-turning animations
- **Mobile**: Optimized scrolling experience with touch-friendly navigation

### 🔐 Authentication & User Management
- Secure authentication via Zoho Catalyst
- User profiles with personalized experience
- Session management and logout functionality

### ⭐ Rating System
- Rate each chapter (1-5 stars)
- View average ratings and total rating counts
- One rating per user per chapter (enforced)
- Real-time rating updates

### 💬 Discussion System
- Chapter-specific comment sections
- Real-time comment posting and deletion
- User-specific comment management
- Character count validation (max 1000 characters)

### 🎨 Rich Reading Experience
- 30 chapters with images and formatted text
- Smooth page transitions
- Chapter navigation sidebar
- Progress tracking
- Fullscreen mode for immersive reading

### 🔔 Admin Features
- Cliq notification system for new chapters
- Admin-only access controls
- User management dashboard

## 🛠️ Tech Stack

### Frontend
- **HTML5** - Structure
- **CSS3** - Styling with responsive design
- **JavaScript (ES6+)** - Core functionality
- **jQuery** - DOM manipulation
- **Turn.js** - Flipbook effect (desktop)

### Backend
- **Node.js** - Runtime
- **Express.js** - API server
- **Zoho Catalyst** - Backend services
  - Authentication
  - Database (Datastore)
  - Cloud Functions
  - User Management

### Database Tables
1. **Chapters** - Chapter metadata and ratings
2. **Ratings** - User rating records
3. **Comments** - Chapter discussions
4. **Users** - Email subscriptions

## 📁 Project Structure

```
novel-november/
├── app/
│   ├── index.html           # Desktop interface
│   ├── mobile.html          # Mobile interface
│   ├── main.css            # Desktop styles
│   ├── mobile.css          # Mobile styles
│   ├── main.js             # Core JavaScript
│   ├── bookContent.js      # Chapter content data
│   └── config.js           # Configuration
│
├── functions/
│   └── novelnovemberfunction/
│       └── index.js        # Backend API endpoints
│
├── images/                 # Chapter illustrations
├── .gitignore
├── README.md
├── SETUP.md               # Detailed setup guide
├── CONTRIBUTING.md        # Contribution guidelines
└── LICENSE
```

## 🚀 Quick Start

### Prerequisites
- Node.js (v14 or higher)
- Zoho Catalyst CLI
- Modern web browser

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/novel-november.git
cd novel-november
```

2. **Install dependencies**
```bash
npm install
```

3. **Configure the backend**

Edit `app/config.js`:
```javascript
// For development
const BASE_URL = 'https://your-dev-url.development.catalystserverless.in';

// For production
const BASE_URL = 'https://your-prod-url.catalystserverless.in';
```

4. **Deploy to Catalyst**
```bash
catalyst deploy
```

5. **Access the application**
- Desktop: `https://your-url/app/index.html`
- Mobile: `https://your-url/app/mobile.html`

## 📖 Usage

### For Readers
1. **Sign up** with your @zohocorp.com email
2. **Browse chapters** using the sidebar navigation
3. **Rate chapters** after reading (1-5 stars)
4. **Join discussions** by posting comments
5. **Track progress** through the chapter list

### For Admins
1. Access the admin notification button (bottom-right)
2. Enter chapter number to announce
3. System sends Cliq DMs to all subscribed users

## 🔧 Configuration

### Environment Variables
Set in `config.js`:
```javascript
BACKEND_URL: Your Catalyst function URL
AUTH_LOGIN_URL: Authentication endpoint
AUTH_SIGNUP_URL: Signup endpoint
```

### Database Schema

**Chapters Table**
- `ROWID` (Text) - Chapter ID
- `avgRating` (Number) - Average rating
- `totalNoOfRatings` (Number) - Total ratings count

**Ratings Table**
- `user_id` (Text) - User identifier
- `chapter_id` (Text) - Chapter identifier
- `rating` (Number) - Rating value (1-5)

**Comments Table**
- `chapter_id` (Text) - Chapter identifier
- `user_id` (Text) - User identifier
- `user_name` (Text) - Display name
- `user_email` (Text) - User email
- `comment_text` (Text) - Comment content

## 🎯 Key Features Implementation

### Rating System
```javascript
// One rating per user per chapter
// Prevents duplicate ratings
// Real-time average calculation
```

### Comment System
```javascript
// Chapter-specific discussions
// User can delete own comments
// 1000 character limit
// Timestamp tracking
```

### Responsive Design
```javascript
// Auto-detects device type
// Redirects to appropriate interface
// Touch-optimized controls
```

## 🐛 Known Issues & Limitations

1. **Browser Storage** - localStorage not supported in artifacts (by design)
2. **Image Loading** - Requires stable internet connection
3. **Mobile Landscape** - Best viewed in portrait mode

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details.

### How to Contribute
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Team CodeCraft** - Initial work and story writing
- Multiple authors contributed to different chapters (see individual chapter credits)

## 🙏 Acknowledgments

- Turn.js library for flipbook functionality
- Zoho Catalyst for backend infrastructure
- All contributing authors and testers
- The CodeCraft community

## 📞 Support

For issues and questions:
- Create an issue on GitHub
- Contact: aathithyan.v@zohocorp.com

## 🗺️ Roadmap

- [ ] PDF export functionality
- [ ] Bookmarking system
- [ ] Reading progress sync
- [ ] Dark mode
- [ ] Multilingual support
- [ ] Audio narration
- [ ] Social sharing features

## 📊 Project Stats

- **30 Chapters** written
- **Multiple authors** collaborated
- **Full-stack implementation** with authentication
- **Real-time features** for ratings and comments

---

Made with ❤️ by the Novel November Team
