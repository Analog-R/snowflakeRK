# SnowflakeRK - Engineering Growth Framework Tool

## Project Overview

SnowflakeRK is a web-based interactive tool for visualizing and tracking engineering career progression based on Medium's engineering growth framework. The application provides a comprehensive system for evaluating engineers across multiple skill tracks and career levels.

## Technical Architecture

### Technology Stack
- **Frontend Framework**: Next.js 9.0.7
- **UI Library**: React 16.10.2
- **Data Visualization**: D3.js 4.11.0
- **Type System**: Flow (Facebook's static type checker)
- **Package Manager**: Yarn
- **Build System**: Next.js built-in build system

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

### Development Environment
- Node.js environment for Next.js
- Yarn package manager
- Flow type checker for static analysis
- Development server with hot reloading

### Build and Deployment
- Static site generation via `next export`
- No server-side requirements
- Deployable to any static hosting service

## Data Model

### Core Types
```javascript
type TrackId = 'MOBILE' | 'WEB_CLIENT' | 'FOUNDATIONS' | ... // 16 tracks
type Milestone = 0 | 1 | 2 | 3 | 4 | 5
type MilestoneMap = { [TrackId]: Milestone }
```

### Application State
```javascript
type SnowflakeAppState = {
  milestoneByTrack: MilestoneMap,
  name: string,
  title: string,
  focusedTrackId: TrackId
}
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

## Constraints and Limitations

### Technical Constraints
1. **Client-Side Only**: No backend database or user authentication
2. **Browser Dependency**: Requires modern browser with JavaScript enabled
3. **Static Data**: Track definitions and criteria are hardcoded
4. **No Persistence**: Data only persists in URL hash

### Business Constraints
1. **Deprecated Tool**: Medium no longer actively uses this framework
2. **Open Source**: Available for community use and modification
3. **No Support**: No official maintenance or support from Medium

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
1. **Modern React**: Upgrade to React Hooks and modern patterns
2. **TypeScript**: Migration from Flow to TypeScript
3. **Accessibility**: Enhanced screen reader and keyboard support
4. **Performance**: Code splitting and optimization
5. **Testing**: Comprehensive test suite implementation