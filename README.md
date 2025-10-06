# Zen Dashboard

A minimal and zen full-stack dashboard application for managing tasks, study sessions, habits, and university applications. Features a calming beige and matcha green color palette designed for focused productivity.

## Features

### 🍵 Zen Design Philosophy
- **Minimal & Clean**: Soft beige and matcha green color palette
- **Gentle Animations**: Smooth, calming transitions (0.4-0.6s duration)
- **Typography**: Light font weights for a peaceful reading experience
- **Backdrop Blur**: Frosted glass effects for depth and tranquility
- **Soft Shadows**: Subtle elevation without harsh contrasts

### 📊 Dashboard Overview
- **AI Daily Briefing**: Personalized daily summary with insights, suggestions, and trend analysis powered by Google Gemini AI
- **Upcoming Deadlines Widget**: Track assignment and application deadlines with priority indicators
- **Enhanced Study Timer**: Three modes - Custom, Pomodoro (configurable work/break cycles), and Deepwork (90-minute focused sessions)
- **Brain.fm Integration**: Embedded music player for focus-enhancing soundtracks
- **Recurring Habits**: Daily/weekly/monthly habit tracking with streak visualization and 90-day heatmap
- **Quick Links Panel**: Customizable shortcuts to frequently used websites
- **Global Search**: AI-powered search across all your tasks, deadlines, and universities
- **System Status Indicator**: Real-time monitoring of backend health

### 🤖 AI-Powered Features
- **Daily Briefing**: Get personalized insights about your productivity patterns each day
- **Trend Analysis**: AI identifies improving, declining, or stable trends in tasks, study, and habits
- **Smart Task Suggestions**: AI automatically suggests tasks based on your upcoming deadlines
- **Performance Predictions**: Receive recommendations to optimize your productivity

### 🎯 Enhanced Study Timer
- **Pomodoro Mode**: Customizable work/break intervals (default: 25/5 min) with automatic break reminders
- **Deepwork Mode**: 90-minute focused study sessions
- **Custom Mode**: Flexible timing for any study approach
- **Session History**: Track all study sessions with notes and timer modes
- **Visual Progress**: See progress bars and cycle indicators during Pomodoro sessions
- **Sound Notifications**: Gentle chimes when timers complete

### 📈 Performance Dashboard
- **Analytics Overview**: View tasks completed, study hours, habit streaks, and productivity scores
- **Visual Charts**: Line charts for daily metrics, donut charts for completion rates
- **Trend Analysis**: AI-powered insights about your productivity patterns
- **Time Periods**: Filter by 7, 30, or 90 days
- **Data Export**: Download your performance data as CSV

### 🔥 Habit Streak Visualizer
- **90-Day Heatmap**: Visual calendar showing completion patterns with matcha green gradient
- **Streak Stats**: Current streak, longest streak, and completion rate
- **Interactive Calendar**: Hover over days to see details
- **Recent Activity**: Quick view of the last 14 days

### 📝 Task Management
- Create, update, and delete tasks
- Priority levels (low, medium, high, urgent)
- Categories (course, application, personal, other)
- Status tracking (pending, in-progress, completed)
- Due date management

### 🎓 University Applications
- Track multiple university applications
- Manage application requirements with checklists
- Priority classification (safety, target, reach)
- Status updates (not-started, in-progress, submitted, accepted, rejected)
- Progress tracking for each application
- Delete universities you're no longer targeting

### 🎵 Brain.fm Music Integration
- Embedded player for focus-enhancing music
- Expandable/collapsible widget
- Seamlessly integrated into zen dashboard design
- Perfect companion for Pomodoro and Deepwork sessions

### 🔊 Zen Sound Design
- **Tactile Audio Feedback**: Keyboard-like click/clack sounds using Web Audio API (no files needed)
- **Timer Completion**: Satisfying double-click when study sessions finish
- **Break Reminders**: Descending click sequence for Pomodoro breaks
- **Task Completion**: Rewarding click-clack sequence for completed tasks
- **Habit Checks**: Single crisp click for habit completion
- **Navigation**: Subtle click when changing pages
- **Sound Toggle**: Floating control button (bottom right) to enable/disable sounds
- **Pure Web Audio**: Generated using oscillators and noise for realistic mechanical feel

### ⏱️ Study Sessions
- Start/stop/pause timer functionality
- Session history with duration tracking
- Subject and notes for each session
- Visual timer display

### 🔄 Habit Tracking
- Create daily, weekly, or monthly habits
- Check off completed habits
- Streak counting
- Visual progress indicators

## Tech Stack

### Frontend
- **React 18** with TypeScript
- **Vite** for build tooling
- **React Router** for navigation
- **React Query** for server state management
- **Zustand** for client state management
- **Framer Motion** for animations (0.5-0.6s duration for zen feel)
- **Tailwind CSS** for styling with custom beige/matcha palette
- **Lucide React** for icons
- **date-fns** for date manipulation
- **Web Audio API** for sound design

### Backend
- **Express.js** with TypeScript
- **Google Generative AI** (Gemini) for AI features
- **Node-cron** for scheduled tasks
- **dotenv** for environment configuration
- **JSON file-based storage** for simplicity
- RESTful API design
- CORS enabled

### Testing
- **Vitest** for unit testing
- **Testing Library** for React component testing
- **Supertest** for API integration testing

## Installation

### Prerequisites
- Node.js 18+ installed
- npm or yarn package manager
- Google Gemini API key (get one at https://makersuite.google.com/app/apikey)
- Brain.fm subscription (for music player functionality)

### Setup

1. **Clone or extract the project**

2. **Install all dependencies**
   ```bash
   npm run install:all
   ```

   This will install dependencies for the root, client, and server.

3. **Configure Your Gemini API Key**
   
   You have two options:
   
   **Option A - In the UI (Recommended)**:
   - Start the app and navigate to Settings
   - Enter your Gemini API key
   - Click "Save API Key"
   - Your key is stored locally in your browser only
   
   **Option B - Server Environment Variable**:
   - Create a `.env` file in the `server/` directory
   - Add: `GEMINI_API_KEY=your_key_here`
   - This serves as a fallback if no key is set in the UI
   
   Get your free API key from [Google AI Studio](https://makersuite.google.com/app/apikey)

4. **Start the development servers**
   ```bash
   npm run dev
   ```

   This will start both the frontend (Vite) and backend (Express) servers concurrently.

   - Frontend: http://localhost:5173
   - Backend API: http://localhost:3000

## Usage

### Development

- **Client only**: `npm run dev:client`
- **Server only**: `npm run dev:server`
- **Both together**: `npm run dev`

### Testing

- **Run all tests**: `npm test`
- **Client tests**: `npm run test:client`
- **Server tests**: `npm run test:server`

### Building for Production

```bash
npm run build
```

This will build both the client and server for production.

### Important Notes

⚠️ **After modifying Tailwind configuration** (tailwind.config.js), you should restart the Vite dev server for changes to take effect:
```bash
# Stop the dev server (Ctrl+C)
npm run dev:client
```

## Project Structure

```
Dashboard/
├── client/                    # Frontend React application
│   ├── src/
│   │   ├── api/              # API client and React Query hooks
│   │   ├── components/       # React components
│   │   │   ├── global/       # Global components (search, status, links)
│   │   │   ├── layout/       # Layout components (sidebar)
│   │   │   ├── universities/ # University-specific components
│   │   │   └── widgets/      # Dashboard widgets
│   │   ├── pages/            # Page components
│   │   ├── store/            # Zustand state management
│   │   ├── styles/           # CSS styles
│   │   └── tests/            # Frontend tests
│   └── package.json
├── server/                    # Backend Express application
│   ├── data/                 # JSON data storage
│   ├── src/
│   │   ├── utils/            # Utility functions
│   │   ├── tests/            # Backend tests
│   │   └── index.ts          # Main server file
│   └── package.json
├── src/
│   └── types/                # Shared TypeScript types
└── package.json              # Root package.json
```

## Features in Detail

### AI Daily Briefing
The dashboard uses **Gemini 2.5 Pro** to generate a personalized daily briefing analyzing your:
- Tasks completed vs pending
- Study session frequency and duration
- Habit completion patterns
- Upcoming deadlines

The AI provides:
- A zen-like summary of your productivity state
- 3-4 key insights about your patterns
- 2-3 gentle suggestions for improvement
- Trend analysis across tasks, study, and habits

Briefings are cached daily to avoid regenerating and save API costs.

**Models Used**:
- **Gemini 2.5 Pro** (`gemini-2.5-pro`) - For briefings, suggestions, and trend analysis
- **Text Embedding 004** (`text-embedding-004`) - For semantic search functionality

### Pomodoro Timer
Configure your perfect Pomodoro rhythm:
- **Work Duration**: Default 25 minutes (customizable 1-90 min)
- **Break Duration**: Default 5 minutes (customizable 1-30 min)
- **Long Break**: Default 15 minutes (customizable 1-60 min)
- **Cycles Until Long Break**: Default 4 (customizable 2-10)

The timer automatically:
- Tracks which session you're on (e.g., "Session 2/4")
- Switches to breaks when work periods complete
- Plays different sounds for work completion vs break start
- Shows visual progress bars

### Sound Design Philosophy
All sounds are generated using the Web Audio API with tactile click/clack mechanics:
- **No audio files** - everything is code-generated
- **Keyboard-like feel** - square wave oscillators with noise texture for realism
- **Sharp attack, quick decay** - mechanical, satisfying feedback
- **Layered sounds** - click (press) + clack (release) sequences
- **Minimal duration** - 30-50ms for instant tactile feedback
- **Respectful** - easy to toggle off with floating control

### Performance Analytics
The performance page calculates:
- **Productivity Score**: Weighted formula based on tasks (×10) + study hours (×5) + habit streaks (×2)
- **Daily Aggregations**: Metrics calculated per day for trends
- **Completion Rates**: Tasks completed vs total tasks
- **Study Patterns**: Hours per day with visual line charts

## API Endpoints

### AI Endpoints
- `GET /api/ai/briefing` - Get today's AI briefing (cached)
- `GET /api/ai/trends?period=7d` - Get AI trend analysis
- `POST /api/ai/suggest-tasks` - Generate task suggestions from deadlines

### Performance
- `GET /api/performance/metrics?startDate&endDate` - Get performance data

### Pomodoro
- `GET /api/pomodoro/settings` - Get Pomodoro configuration
- `PUT /api/pomodoro/settings` - Update Pomodoro settings

### Tasks
- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create a new task
- `PUT /api/tasks/:id` - Update a task
- `DELETE /api/tasks/:id` - Delete a task

### Deadlines
- `GET /api/deadlines` - Get all deadlines
- `POST /api/deadlines` - Create a deadline
- `PUT /api/deadlines/:id` - Update a deadline
- `DELETE /api/deadlines/:id` - Delete a deadline

### Study Sessions
- `GET /api/study-sessions` - Get all study sessions
- `POST /api/study-sessions` - Create a session
- `PUT /api/study-sessions/:id` - Update a session
- `DELETE /api/study-sessions/:id` - Delete a session

### Habits
- `GET /api/habits` - Get all habits
- `POST /api/habits` - Create a habit
- `PUT /api/habits/:id` - Update a habit
- `DELETE /api/habits/:id` - Delete a habit

### Universities
- `GET /api/universities` - Get all universities
- `POST /api/universities` - Create a university
- `PUT /api/universities/:id` - Update a university
- `DELETE /api/universities/:id` - Delete a university

### Quick Links
- `GET /api/quick-links` - Get all quick links
- `POST /api/quick-links` - Create a quick link
- `PUT /api/quick-links/:id` - Update a quick link
- `DELETE /api/quick-links/:id` - Delete a quick link

### Search & System
- `GET /api/search?q=query` - Search across all data
- `GET /api/system-status` - Get system health status

## Data Storage

Data is stored in JSON files in the `server/data/` directory:
- `tasks.json` - Task data
- `deadlines.json` - Deadline data
- `study-sessions.json` - Study session data (now includes timer mode)
- `habits.json` - Habit data with completion dates
- `universities.json` - University application data
- `quick-links.json` - Quick links configuration
- `ai-briefings.json` - Cached daily AI briefings
- `performance-metrics.json` - Historical performance data
- `pomodoro-settings.json` - User's Pomodoro preferences

## AI Models & Configuration

### Gemini API Integration
This dashboard integrates with Google's Gemini API using the latest models:

**Gemini 2.5 Pro** (`gemini-2.5-pro`):
- State-of-the-art reasoning model
- Used for: Daily briefings, task suggestions, trend analysis
- Context window: Up to 2M tokens
- Knowledge cutoff: August 2024
- [Model documentation](https://ai.google.dev/gemini-api/docs/models)

**Text Embedding 004** (`text-embedding-004`):
- Latest embedding model for semantic understanding
- Used for: Intelligent semantic search across all data
- Output dimensions: 768
- [Embedding documentation](https://ai.google.dev/gemini-api/docs/embeddings)

**API Key Configuration**:
- Navigate to **Settings** page in the dashboard
- Enter your Gemini API key (get one free at [Google AI Studio](https://makersuite.google.com/app/apikey))
- Keys are stored in browser localStorage (client-side only)
- Keys are sent directly to Google's servers via secure headers
- We never store or see your API key on our backend

**Free Tier Limits**:
- 15 requests per minute
- 1,500 requests per day
- Briefings cached daily to minimize API usage
- Semantic search optional (falls back to keyword search)

## Customization

### Tailwind Theme
Edit `client/tailwind.config.js` to customize colors, spacing, and animations.

### Animation Duration
Framer Motion animations are configured with longer durations (0.4-0.6s) for better visibility. Adjust in individual components as needed.

### Quick Links
Add or modify quick links directly through the UI or by editing `server/data/quick-links.json`.

### Pomodoro Settings
Customize your work/break intervals in the Settings page or directly from the Study Timer widget.

## Troubleshooting

### AI Features Not Working
- **Check API Key**: Go to Settings page and enter your Gemini API key
- **Get API Key**: Visit [Google AI Studio](https://makersuite.google.com/app/apikey) for a free key
- **API Quota**: Free tier allows 15 req/min, 1,500 req/day - briefings are cached daily to minimize usage
- **Model**: Ensure you have access to Gemini 2.5 Pro (available in free tier)
- **Fallback Mode**: If AI is unavailable, the app provides default messages
- **Semantic Search**: Uses embedding model for intelligent search (falls back to keyword search if no API key)

### Port Already in Use
If ports 3000 or 5173 are already in use, you can change them:
- Client: Edit `client/vite.config.ts` → `server.port`
- Server: Set environment variable `PORT=<new-port>` in `.env`

### Styles Not Updating
After Tailwind config changes, restart Vite:
```bash
npm run dev:client
```

### API Connection Issues
Ensure the backend server is running on port 3000. Check the proxy configuration in `client/vite.config.ts`.

### Brain.fm Player Not Loading
- Ensure you have an active Brain.fm subscription at [brain.fm](https://www.brain.fm/)
- Log into Brain.fm in the same browser before using the dashboard
- Check browser console for iframe loading errors
- Some browsers may block iframes - check browser settings
- The iframe loads the full Brain.fm website for seamless integration

### Sounds Not Playing
- Click the sound control button (bottom right) to ensure sounds are enabled
- Check browser permissions for audio
- Some browsers require user interaction before playing audio

### Performance Data Missing
- Performance metrics are calculated from historical data
- Add some tasks, study sessions, and habits first
- Data aggregates over time - give it a few days for meaningful trends

## License

MIT

## Contributing

This is a personal dashboard application. Feel free to fork and customize for your own needs!

