# Tasker Pro

AI-powered task and social media management platform with Cloudflare R2 storage integration.

## Features

- 🤖 **AI-Powered Content Generation** - Create engaging content and manage tasks with Google AI
- 📅 **Smart Scheduling** - Schedule posts and tasks at optimal times
- 🎭 **AI Agents** - Create custom AI personas for different content styles
- 📸 **Media Management** - Upload and optimize images/videos with automatic compression
- ☁️ **Cloudflare R2 Storage** - Zero egress fees for media delivery
- 🔐 **Secure Authentication** - Google OAuth integration via Supabase
- 📊 **Analytics Dashboard** - Track performance, engagement, and productivity

## Quick Setup

### 1. Environment Variables

Create a `.env` file with your credentials:

```env
# Supabase Configuration
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key

# Cloudflare R2 Configuration (Pre-configured)
VITE_CLOUDFLARE_R2_ACCOUNT_ID=your_account_id_here
VITE_CLOUDFLARE_R2_ACCESS_KEY_ID=your_access_key_id_here
VITE_CLOUDFLARE_R2_SECRET_ACCESS_KEY=your_secret_access_key_here
VITE_CLOUDFLARE_R2_BUCKET_NAME=tasker
VITE_CLOUDFLARE_R2_ENDPOINT=https://your_account_id.r2.cloudflarestorage.com
```

### 2. Create R2 Bucket

1. Log into your Cloudflare dashboard
2. Navigate to R2 Object Storage
3. Create a new bucket named `tasker`
4. Generate R2 API tokens with read/write permissions
5. Copy your credentials to the .env file
6. Test the connection in Settings → Cloudflare R2 Storage

### 3. Install Dependencies

```bash
npm install
```

### 4. Run Development Server

```bash
npm run dev
```

## R2 Storage Benefits

- **Zero Egress Fees**: No charges for file downloads/delivery
- **Global CDN**: Fast media delivery worldwide
- **S3 Compatible**: Uses proven AWS SDK
- **Cost Effective**: Significantly cheaper than traditional cloud storage

## Media Optimization

All uploaded media is automatically optimized:

- **Images**: Compressed to optimal quality while maintaining visual fidelity
- **Automatic Resizing**: Scaled to appropriate dimensions for social media
- **Format Conversion**: Converted to web-optimized formats
- **Size Reduction**: Typically 40-70% smaller file sizes

## AI Features

### Content Generation
- Generate tweets based on prompts and tone
- Analyze uploaded images to create contextual content
- Improve existing tweets with AI suggestions

### AI Agents
- Create custom AI personas with unique personalities
- Define expertise areas, writing styles, and example posts
- Generate content that matches specific brand voices

## Tech Stack

- **Frontend**: React + TypeScript + Tailwind CSS
- **Backend**: Supabase (PostgreSQL + Auth + Edge Functions)
- **Storage**: Cloudflare R2 (S3-compatible)
- **AI**: Google Gemini API
- **Build Tool**: Vite
- **Deployment**: Netlify

## Database Schema

The application uses several key tables:

- `profiles` - User profile information
- `agents` - AI agent configurations
- `tweets` - Tweet content and scheduling
- `media_library` - Media file metadata and optimization stats
- `user_settings` - User preferences and API keys

## Security

- All API keys stored locally in browser
- Row Level Security (RLS) enabled on all database tables
- Secure OAuth authentication via Supabase
- Direct client-to-R2 uploads (no server intermediary)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

MIT License - see LICENSE file for details