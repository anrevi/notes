# ⚡ Quick Reference Card

## 🔑 Essential Config

### Firebase Config (index.html line ~865)
```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "your-project.firebaseapp.com",
    projectId: "your-project-id",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "123456789",
    appId: "1:123456789:web:xxxxx"
};
```

### Authorized Email (index.html line ~873)
```javascript
const AUTHORIZED_EMAIL = "your-email@gmail.com";
```

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl/Cmd + K` | Focus search |
| `Ctrl/Cmd + N` | New note |
| `Esc` | Close modal |

---

## 🎨 UI Elements

### Header
- **App Title** - Click to refresh
- **🌙/☀️ Icon** - Toggle dark/light theme
- **👤 Icon** - Logout

### Note Card
- **📌/📍** - Pin/Unpin note
- **✏️** - Edit note
- **🗑️** - Delete note (no undo!)

### Modal
- **Tags** - Type tag, press Enter to add
- **×** - Click to remove tag
- **📌 Checkbox** - Pin important notes

---

## 🔍 Search Tips

- Search by **title**
- Search by **content**
- Search by **tags**
- Case-insensitive
- Instant results

---

## 📱 Mobile Features

### Touch Gestures
- **Tap note** - Edit
- **Swipe** - Scroll through notes
- **Pull down** - Refresh (browser native)

### Add to Home Screen
**iOS**: Share → Add to Home Screen
**Android**: Menu → Add to Home Screen

---

## 🚨 Important Notes

### ⚠️ Security
- Only ONE email can access
- Other users see "Unauthorized" message
- Change `AUTHORIZED_EMAIL` to update access

### 💾 Data Storage
- Data stored in Firebase Firestore
- Automatic offline sync
- No data loss during offline mode

### 🔄 Updates
- Push to GitHub → Auto-deploys
- Takes 1-2 minutes
- Clear cache if changes don't appear

---

## 🐛 Quick Fixes

### Can't Login?
1. Check Firebase authorized domains
2. Verify `AUTHORIZED_EMAIL` matches
3. Clear cookies and cache

### Notes Not Saving?
1. Check Firestore rules published
2. Verify Firebase config correct
3. Open browser console (F12)

### App Not Loading?
1. Wait 2-3 minutes for deployment
2. Clear browser cache
3. Try incognito/private window

---

## 📊 File Sizes

- `index.html`: ~50KB (all-in-one)
- Firebase SDK: ~200KB (CDN)
- Total Load: ~250KB (very fast!)

---

## 🎯 Best Practices

### Note Organization
- ✅ Use descriptive titles
- ✅ Add relevant tags
- ✅ Pin important notes
- ✅ Regular cleanup

### Security
- ✅ Keep Firebase config private
- ✅ Don't share API keys
- ✅ Review authorized domains
- ✅ Monitor Firebase usage

### Performance
- ✅ Limit notes to ~1000 for best performance
- ✅ Delete unused notes
- ✅ Use tags instead of many small notes

---

## 🔗 Quick Links

- **Firebase Console**: https://console.firebase.google.com/
- **GitHub Pages**: `https://[username].github.io/secure-notes`
- **Repository Settings**: GitHub → Settings → Pages
- **GitHub Actions**: GitHub → Actions tab

---

## 💡 Pro Tips

1. **Backup**: Export notes occasionally (future feature)
2. **Tags**: Use consistent naming (e.g., `work`, `personal`, `urgent`)
3. **Search**: Use specific keywords for faster results
4. **Offline**: Works perfectly offline, syncs when back
5. **Theme**: Auto-saves your preference

---

## 📞 Emergency Commands

### Firebase CLI
```bash
firebase login
firebase use your-project-id
firebase deploy --only firestore:rules
```

### Git Commands
```bash
git add .
git commit -m "Your message"
git push origin main
```

### Reset Local Database
```bash
# In browser console (F12)
localStorage.clear();
location.reload();
```

---

**Keep this card handy! 📌**
