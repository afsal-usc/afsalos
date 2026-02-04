# AfsalOS - Interactive Portfolio

An interactive portfolio website that simulates a Windows-like operating system experience, built entirely with HTML, CSS, and JavaScript. This single-file application runs entirely in the browser and provides a unique way to showcase your projects, skills, and personality.

## 🚀 Features

- **Desktop Environment**: Windows-like desktop with icons, folders, and applications
- **File Explorer**: Navigate through a virtual file system
- **Multiple Apps**: Terminal, Notepad, Calculator, Paint, Music Player, Snake Game, and more
- **AI Project Viewer**: Showcase your AI projects with video demos and descriptions
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **No Backend Required**: Everything runs client-side in a single HTML file

## 📁 Project Structure

```
afsalos/
├── afsalos.html          # Main HTML file (contains all code)
├── public/               # Public assets folder
│   ├── afsal.jpg         # Profile photo
│   ├── wallpaper.jpg     # Desktop wallpaper
│   ├── *.mp4            # Video files for projects
│   └── *.mp3            # Audio files for music player
└── README.md            # This file
```

## 🛠️ Setup Instructions

1. **Clone or download this repository**
   ```bash
   git clone <your-repo-url>
   cd afsalos
   ```

2. **Add your assets to the `public/` folder**
   - Add your profile photo (rename to match the reference in code)
   - Add your wallpaper image
   - Add any video files for project demos
   - Add audio files for the music player

3. **Open `afsalos.html` in a browser**
   - Simply double-click the file or open it in any modern web browser
   - No server or build process required!

## 🎨 Customization Guide

### 1. Personal Information

#### Update Profile Photo
- Replace `public/afsal.jpg` with your own photo
- Or update the path in the code:
  ```javascript
  // Line ~732: In createAboutMe function
  <img src="public/afsal.jpg" alt="Your Name">
  ```

#### Update About Me Section
- Find the `createAboutMe` function (around line 726)
- Update the name, title, and description:
  ```javascript
  <h1>Your Name</h1>
  <p>Your Title • Your Tagline</p>
  <p>Your bio and description...</p>
  ```

#### Update Contact Information
- Edit `'Get in Touch.txt'` in the VFS (around line 558):
  ```javascript
  'Get in Touch.txt': { 
      type: 'file', 
      ext: 'txt', 
      content: '📧 GET IN TOUCH\n\nEmail: your@email.com\n\n...' 
  }
  ```

### 2. Desktop Wallpaper

- Replace `public/wallpaper.jpg` with your own wallpaper
- Or update the CSS variable (line ~25):
  ```css
  --Wallpaper: url('public/your-wallpaper.jpg');
  ```

### 3. Desktop Icons

#### Change Icon Order
- Edit the `initDesktop` function (around line 1850)
- Modify the order of apps and files:
  ```javascript
  // Step 1: Add About Me
  // Step 2: Add AI Experiments folder
  // Step 3: Add apps (my-music, terminal, etc.)
  // Step 4: Add files (Getting Started.txt, etc.)
  ```

#### Add/Remove Desktop Icons
- To add an app icon, add it to the `desktopApps` array
- To remove an icon, remove it from the array or the initialization code

### 4. AI Experiments / Projects

#### Add a New Project
1. Add your video file to the `public/` folder
2. Edit the VFS structure (around line 569):
   ```javascript
   'AI Experiments': { 
       type: 'folder', 
       children: {
           'Your Project Name': { 
               type: 'file', 
               ext: 'aiproject', 
               projectType: 'your-project-type', 
               videoPath: 'public/YourVideo.mp4', 
               title: 'Your Project Name', 
               icon: 'fa-solid fa-icon-name',  // Font Awesome icon
               description: 'Your project description...' 
           }
       }
   }
   ```

#### Change Project Order
- Reorder the items in the `children` object (order matters)

#### Custom Icons
- Use Font Awesome icons: `fa-solid fa-icon-name`
- Examples: `fa-phone`, `fa-baseball-bat-ball`, `fa-shirt`, `fa-robot`
- Browse icons at: https://fontawesome.com/icons

### 5. Music Player

#### Add Your Music
1. Add audio file to `public/` folder
2. Update the music player (around line 1352):
   ```javascript
   <source src="public/YourSong.mp3" type="audio/mpeg">
   ```
3. Update track name (around line 1337):
   ```javascript
   <div class="wmp-track-name">Your Song Name</div>
   ```

#### Update Music Links
- Edit the YouTube and Instagram links in the music player section

### 6. Terminal Commands

#### Add Custom Commands
- Edit the `processCommand` function (around line 855)
- Add new cases to the switch statement:
   ```javascript
   case 'yourcommand':
       output('Your command output');
       break;
   ```

#### Update Terminal Welcome Message
- Edit the `createTerminal` function (around line 827)
- Modify the `welcomeMessage` variable

### 7. Start Menu Apps

#### Add/Remove Apps from Start Menu
- Edit the `initStartMenu` function (around line 1949)
- Modify the `startMenuApps` array:
   ```javascript
   const startMenuApps = ['calculator', 'terminal', 'paint', 'game', 'my-music'];
   ```

### 8. File System (VFS)

#### Add Files/Folders
- Edit the VFS structure (around line 560)
- Add new entries to the `children` object:
   ```javascript
   'Desktop': {
       type: 'folder',
       children: {
           'Your Folder': {
               type: 'folder',
               children: { /* ... */ }
           },
           'Your File.txt': {
               type: 'file',
               ext: 'txt',
               content: 'Your file content...'
           }
       }
   }
   ```

#### File Types Supported
- `txt`: Opens in Notepad
- `js`: Opens in Code Editor
- `aiproject`: Opens in AI Project Viewer
- `folder`: Opens in File Explorer

### 9. Styling & Colors

#### Change Color Scheme
- Edit CSS variables (around line 15):
   ```css
   :root {
       --accent-color: #0078d4;  /* Your accent color */
       --bg-color: #f3f3f3;       /* Background color */
       --text-color: #222;        /* Text color */
   }
   ```

#### Dark Mode
- Dark mode styles are already included (around line 28)
- Automatically activates based on system preferences
- Customize dark mode colors in the `@media (prefers-color-scheme: dark)` section

### 10. Window Titles & App Names

#### Change App Titles
- Edit the `AppRegistry` (around line 533):
   ```javascript
   const AppRegistry = {
       'app-id': { 
           title: 'Your App Name', 
           icon: 'fa-solid fa-icon', 
           color: '#colorcode', 
           func: createFunction 
       }
   };
   ```

## 📱 Mobile Responsiveness

The portfolio is fully responsive and works on mobile devices:
- Desktop icons scroll horizontally
- Windows take full screen on mobile
- Touch-friendly interactions
- Optimized font sizes and spacing

To customize mobile styles, edit the `@media (max-width: 768px)` section (around line 345).

## 🎯 Quick Customization Checklist

- [ ] Replace profile photo (`public/afsal.jpg`)
- [ ] Update name and bio in `createAboutMe` function
- [ ] Replace wallpaper (`public/wallpaper.jpg`)
- [ ] Update contact information in `Get in Touch.txt`
- [ ] Add your projects to `AI Experiments` folder
- [ ] Update music player with your tracks
- [ ] Customize terminal commands
- [ ] Update color scheme
- [ ] Add/remove desktop icons
- [ ] Update Start Menu apps

## 🔧 Advanced Customization

### Adding a New App

1. Create the app function:
   ```javascript
   function createYourApp(container, filePath, winId) {
       container.innerHTML = `
           <div>Your app content here</div>
       `;
   }
   ```

2. Register it in `AppRegistry`:
   ```javascript
   'your-app': { 
       title: 'Your App', 
       icon: 'fa-solid fa-icon', 
       color: '#color', 
       func: createYourApp 
   }
   ```

3. Add it to desktop/start menu if desired

### Adding a New File Type

1. Add file type handling in File Explorer (around line 1002):
   ```javascript
   if(item.ext === 'yourtype') WindowManager.open('your-app', currentPath + '/' + key);
   ```

2. Add icon styling (around line 183):
   ```css
   .file-item[data-type="yourtype"] i { color: #color; }
   ```

## 📝 Notes

- All code is in a single HTML file for easy deployment
- No external dependencies except Font Awesome and Monaco Editor (for code editor)
- Videos and images are loaded from the `public/` folder
- The virtual file system (VFS) is stored in memory
- All data is client-side only (no backend required)


## 📄 License

Feel free to use this project as a template for your own portfolio. Customize it to your heart's content!

## 🙏 Credits

Built with:
- Font Awesome for icons
- Monaco Editor for code editing
- Pure HTML, CSS, and JavaScript

---

**Happy Customizing!** 🎨

If you have questions or need help customizing, feel free to open an issue or reach out!
