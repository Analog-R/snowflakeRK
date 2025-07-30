# SnowflakeRK - Engineering Growth Framework Tool

## Project Overview

SnowflakeRK is a web-based interactive tool for visualizing and tracking engineering career progression based on Medium's engineering growth framework. The application provides a comprehensive system for evaluating engineers across multiple skill tracks and career levels.

## Quick Start

### Prerequisites
- Node.js 18.0.0 or higher
- npm (comes with Node.js) or Yarn

### Installation & Running
```bash
# Clone the repository
git clone https://github.com/KwokR/snowflakeRK.git
cd snowflakeRK

# Install dependencies
npm install

# Start development server
npm run dev

# Open browser to http://localhost:3000
```

### Available Scripts
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run export` - Export static site

## Technical Architecture

### Technology Stack
- **Frontend Framework**: Next.js 13.5.6
- **UI Library**: React 18.2.0 with React DOM 18.2.0
- **Data Visualization**: D3.js 7.8.5
- **Type System**: JavaScript (Flow types removed for compatibility)
- **Package Manager**: npm (Yarn compatible)
- **Build System**: Next.js built-in build system
- **Node.js**: Minimum version 18.0.0

### Application Structure
```
snowflakeRK/
├── components/          # React components
├── pages/              # Next.js pages
├── types/              # Flow type definitions
├── constants.js        # Core data models and configurations
├── package.json        # Dependencies and scripts
└── next.config.js      # Next.js configuration
```

## Core Features

### 1. Interactive Career Assessment
- **Nightingale Chart**: Circular radar chart visualization showing skill levels across all tracks
- **Track Selection**: Navigate between 16 different engineering skill tracks
- **Milestone Selection**: Set skill levels from 0-5 for each track
- **Real-time Updates**: Immediate visual feedback when changing skill levels

### 2. Skill Tracking System
The application tracks 16 distinct engineering tracks organized into 3 categories:

#### Category A - Technical Skills
- Mobile Development (iOS/Android)
- Web Client Development (HTML/CSS/JavaScript)
- Foundations (Infrastructure, ML, Databases)
- Server Development (Backend services)

#### Category B - Execution Skills
- Project Management
- Communication
- Craft (Code quality and best practices)
- Initiative

#### Category C - Supporting Skills
- Career Development
- Organizational Design
- Wellbeing
- Accomplishment
- Mentorship
- Evangelism
- Recruiting
- Community Building

### 3. Level Progression System
- **Milestone Levels**: 0-5 scale for each track
- **Point System**: Exponential point allocation (0, 1, 3, 6, 12, 20 points)
- **Career Levels**: Automatic calculation from 1.1 to 5.3 based on total points
- **Title Suggestions**: Dynamic title recommendations based on skill distribution

### 4. User Interface Components

#### Core Components
- **SnowflakeApp**: Main application container and state management
- **NightingaleChart**: Interactive circular visualization
- **Track**: Detailed view of individual skill tracks
- **TrackSelector**: Navigation between different tracks
- **TitleSelector**: Career title selection interface
- **LevelThermometer**: Visual progress indicator
- **PointSummaries**: Numerical breakdown of points and levels

#### Supporting Components
- **KeyboardListener**: Keyboard navigation support
- **Wordmark**: Medium branding component
- **DeprecationNotice**: Warning about tool status

### 5. Data Persistence
- **URL Hash State**: Application state encoded in URL hash for sharing
- **Local State Management**: React component state for real-time interactions
- **No Backend Required**: Fully client-side application

## Functional Requirements

### User Interactions
1. **Profile Creation**: Enter name and select appropriate title
2. **Skill Assessment**: Rate proficiency in each of 16 tracks (0-5 scale)
3. **Visual Navigation**: Use circular chart or track selector to navigate
4. **Keyboard Controls**: Arrow keys for navigation, +/- for level adjustment
5. **State Sharing**: Share assessments via URL

### Data Requirements
1. **Track Definitions**: Comprehensive descriptions for each skill area
2. **Milestone Descriptions**: Detailed criteria for each level (0-5)
3. **Example Behaviors**: Specific signals and examples for each milestone
4. **Point Mapping**: Conversion from milestones to points to career levels
5. **Title Eligibility**: Logic for determining appropriate job titles

### Performance Requirements
1. **Real-time Updates**: Immediate visual feedback on interactions
2. **Responsive Design**: Works on desktop browsers
3. **Fast Loading**: Minimal bundle size for quick initial load
4. **Smooth Animations**: D3.js powered transitions

## Technical Requirements

### Browser Compatibility
- Modern browsers supporting ES6+ features
- SVG support for D3.js visualizations
- CSS-in-JS support (styled-jsx)
- React 18 compatible browsers

### Development Environment
- Node.js 18.0.0 or higher
- npm package manager (or Yarn if preferred)
- Development server with hot reloading and Fast Refresh
- Modern JavaScript (ES2020+) support

### Build and Deployment
- Static site generation via `next build && next export`
- Server-side rendering support with `next start`
- Development mode with `next dev`
- No backend server requirements for static deployment
- Deployable to any static hosting service (Vercel, Netlify, GitHub Pages, etc.)

## Data Model

### Core Types (JavaScript Objects)
```javascript
// TrackId: String literals representing 16 different tracks
// 'MOBILE' | 'WEB_CLIENT' | 'FOUNDATIONS' | 'SERVERS' | 
// 'PROJECT_MANAGEMENT' | 'COMMUNICATION' | 'CRAFT' | 'INITIATIVE' |
// 'CAREER_DEVELOPMENT' | 'ORG_DESIGN' | 'WELLBEING' | 'ACCOMPLISHMENT' |
// 'MENTORSHIP' | 'EVANGELISM' | 'RECRUITING' | 'COMMUNITY'

// Milestone: Numbers 0-5 representing skill levels
// MilestoneMap: Object mapping TrackId to Milestone values
```

### Application State
```javascript
// SnowflakeAppState structure:
// {
//   milestoneByTrack: Object, // Maps track IDs to milestone levels (0-5)
//   name: String,             // User's name
//   title: String,            // Selected job title
//   focusedTrackId: String    // Currently selected track
// }
```

## User Experience Requirements

### Usability
1. **Intuitive Navigation**: Clear visual hierarchy and navigation patterns
2. **Progressive Disclosure**: Detailed information available on demand
3. **Visual Feedback**: Clear indication of current selections and progress
4. **Accessibility**: Keyboard navigation support

### Visual Design
1. **Color Coding**: Category-based color scheme for track organization
2. **Responsive Layout**: Flexible layout adapting to content
3. **Clean Typography**: Readable fonts and appropriate sizing
4. **Professional Appearance**: Suitable for workplace use

## Recent Modernization Changes

### Technology Updates (2024)
1. **React Upgrade**: Updated from React 16.10.2 to React 18.2.0
2. **Next.js Upgrade**: Updated from Next.js 9.0.7 to Next.js 13.5.6
3. **D3.js Upgrade**: Updated from D3.js 4.11.0 to D3.js 7.8.5
4. **Flow Removal**: Removed Flow type annotations for better compatibility
5. **Node.js Requirement**: Now requires Node.js 18.0.0 or higher
6. **Build Scripts**: Updated build and development scripts

### Compatibility Improvements
1. **Modern JavaScript**: Uses current JavaScript standards
2. **Fast Refresh**: Improved development experience with Next.js 13
3. **Better Performance**: Leverages React 18 concurrent features
4. **Enhanced D3**: Uses latest D3.js with improved APIs

## Constraints and Limitations

### Technical Constraints
1. **Client-Side Only**: No backend database or user authentication
2. **Browser Dependency**: Requires modern browser with JavaScript enabled
3. **Static Data**: Track definitions and criteria are hardcoded
4. **No Persistence**: Data only persists in URL hash
5. **Node.js Version**: Requires Node.js 18.0.0 or higher for development

### Business Constraints
1. **Deprecated Tool**: Medium no longer actively uses this framework
2. **Open Source**: Available for community use and modification
3. **No Support**: No official maintenance or support from Medium
4. **Security Vulnerabilities**: Legacy dependencies may have known vulnerabilities

## Success Criteria

### Functional Success
1. **Complete Assessment**: Users can evaluate all 16 tracks
2. **Visual Clarity**: Progress and gaps clearly visible in chart
3. **State Persistence**: Assessments can be saved and shared via URL
4. **Accurate Calculations**: Correct point totals and level assignments

### Technical Success
1. **Performance**: Fast loading and responsive interactions
2. **Reliability**: Consistent behavior across supported browsers
3. **Maintainability**: Clean, well-documented code structure
4. **Extensibility**: Easy to modify tracks or add new features

## Future Considerations

### Potential Enhancements
1. **Backend Integration**: User accounts and data persistence
2. **Team Features**: Compare multiple team members
3. **Progress Tracking**: Historical progression over time
4. **Custom Frameworks**: Support for different career frameworks
5. **Export Features**: PDF reports or data export capabilities
6. **Mobile Optimization**: Touch-friendly mobile interface

### Technical Improvements
1. **Modern React Patterns**: Migrate to React Hooks and functional components
2. **TypeScript**: Add TypeScript for better type safety (replacing removed Flow)
3. **Accessibility**: Enhanced screen reader and keyboard support
4. **Performance**: Code splitting and optimization with Next.js 13 features
5. **Testing**: Comprehensive test suite implementation
6. **Security**: Update dependencies to resolve security vulnerabilities
7. **Component Library**: Modernize to use contemporary React patterns