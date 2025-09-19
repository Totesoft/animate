# EventCraft Pro

Professional event invitation and greeting card design platform with automated code obfuscation for production deployment.

## Features

- **Birthday Wishes**: Create animated text-based birthday messages
- **Greeting Cards**: Design personalized cards with templates
- **Party Invitations**: Create e-vites with RSVP functionality
- **Social Login**: Google OAuth integration for user authentication
- **Save & Share**: Authenticated users can save and share their creations

## Social Login Implementation

### Current Setup
- **Google OAuth Client ID**: `132435517223-cgvv1befsebst3113v3nh9ie9hg9ur9u.apps.googleusercontent.com`
- **Library**: Google Identity Services (`https://accounts.google.com/gsi/client`)
- **Callback**: `handleCredentialResponse()` function at `index.html:1967`

### Key Components
- **Login Button**: Google Sign-In button in navigation bar
- **User Management**: Login/logout functionality with user info display
- **Authentication Flow**: JWT token decoding and user session management

### Recent Fixes (2025-09-17)
1. **Fixed Google Sign-In button visibility** - Removed `display: none` from `.g_id_signin` div
2. **Removed redundant client ID configuration** - Eliminated duplicate JavaScript setting
3. **Streamlined login flow** - Button now visible by default in navigation

### Files Structure
- `index.html` - Complete SPA with all functionality
- Authentication code: Lines 1966-2024
- Login UI: Lines 1244-1267
- Google library load: Line 7

### Authentication Functions
- `handleCredentialResponse()` - Processes Google OAuth response
- `decodeJwtResponse()` - Decodes JWT token from Google
- `showLogin()` - Shows login interface
- `showUserLoggedIn()` - Updates UI after successful login
- `logout()` - Clears user session

### User Data Management
- Saves user evites and RSVP data
- Links saved content to user ID
- Provides dashboard for managing saved items

## Usage
1. Open `index.html` in a web browser
2. Click "Sign in with Google" in the navigation
3. Authenticate with Google account
4. Access authenticated features (save, share, manage evites)

## Development Workflow

### Branch Structure
- **`development`** - Clean, readable development code
- **`production`** - Obfuscated code for deployment
- **`gh-pages`** - Auto-deployed from production branch

### Local Development

1. **Setup:**
   ```bash
   npm install
   git checkout development
   ```

2. **Development:**
   - Work on `development` branch
   - Code remains clean and readable
   - Test in browser: `index.html`

3. **Deploy to Production:**
   ```bash
   git add .
   git commit -m "Add new feature"
   git push origin development
   ```
   GitHub Actions automatically:
   - Merges to `production` branch
   - Obfuscates the code
   - Deploys to GitHub Pages

### Manual Build (Optional)
```bash
npm run build          # Obfuscate code
npm run backup-dev     # Backup original
npm run restore-dev    # Restore from backup
```

### Code Protection
- **JavaScript Obfuscation**: Variable/function name mangling
- **Control Flow Flattening**: Logic flow protection
- **String Array Encoding**: Base64 encoded strings
- **Dead Code Injection**: Anti-reverse engineering
- **Self-Defending**: Anti-debugging protection

## Technical Notes
- Pure HTML/CSS/JavaScript implementation
- No backend required for basic functionality
- Uses localStorage for client-side data persistence
- Google OAuth for authentication only (no backend auth)
- Automated obfuscation via GitHub Actions