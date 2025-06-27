# Vibely 🌐

**Bridging Distances, Building Relationships**

Vibely is a modern, full-stack social media platform built with Next.js 14, designed to facilitate meaningful connections and conversations in a sleek, dark-themed interface. The platform enables users to share messages, engage with communities, and build lasting relationships through real-time interactions.

## ✨ Features

### Core Functionality
- **Message Sharing**: Create, view, and interact with messages in a Twitter-like interface
- **Threaded Conversations**: Reply to messages with nested comment threads
- **Community Integration**: Join and participate in organized communities
- **User Profiles**: Comprehensive user profiles with activity tracking
- **Real-time Updates**: Live activity feeds and notifications
- **Search & Discovery**: Find users, messages, and communities easily

### User Experience
- **Authentication**: Secure sign-in/sign-up with Clerk authentication
- **Onboarding**: Guided profile setup for new users
- **Responsive Design**: Seamless experience across desktop and mobile devices
- **Dark Theme**: Modern dark UI with carefully crafted color schemes
- **Interactive Elements**: Like, reply, repost, and share functionality

### Technical Features
- **Server-Side Rendering**: Fast page loads with Next.js 14 App Router
- **Database Integration**: MongoDB with Mongoose ODM for data persistence
- **File Uploads**: Image upload capabilities with UploadThing
- **Webhook Integration**: Real-time synchronization with Clerk webhooks
- **Type Safety**: Full TypeScript implementation
- **Form Validation**: Robust client-side and server-side validation with Zod

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: Radix UI primitives
- **Forms**: React Hook Form with Zod validation
- **Icons**: Lucide React

### Backend & Database
- **Database**: MongoDB
- **ODM**: Mongoose
- **Authentication**: Clerk
- **File Storage**: UploadThing
- **Webhooks**: Svix for webhook verification

### Development Tools
- **Linting**: ESLint with Next.js config
- **Styling**: PostCSS, Autoprefixer
- **Type Checking**: TypeScript strict mode

## 📁 Project Structure

```
vibely/
├── app/                          # Next.js 14 App Router
│   ├── (auth)/                   # Authentication routes
│   │   ├── layout.tsx           # Auth layout with Clerk
│   │   ├── onboarding/          # User onboarding flow
│   │   ├── sign-in/             # Sign-in pages
│   │   └── sign-up/             # Sign-up pages
│   ├── (root)/                   # Main application routes
│   │   ├── layout.tsx           # Main layout with sidebars
│   │   ├── page.tsx             # Home feed
│   │   ├── activity/            # User activity page
│   │   ├── communities/         # Community pages
│   │   ├── create-message/      # Message creation
│   │   ├── profile/             # User profiles
│   │   ├── search/              # Search functionality
│   │   └── thread/              # Message threads
│   ├── api/                      # API routes
│   │   ├── uploadthing/         # File upload endpoints
│   │   └── webhook/             # Clerk webhook handlers
│   └── globals.css              # Global styles
├── components/                   # Reusable UI components
│   ├── cards/                   # Card components
│   │   ├── CommunityCard.tsx    # Community display
│   │   ├── MessageCard.tsx      # Message display
│   │   └── UserCard.tsx         # User profile cards
│   ├── forms/                   # Form components
│   │   ├── AccountProfile.tsx   # Profile management
│   │   ├── Comment.tsx          # Comment forms
│   │   ├── DeleteMessage.tsx    # Message deletion
│   │   └── PostMessage.tsx      # Message creation
│   ├── shared/                  # Shared layout components
│   │   ├── Bottombar.tsx        # Mobile navigation
│   │   ├── LeftSidebar.tsx      # Desktop sidebar
│   │   ├── RightSidebar.tsx     # Additional content sidebar
│   │   ├── Topbar.tsx           # Top navigation
│   │   └── ...                  # Other shared components
│   └── ui/                      # Base UI components (shadcn/ui)
├── lib/                         # Utility functions and configurations
│   ├── actions/                 # Server actions
│   │   ├── community.actions.ts # Community CRUD operations
│   │   ├── message.actions.ts   # Message CRUD operations
│   │   └── user.actions.ts      # User CRUD operations
│   ├── models/                  # Mongoose schemas
│   │   ├── community.model.ts   # Community data model
│   │   ├── message.model.ts     # Message data model
│   │   └── user.model.ts        # User data model
│   ├── validations/             # Zod schemas
│   ├── mongoose.ts              # Database connection
│   └── utils.ts                 # Utility functions
├── constants/                   # Application constants
└── public/                      # Static assets
    └── assets/                  # SVG icons and images
```

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ and npm/yarn
- MongoDB database (local or cloud)
- Clerk account for authentication
- UploadThing account for file uploads

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd connect
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment setup**
   Create a `.env.local` file in the root directory:
   ```env
   # Database
   MONGODB_URL=your_mongodb_connection_string
   
   # Clerk Authentication
   NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
   CLERK_SECRET_KEY=your_clerk_secret_key
   NEXT_CLERK_WEBHOOK_SECRET=your_clerk_webhook_secret
   
   # UploadThing
   UPLOADTHING_SECRET=your_uploadthing_secret
   UPLOADTHING_APP_ID=your_uploadthing_app_id
   ```

4. **Database setup**
   Ensure your MongoDB database is running and accessible via the connection string.

5. **Start the development server**
   ```bash
   npm run dev
   ```

6. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

### Deployment

The application is ready for deployment on platforms like Vercel, Netlify, or any Node.js hosting service:

```bash
npm run build
npm start
```

## 🔧 Configuration

### Clerk Authentication Setup
1. Create a Clerk application
2. Configure OAuth providers (optional)
3. Set up webhooks for organization sync
4. Add environment variables

### Database Schema
The application uses three main models:
- **User**: Stores user profile information and relationships
- **Message**: Handles posts and threaded conversations
- **Community**: Manages community data and memberships

### Webhook Configuration
Set up Clerk webhooks to sync organization data:
- Organization created/updated/deleted
- Membership changes
- Invitation management

## 🎨 Customization

### Styling
- **Colors**: Modify the color scheme in `tailwind.config.js`
- **Components**: Customize UI components in the `components/ui/` directory
- **Layout**: Adjust layouts in the `app/(root)/layout.tsx` and `app/(auth)/layout.tsx`

### Features
- **Add new page routes**: Create new directories under `app/(root)/`
- **Extend models**: Modify schemas in `lib/models/`
- **Add server actions**: Create new actions in `lib/actions/`

## 📱 Usage

### For Users
1. **Sign up/Sign in**: Create an account or log in with existing credentials
2. **Complete onboarding**: Set up your profile with username, bio, and profile picture
3. **Explore**: Browse the home feed, search for users, or discover communities
4. **Engage**: Create messages, reply to conversations, and interact with the community
5. **Manage profile**: Update your information and view your activity

### For Communities
1. **Create communities**: Organize around topics or interests
2. **Manage members**: Add or remove community members
3. **Community content**: Share messages within specific communities
4. **Moderation**: Community leaders can manage content and membership

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License.


