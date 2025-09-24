# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.3.0] - 2025-09-24

### Added
- Real-time memory metrics integration with Spring Boot Actuator endpoints
- Dynamic trending indicators with historical tracking and up/down arrows
- Countdown timer showing "Next refresh in... Xs" for auto-refresh functionality
- Memory difference calculations showing actual MB changes between refreshes
- Start value references for trending comparisons across all memory sections
- Progress bars and usage indicators for memory visualization
- Automatic memory metrics refresh when switching to memory tab
- Enhanced error handling and graceful degradation for missing metrics

### Changed
- Connect button text changes to "🔄 Refresh Now" after successful connection
- Status display integrated into configuration panel layout using flexbox
- Trending calculations now reference starting values instead of previous values
- Memory metrics display actual differences (e.g., "4.0 MB ▲", "8.0 MB ▼")
- Heap area notifications moved into dedicated Heap Area panel section
- Default refresh interval updated from 5 to 10 seconds
- Improved countdown reset functionality for manual refreshes and interval changes

### Fixed
- Trending marks now show actual memory differences instead of total current values
- Resolved "cron function" timing conflicts and duplicate interval creation
- Fixed byte-to-MB conversion bugs in trending calculations
- Added proper unchanged state styling for zero-difference displays
- Eliminated race conditions between auto-refresh and countdown timers

### Improved
- UI responsiveness with better flexbox layout and spacing
- Visual hierarchy with status messages positioned next to Connect button
- Memory monitoring accuracy with live data instead of static values
- User experience with integrated refresh functionality and visual feedback
- Dashboard layout optimization for better space utilization

## [1.2.0] - 2025-09-24

### Added
- Added UI/UX elements for aggregated, heap and non-heap memory metrics
- Added progress bars showing memory utilization with color-coded status indicators
- Tabular number formatting for improved metric readability
- Contextual tooltips for technical terms (OutOfMemoryError explanations)
- Section-specific educational notes with color-coded backgrounds
- Smooth hover effects and transitions for better user experience
- Enhanced historical values with improved visual feedback

### Changed
- Improved spacing and visual hierarchy across dashboard sections
- Enhanced notification hover animations with subtle translateX effects
- Updated dashboard UI with better visual breathing room
- Refined memory section layouts for better information organization

### Improved
- Overall user experience with smoother interactions
- Educational value through contextual explanations for each memory section
- Visual consistency with better color coding and transitions
- Accessibility with descriptive tooltips for technical concepts

## [1.1.0] - 2025-09-23

### Added
- New "All Metrics" section with separate tabs for Memory and CPU metrics
- Coming Soon placeholders for detailed metric views
- Enhanced documentation for semantic versioning
- Contribution guidelines with standardized formats

### Changed
- Moved refresh controls above the URL configuration area
- Reorganized UI elements for better user experience
- Updated documentation to follow SEMVER
- Enhanced contribution workflow documentation

### Improved
- Controls accessibility and visibility
- Documentation structure and consistency
- Version tracking across all files
- Code organization and readability

## [1.0.0] - 2025-01-16

### Added
- Initial release with core monitoring features
- Real-time JVM memory monitoring
- CPU and GC metrics tracking
- Educational tooltips and documentation
- Responsive design implementation
- Zero-dependency architecture

### Features
- Memory metrics (heap/non-heap)
- CPU usage tracking
- Thread monitoring
- GC statistics
- Auto-refresh functionality
- Progress bar visualizations

[1.3.0]: https://github.com/fhgomes/lightweight-spring-actuator-monitor/releases/tag/v1.3.0
[1.2.0]: https://github.com/fhgomes/lightweight-spring-actuator-monitor/releases/tag/v1.2.0
[1.1.0]: https://github.com/fhgomes/lightweight-spring-actuator-monitor/releases/tag/v1.1.0
[1.0.0]: https://github.com/fhgomes/lightweight-spring-actuator-monitor/releases/tag/v1.0.0
