# 📘 SecureNotes Enhanced - Personal Firebase Notes Application

A beautiful, feature-rich, secure notes application with **rich text editing**, **export functionality**, **categories**, **templates**, and **PWA support**.

![Version](https://img.shields.io/badge/version-2.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)

## 🆕 What's New in v2.0

### ✨ Enhanced Features

- 📝 **Rich Text Editor** - Format your notes with Quill editor (bold, italic, lists, headers, colors)
- 💾 **Export Notes** - Export individual notes or all notes as Markdown files
- 📁 **Categories/Folders** - Organize notes into custom categories
- 📄 **Note Templates** - Quick-start with 6 pre-built templates (Meeting Notes, Journal, Recipe, etc.)
- 📱 **PWA Installation** - Install as a native app on any device
- 🔄 **Service Worker** - Enhanced offline support with smart caching

## ✨ All Features

### Security & Authentication
- 🔐 **Secure Authentication** - Google login restricted to single email
- 🛡️ **Firestore Security Rules** - Server-side data protection
- 👤 **Single User Access** - Only authorized email can access

### Note Management
- ✍️ **Rich Text Editing** - Full WYSIWYG editor with formatting
- 📝 **Create, Edit, Delete** - Full CRUD operations
- 🏷️ **Tags** - Organize with custom tags
- 📁 **Categories** - Group notes into folders
- 📌 **Pin Notes** - Keep important notes at the top
- 🔍 **Search** - Quick search across titles, content, tags, and categories
- 💾 **Auto-Save** - Changes saved automatically

### Templates (6 Built-in)
1. 📄 **Blank** - Start fresh
2. 🤝 **Meeting Notes** - Date, attendees, agenda, action items
3. ✅ **To-Do List** - Simple checklist
4. 📔 **Journal Entry** - Daily reflections
5. 🎯 **Project Plan** - Goals, milestones, resources
6. 🍳 **Recipe** - Ingredients and instructions

### Export & Backup
- 💾 **Export Single Note** - Download as Markdown
- 📦 **Export All Notes** - Batch export with metadata
- 📄 **Markdown Format** - Universal, readable format

### Design & UX
- 🌓 **Dark/Light Themes** - Beautiful themes with smooth transitions
- 📱 **Mobile-First** - Responsive and touch-optimized
- ⌨️ **Keyboard Shortcuts** - Power-user friendly
- 🎨 **Elegant Design** - Crimson Pro + Work Sans typography
- ✨ **Smooth Animations** - Delightful micro-interactions

### Progressive Web App
- 📱 **Install as App** - Works like a native app
- 📡 **Offline Support** - Full offline functionality
- 🔄 **Background Sync** - Auto-sync when back online
- ⚡ **Fast Loading** - Smart caching strategy

## 🎨 Design

- **Typography**: Crimson Pro (serif) + Work Sans (sans-serif)
- **Theme**: Elegant dark-first design with golden accents (#d4af37)
- **Aesthetic**: Minimal, refined, personal journal feel
- **Animations**: Smooth transitions and micro-interactions
- **Editor**: Quill WYSIWYG with custom styling

## 📋 Requirements

- Google account
- Firebase account (free tier works perfectly)
- GitHub account
- Modern web browser (Chrome, Firefox, Safari, Edge)

## 🚀 Quick Start

### 1. Setup Firebase

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create new project: `secure-notes-enhanced`
3. Enable **Authentication** → Google sign-in
4. Enable **Firestore Database** → Production mode
5. Add authorized domain: `yourusername.github.io`

### 2. Configure Application

Open `index-enhanced.html` and update:

**Line ~587** - Firebase config:
```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_AUTH_DOMAIN",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_STORAGE_BUCKET",
    messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```

**Line ~595** - Authorized email:
```javascript
const AUTHORIZED_EMAIL = "your-email@gmail.com";
```

### 3. Set Firestore Security Rules

Copy from `firestore.rules` to Firebase Console → Firestore → Rules

### 4. Deploy to GitHub Pages

```bash
git add .
git commit -m "Deploy SecureNotes Enhanced"
git push origin main
```

Enable GitHub Pages in repository settings.

**Live at:** `https://yourusername.github.io/secure-notes`

## 📱 Using the Enhanced Features

### Categories

1. Click **☰ Menu** button
2. Click **+ Add Category**
3. Enter category name
4. Filter notes by clicking category

### Templates

1. Click **☰ Menu** button
2. Click **📄 Use Template**
3. Choose template
4. Edit and save

### Rich Text Editing

When creating/editing notes:
- Use toolbar for formatting
- **Bold**, *Italic*, Underline, Strike
- Headers (H1, H2, H3)
- Ordered/Unordered lists
- Text and background colors
- Links

### Exporting Notes

**Single Note:**
1. Open note in edit mode
2. Click **💾 Export** button
3. Downloads as Markdown

**All Notes:**
1. Click **☰ Menu** button
2. Click **💾 Export All Notes**
3. Downloads all notes with metadata

### Installing as App

**Desktop (Chrome/Edge):**
1. Click install icon in address bar
2. Or wait for install prompt

**Mobile (iOS/Android):**
1. Open in Safari/Chrome
2. "Add to Home Screen"
3. Or wait for install prompt

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + K` | Focus search |
| `Ctrl/Cmd + N` | New note |
| `Esc` | Close any modal |

### Rich Text Shortcuts (in editor)

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + B` | Bold |
| `Ctrl/Cmd + I` | Italic |
| `Ctrl/Cmd + U` | Underline |

## 🔒 Security Features

### Authentication
- ✅ Google OAuth login
- ✅ Single email restriction (client + server)
- ✅ Automatic logout for unauthorized users

### Data Protection
- ✅ Firestore security rules
- ✅ User-scoped data access
- ✅ Categories collection secured
- ✅ No public data exposure

### PWA Security
- ✅ HTTPS only (GitHub Pages)
- ✅ Service worker domain restrictions
- ✅ Secure credential storage

## 🎯 File Structure

```
secure-notes-enhanced/
├── index-enhanced.html    # Main application (v2.0)
├── manifest.json          # PWA manifest
├── sw.js                  # Service worker
├── firestore.rules        # Security rules
├── firestore.indexes.json # Database indexes
├── firebase.json          # Firebase config
├── .github/
│   └── workflows/
│       └── deploy.yml     # Auto-deployment
├── README-ENHANCED.md     # This file
└── LICENSE
```

## 📊 Data Model

### Notes Collection
```javascript
{
  title: String,
  content: String,        // HTML from Quill
  contentText: String,    // Plain text for search
  category: String,       // Category name
  tags: Array<String>,
  pinned: Boolean,
  userId: String,
  createdAt: Timestamp,
  updatedAt: Timestamp
}
```

### Categories Collection
```javascript
{
  name: String,
  userId: String,
  createdAt: Timestamp
}
```

## 🎨 Customization

### Change Colors

Edit CSS variables in `index-enhanced.html`:

```css
:root {
    --accent: #d4af37;      /* Golden accent */
    --accent-dim: #9a7f2a;  /* Darker accent */
}
```

### Change Fonts

Replace Google Fonts import:

```html
<link href="https://fonts.googleapis.com/css2?family=YourFont&display=swap">
```

### Add More Templates

Edit the `templates` array in JavaScript:

```javascript
const templates = [
    {
        name: 'Your Template',
        icon: '📝',
        content: '<h2>Your HTML content</h2>'
    }
];
```

## 🐛 Troubleshooting

### Rich Text Editor Not Loading

1. Check internet connection (Quill loads from CDN)
2. Check browser console for errors
3. Verify CDN URLs are accessible

### Export Not Working

1. Check browser allows downloads
2. Disable popup blockers
3. Try different browser

### PWA Not Installing

1. Must use HTTPS (GitHub Pages provides this)
2. Clear browser cache
3. Check manifest.json is accessible
4. Verify service worker registered

### Categories Not Saving

1. Check Firestore rules include categories collection
2. Verify authenticated user
3. Check browser console for errors

## 📈 Performance Tips

- **Limit to 1000 notes** for best performance
- **Use categories** to organize large collections
- **Delete unused notes** regularly
- **Export and archive** old notes

## 🔧 Tech Stack

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Editor**: Quill.js (WYSIWYG)
- **Backend**: Firebase (Auth + Firestore)
- **Hosting**: GitHub Pages
- **CI/CD**: GitHub Actions
- **PWA**: Service Worker + Manifest
- **Fonts**: Google Fonts
- **Icons**: Unicode Emoji

## 📱 Progressive Web App Features

### Offline Functionality
- ✅ View all notes offline
- ✅ Create/edit notes offline
- ✅ Auto-sync when back online
- ✅ Smart caching of assets

### Native App Experience
- ✅ Install on home screen
- ✅ Full-screen mode
- ✅ App icon and splash screen
- ✅ Fast loading
- ✅ Works like native app

## 🆚 Version Comparison

| Feature | v1.0 (Basic) | v2.0 (Enhanced) |
|---------|--------------|-----------------|
| Plain Text | ✅ | ✅ |
| Rich Text | ❌ | ✅ |
| Categories | ❌ | ✅ |
| Templates | ❌ | ✅ (6 types) |
| Export | ❌ | ✅ (MD) |
| PWA Install | ❌ | ✅ |
| Offline | Basic | Enhanced |
| File Size | 50KB | 70KB |

## 📄 License

MIT License - free for personal use!

## 🙏 Acknowledgments

- Firebase for backend services
- Quill.js for rich text editing
- Google Fonts for typography
- GitHub for hosting
- jsPDF for PDF generation capability

## 📞 Support

For issues:
1. Check troubleshooting section
2. Review Firebase Console logs
3. Check browser console (F12)
4. Verify Firestore rules
5. Open GitHub issue

---

## 🎉 Quick Reference

### Most Used Features

1. **Create Note**: Click `+` button
2. **Use Template**: Menu → Use Template
3. **Organize**: Menu → Add Category
4. **Search**: Type in search bar
5. **Export**: Edit note → Export icon
6. **Install**: Wait for prompt or browser install icon

### Best Practices

- ✅ Use descriptive titles
- ✅ Organize with categories
- ✅ Tag for easy finding
- ✅ Pin important notes
- ✅ Export regularly for backup
- ✅ Use templates for consistency

---

**Made with ❤️ for productive note-taking**

⭐ Star this repo if you find it useful!

🚀 **Now with 5 major new features!**
