# Node.js OAuth Demo (GitHub + Google)

This is a minimal Node.js backend that implements OAuth login using **GitHub** and **Google**, with no database or user authentication library like Passport.js.

It's designed to help you understand the full OAuth flow — from redirecting users to a provider, to handling the callback, exchanging the code for a token, and retrieving user info.

YouTube: [OAuth 2.0 in Node.js](https://youtu.be/OfEwYw3byJc?si=H3gJVfQLlyWYPqN5)

---

## 🌐 Live Flow

1. User clicks "Login with GitHub" or "Login with Google"
2. User is redirected to the provider's login/consent screen
3. After approval, the provider redirects back to your backend with a `code`
4. Your backend exchanges the code for an access token
5. User info (name and email) is fetched and logged

---

## 🧰 Tech Stack

- Node.js
- Express
- Axios
- dotenv

---

## 📦 Setup

```bash
git clone https://github.com/your-username/nodejs-oauth-demo.git
cd nodejs-oauth-demo
npm install
```
### Environment Variables

Create a `.env` file in the root directory and add your GitHub and Google credentials:

```bash
# GitHub OAuth
GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret

# Google OAuth
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret

```
### Run the Server

```bash
node index.js
```

The server will start on `http://localhost:4001`.

You can now visit `http://localhost:4001/auth/github` or `http://localhost:4001/auth/google` to initiate the OAuth flow.

## Plug this into your Next.js app
You can use this backend as an authentication provider for your Next.js app. Just make sure to set up the appropriate API routes in your Next.js app to handle the OAuth flow.

```javascript
// Login with GitHub
<button onClick={() => window.location.href = 'http://localhost:4001/auth/github'}>
  Login with GitHub
</button>

// Login with Google
<button onClick={() => window.location.href = 'http://localhost:4001/auth/google'}>
  Login with Google
</button>
```
