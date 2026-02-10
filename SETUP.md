# 🚀 Step-by-Step Setup Guide

Follow these steps carefully to set up your SecureNotes application.

## ⏱️ Estimated Time: 15-20 minutes

---

## Step 1: Firebase Project Setup (5 min)

### 1.1 Create Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Click **"Add Project"** or **"Create a Project"**
3. Enter project name: `secure-notes` (or your choice)
4. **Analytics**: Optional (you can disable it)
5. Click **"Create Project"**
6. Wait for project to be ready
7. Click **"Continue"**

✅ **Checkpoint**: You should now see your Firebase project dashboard

---

## Step 2: Enable Firebase Authentication (3 min)

### 2.1 Set Up Google Authentication

1. In the left sidebar, click **"Authentication"**
2. Click **"Get Started"**
3. Click on the **"Sign-in method"** tab
4. Click on **"Google"** provider
5. Toggle **"Enable"** switch to ON
6. **Project support email**: Select your email
7. Click **"Save"**

### 2.2 Add Authorized Domain

1. Still in Authentication → Sign-in method
2. Scroll down to **"Authorized domains"**
3. You should see `localhost` and `[your-project].firebaseapp.com`
4. Click **"Add domain"**
5. Add: `[your-github-username].github.io`
   - Example: `johndoe.github.io`
6. Click **"Add"**

✅ **Checkpoint**: Google sign-in should show "Enabled" status

---

## Step 3: Enable Firestore Database (3 min)

### 3.1 Create Database

1. In the left sidebar, click **"Firestore Database"**
2. Click **"Create database"**
3. **Mode**: Select **"Start in production mode"**
   - Don't worry, we'll add rules next
4. **Location**: Choose closest to your location
   - Example: `us-central` for USA
   - Example: `europe-west` for Europe
5. Click **"Enable"**
6. Wait for database to be created

### 3.2 Set Security Rules

1. Click on the **"Rules"** tab
2. **Delete** all existing text
3. Copy the contents from `firestore.rules` file
4. **Paste** into the rules editor
5. Click **"Publish"**

✅ **Checkpoint**: You should see "Rules published successfully"

---

## Step 4: Get Firebase Configuration (2 min)

### 4.1 Create Web App

1. Click the **gear icon** (⚙️) next to "Project Overview"
2. Click **"Project settings"**
3. Scroll down to **"Your apps"** section
4. Click the **"<\/>"** icon (Web)
5. **App nickname**: `SecureNotes Web`
6. **Firebase Hosting**: Leave unchecked
7. Click **"Register app"**

### 4.2 Copy Configuration

1. You'll see a `firebaseConfig` object
2. **COPY** this entire object:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXX",
  authDomain: "your-project.firebaseapp.com",
  projectId: "your-project-id",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:xxxxx"
};
```

3. Click **"Continue to console"**

✅ **Checkpoint**: You have your Firebase config copied

---

## Step 5: Configure Application (5 min)

### 5.1 Edit index.html

1. Open `index.html` in your text editor
2. Find line ~865 with `firebaseConfig`
3. **Replace** the placeholder config with YOUR config:

```javascript
// BEFORE (placeholder)
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_AUTH_DOMAIN",
    // ...
};

// AFTER (your actual config)
const firebaseConfig = {
    apiKey: "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXX",
    authDomain: "your-project.firebaseapp.com",
    // ... (paste your values)
};
```

### 5.2 Set Authorized Email

1. Find line ~873 with `AUTHORIZED_EMAIL`
2. **Replace** with YOUR Google email:

```javascript
// BEFORE
const AUTHORIZED_EMAIL = "your-email@gmail.com";

// AFTER
const AUTHORIZED_EMAIL = "john.doe@gmail.com";
```

⚠️ **IMPORTANT**: Use the exact email you'll sign in with!

3. **Save** the file

✅ **Checkpoint**: Your app is configured with Firebase

---

## Step 6: GitHub Repository Setup (3 min)

### 6.1 Create Repository

1. Go to [GitHub](https://github.com/)
2. Click **"New repository"** (+ icon)
3. **Repository name**: `secure-notes`
4. **Description**: Personal secure notes application
5. **Public** or **Private**: Your choice
6. **Do NOT** initialize with README
7. Click **"Create repository"**

### 6.2 Push Code

In your terminal:

```bash
# Navigate to project folder
cd path/to/secure-notes

# Initialize git (if not already)
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: SecureNotes app"

# Add remote
git remote add origin https://github.com/[username]/secure-notes.git

# Push to GitHub
git branch -M main
git push -u origin main
```

✅ **Checkpoint**: Code is on GitHub

---

## Step 7: Enable GitHub Pages (2 min)

### 7.1 Configure Pages

1. Go to your GitHub repository
2. Click **"Settings"** tab
3. Scroll to **"Pages"** in left sidebar
4. **Source**: Select "GitHub Actions"
5. Wait ~30 seconds

### 7.2 Trigger Deployment

The GitHub Action should run automatically. To verify:

1. Click **"Actions"** tab
2. You should see "Deploy to GitHub Pages" workflow
3. Wait for green checkmark ✅
4. Deployment URL: `https://[username].github.io/secure-notes`

✅ **Checkpoint**: App is deployed!

---

## Step 8: Test Your Application (2 min)

### 8.1 Open Application

1. Visit: `https://[username].github.io/secure-notes`
2. You should see the login screen

### 8.2 Test Login

1. Click **"Continue with Google"**
2. Select your Google account
3. If email matches `AUTHORIZED_EMAIL`: You're in! 🎉
4. If email doesn't match: You'll be logged out

### 8.3 Test Features

1. **Create Note**: Click + button
2. **Add Title & Content**
3. **Add Tags**: Type tag name, press Enter
4. **Pin Note**: Check the pin checkbox
5. **Save Note**: Click "Save Note"
6. **Edit Note**: Click on the note
7. **Search**: Type in search bar
8. **Delete Note**: Click trash icon
9. **Theme**: Click moon/sun icon

✅ **Checkpoint**: Everything works!

---

## 🎉 Congratulations!

Your SecureNotes application is now:
- ✅ Deployed to GitHub Pages
- ✅ Connected to Firebase
- ✅ Secured with authentication
- ✅ Restricted to your email
- ✅ Auto-deploying on every push

---

## 📱 Next Steps

### Add to Home Screen (Mobile)

**iOS (Safari)**:
1. Open app in Safari
2. Tap Share button
3. Tap "Add to Home Screen"
4. Tap "Add"

**Android (Chrome)**:
1. Open app in Chrome
2. Tap menu (⋮)
3. Tap "Add to Home Screen"
4. Tap "Add"

### Customize

- **Colors**: Edit CSS variables in `index.html`
- **Fonts**: Change Google Fonts import
- **Features**: Add your own features!

---

## ⚠️ Troubleshooting

### Issue: Login button doesn't work
**Solution**: Check authorized domains in Firebase Console

### Issue: "Unauthorized access" message
**Solution**: Verify `AUTHORIZED_EMAIL` matches your Google account exactly

### Issue: Notes don't save
**Solution**: 
1. Check Firestore rules are published
2. Verify Firebase config is correct
3. Check browser console for errors

### Issue: App shows 404
**Solution**: 
1. Wait 2-3 minutes for GitHub Pages to build
2. Check GitHub Actions completed successfully
3. Verify repository name in URL

### Issue: Changes don't appear
**Solution**:
1. Clear browser cache
2. Wait for new deployment
3. Try incognito/private window

---

## 🆘 Need Help?

1. **Check Firebase Console** → Logs
2. **Check Browser Console** (F12)
3. **Check GitHub Actions** → Logs
4. **Review README.md** → Troubleshooting section

---

## 📚 Additional Resources

- [Firebase Documentation](https://firebase.google.com/docs)
- [GitHub Pages Guide](https://pages.github.com/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

---

**Enjoy your new SecureNotes app! 📝✨**
