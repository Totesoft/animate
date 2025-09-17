# Birthday Animation SPA

A single-page application for creating animated birthday wishes, greeting cards, and party invitations.

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

## Technical Notes
- Pure HTML/CSS/JavaScript implementation
- No backend required for basic functionality
- Uses localStorage for client-side data persistence
- Google OAuth for authentication only (no backend auth)