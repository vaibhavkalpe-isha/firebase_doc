# Firebase Analytics Implementation

## Overview

The Sadhana Tracker app implements comprehensive Firebase Analytics tracking to provide actionable insights into user behavior, app usage patterns, and feature adoption. This tracking helps improve user consistency, optimize features, and enhance the overall user experience.

## 📊 Analytics Categories

### 1. **App Usage & Engagement**

#### **Daily/Monthly Active Users**
- **Event**: `daily_login`, `weekly_login`, `monthly_login`
- **Purpose**: Track user retention and engagement patterns
- **Data**: Timestamp, user session count
- **Insights**: Identify active vs. inactive users, retention trends

#### **Session Frequency**
- **Event**: `session_frequency`
- **Purpose**: Monitor how often users practice
- **Data**: Number of sessions per day
- **Insights**: Understand user practice patterns and consistency

#### **Screen Duration & Engagement**
- **Events**: `screen_entered`, `screen_exited`, `screen_engagement`
- **Purpose**: Track detailed screen usage patterns and time spent
- **Data**: Screen duration, engagement type, navigation context
- **Insights**: Screen performance, user engagement, navigation patterns

#### **Expo Router Integration**
- **Event**: `screen_view` (enhanced)
- **Purpose**: Track route-based navigation with rich context
- **Data**: Route segments, navigation level, dynamic parameters
- **Insights**: User journey analysis, route popularity, navigation flow

#### **Screen Views**
- **Event**: `screen_view`
- **Purpose**: Track which screens users visit most
- **Data**: Screen name, screen class, timestamp
- **Insights**: Identify most/least popular features

#### **Enhanced Screen Tracking**
- **Events**: `screen_entered`, `screen_exited`, `screen_engagement`
- **Purpose**: Track detailed screen usage patterns
- **Data**: Screen duration, engagement type, navigation context
- **Insights**: Screen performance, user engagement, navigation patterns

#### **Expo Router Integration**
- **Event**: `screen_view` (enhanced)
- **Purpose**: Track route-based navigation with context
- **Data**: Route segments, navigation level, dynamic parameters
- **Insights**: User journey analysis, route popularity, navigation flow

### 2. **Session & Practice Tracking**

#### **Session Lifecycle**
- **Events**: `session_started`, `session_completed`, `session_cancelled`, `session_abandoned`
- **Purpose**: Track complete session journey
- **Data**: Practice type, duration, cycles, abandonment stage
- **Insights**: Session completion rates, abandonment reasons

#### **Practice Selection**
- **Events**: `practice_selected`, `practice_deselected`
- **Purpose**: Monitor practice preferences
- **Data**: Practice name, selection source, reason
- **Insights**: Most/least popular practices, selection patterns

#### **First Session**
- **Event**: `first_session_completed`
- **Purpose**: Track onboarding success
- **Data**: Number of practices, duration
- **Insights**: Onboarding effectiveness, user engagement

### 3. **Streak & Consistency**

#### **Streak Management**
- **Events**: `streak_broken`, `streak_milestone_reached`, `streak_recovery`
- **Purpose**: Monitor user consistency patterns
- **Data**: Streak length, milestone number, recovery time
- **Insights**: When users break streaks, motivation factors

#### **Consistency Patterns**
- **Event**: `consistency_pattern`
- **Purpose**: Analyze user practice patterns
- **Data**: Pattern type, consistency score
- **Insights**: User behavior segmentation, optimization opportunities

### 4. **Feature Usage**

#### **Feature Discovery**
- **Events**: `feature_accessed`, `feature_discovered`, `feature_exploration`
- **Purpose**: Track feature adoption and discovery
- **Data**: Feature name, access source, discovery method
- **Insights**: Feature popularity, discovery patterns

#### **Settings & Preferences**
- **Events**: `settings_changed`, `settings_exploration`
- **Purpose**: Monitor user customization
- **Data**: Setting name, old/new values, settings section
- **Insights**: User preferences, feature usage

### 5. **Notifications & Reminders**

#### **Notification Settings**
- **Events**: `notification_enabled`, `notification_disabled`, `reminder_time_changed`
- **Purpose**: Track notification effectiveness
- **Data**: Enabled/disabled status, reason, time changes
- **Insights**: Notification impact on user engagement

#### **Sound Settings**
- **Events**: `sound_enabled`, `sound_disabled`
- **Purpose**: Monitor audio preferences
- **Data**: Sound setting status
- **Insights**: User experience preferences

### 6. **Onboarding Journey**

#### **Onboarding Flow**
- **Events**: `onboarding_started`, `onboarding_completed`, `onboarding_abandoned`
- **Purpose**: Track user setup process
- **Data**: Steps completed, abandonment point, reason
- **Insights**: Onboarding effectiveness, drop-off points

### 7. **User Experience**

#### **Error Handling**
- **Events**: `error_encountered`, `error_recovery`
- **Purpose**: Monitor app stability and user recovery
- **Data**: Error type, recovery method, context
- **Insights**: App stability, user frustration points

#### **Help & Support**
- **Events**: `help_sought`, `feedback_submitted`, `frustration_point`
- **Purpose**: Track user support needs
- **Data**: Help topic, feedback type, frustration context
- **Insights**: User pain points, support optimization

### 8. **Navigation & Performance**

#### **Navigation Flow**
- **Event**: `navigation_flow`
- **Purpose**: Track user navigation patterns
- **Data**: From/to screens, flow type, navigation context
- **Insights**: User journey optimization

#### **Button Interactions**
- **Event**: `button_click`
- **Purpose**: Track user interactions with buttons
- **Data**: Button name, screen name, button location
- **Insights**: Most popular actions, user interaction patterns

#### **Carousel Interactions**
- **Events**: `carousel_swipe`, `dot_navigation`, `streak_card_view`
- **Purpose**: Track carousel navigation and card interactions
- **Data**: From/to cards, swipe direction, navigation method, view source
- **Insights**: Card popularity, navigation preferences, user engagement patterns

#### **Session List Interactions**
- **Events**: `session_list_toggle`, `session_card_click`
- **Purpose**: Track session list expansion and individual session card clicks
- **Data**: Expand/collapse actions, session count, session details, click context
- **Insights**: Session exploration patterns, user engagement with session history

#### **Performance Monitoring**
- **Events**: `loading_time`, `api_response_time`
- **Purpose**: Monitor app performance
- **Data**: Screen name, loading time, API endpoint
- **Insights**: Performance bottlenecks, optimization opportunities

### 9. **User Profile**

#### **Profile Updates**
- **Event**: `user_profile_updated`
- **Purpose**: Track user profile changes
- **Data**: Fields updated
- **Insights**: User engagement with profile features

## 🔧 Implementation Details

### **Analytics Service**
- **File**: `src/services/firebaseAnalytics.ts`
- **Features**: 60+ tracking methods, error handling, automatic logging
- **Configuration**: Always enabled by default, no environment variable required

### **New Analytics Events Added**
- **`CAROUSEL_SWIPE`** - Track swipe gestures between cards
- **`DOT_NAVIGATION`** - Track dot indicator taps for navigation
- **`STREAK_CARD_VIEW`** - Track when users view streak information
- **`SESSION_LIST_TOGGLE`** - Track session list expansion/collapse
- **`SESSION_CARD_CLICK`** - Track individual session card clicks
- **`SCREEN_ENTERED`** - Track when users enter screens
- **`SCREEN_EXITED`** - Track when users exit screens with duration
- **`SCREEN_ENGAGEMENT`** - Track user interactions on screens
- **`BUTTON_CLICK`** - Track button interactions with context

### **Enhanced Screen Tracking**
- **File**: `src/hooks/useScreenTracking.ts`
- **Features**: Automatic screen duration tracking, Expo Router integration
- **Capabilities**: Screen entry/exit, engagement tracking, button interactions

### **Component Integration**
- **File**: `src/components/ui/VirtualizedSessionList.tsx`
- **Features**: Analytics callback support for session interactions
- **Capabilities**: Session card click tracking, user engagement monitoring

### **React Hook**
- **File**: `src/hooks/useFirebaseAnalytics.ts`
- **Features**: Easy-to-use hook interface, callback optimization
- **Usage**: Import and use in any component

### **Integration Points**
- **Home Screen**: Session tracking, practice selection, completion
- **Settings Screen**: Settings changes, preferences
- **Onboarding**: User setup process
- **All Screens**: Screen views, navigation

## 📈 Key Metrics & Insights

### **User Engagement**
- Daily/Monthly Active Users
- Session frequency patterns
- Screen visit distribution
- Time spent in app

### **Practice Consistency**
- Session completion rates
- Streak patterns and breaks
- Practice selection preferences
- Consistency scores

### **Feature Adoption**
- Feature discovery rates
- Settings usage patterns
- Notification effectiveness
- User customization trends

### **User Experience**
- Error rates and recovery
- Performance metrics
- Support request patterns
- Frustration points

### **Onboarding Success**
- Completion rates
- Drop-off points
- First session success
- Setup time analysis

## 🎯 Actionable Insights

### **For Improving Consistency**
- **Streak Break Patterns**: When users typically break streaks
- **Motivation Triggers**: What keeps users engaged
- **Optimal Times**: Best practice times for different users
- **Recovery Strategies**: How to help users get back on track

### **For Feature Development**
- **High-Demand Features**: Features users want but don't have
- **Underutilized Features**: Features that need better UX
- **Feature Combinations**: How users combine different features
- **Workflow Optimization**: Streamlining common user journeys

### **For User Experience**
- **Friction Points**: Where users get frustrated
- **Performance Issues**: Loading times and API response times
- **Navigation Patterns**: How users move through the app
- **Support Needs**: What help users seek most

### **For Onboarding Optimization**
- **Completion Rates**: How many users complete setup
- **Drop-off Points**: Where users abandon onboarding
- **Success Factors**: What leads to successful onboarding
- **First Session Impact**: How onboarding affects first practice

## 🔒 Privacy & Security

### **Data Protection**
- No personal information in analytics
- Only behavioral and usage patterns
- Secure data transmission
- User consent compliance

### **Data Minimization**
- Essential metrics only
- Aggregated data where possible
- No sensitive practice details
- Respects user preferences

## 📱 Usage Examples

### **Basic Tracking**
```typescript
import { useFirebaseAnalytics } from '@/src/hooks/useFirebaseAnalytics';

const { logScreenView, logSessionCompleted } = useFirebaseAnalytics();

// Track screen view
logScreenView('Home');

// Track session completion
logSessionCompleted('Surya Kriya', 30, 3);
```

### **Enhanced Screen Tracking**
```typescript
import { useScreenTracking } from '@/src/hooks/useScreenTracking';

const { 
  trackScreenEngagement, 
  trackButtonClick, 
  trackNavigation 
} = useScreenTracking();

// Track screen engagement
trackScreenEngagement('scroll', { scroll_depth: '75%' });

// Track button click
trackButtonClick('start_session', 'center_bottom', { 
  available_practices: 5 
});

// Track navigation
trackNavigation('/session-detail/123', 'push', { 
  session_type: 'surya_kriya' 
});
```

### **Carousel & Card Interactions**
```typescript
const { 
  logCarouselSwipe, 
  logDotNavigation, 
  logStreakCardView 
} = useFirebaseAnalytics();

// Track carousel swipe
logCarouselSwipe('today_summary', 'streak_card', 'right');

// Track dot navigation
logDotNavigation('today_summary', 'streak_card');

// Track streak card view
logStreakCardView('carousel_swipe');
```

### **Session List Interactions**
```typescript
const { 
  logSessionListToggle, 
  logSessionCardClick 
} = useFirebaseAnalytics();

// Track session list expansion
logSessionListToggle('expand', 5, { user_context: 'today_summary' });

// Track session card click
logSessionCardClick(3, 'session_123', { 
  practices_count: 4, 
  session_duration: 45 
});
```

### **Advanced Tracking**
```typescript
const { 
  logPracticeSelected, 
  logStreakBroken, 
  logFeatureAccessed 
} = useFirebaseAnalytics();

// Track practice selection
logPracticeSelected('Shambhavi', 'practice_modal');

// Track streak break
logStreakBroken(15, 'missed_day');

// Track feature access
logFeatureAccessed('insights', 'tab_navigation');
```

## 🚀 Benefits

### **Data-Driven Decisions**
- Understand user behavior patterns
- Identify optimization opportunities
- Measure feature effectiveness
- Track improvement over time

### **User Experience Enhancement**
- Reduce friction points
- Optimize performance
- Improve feature discoverability
- Enhance onboarding flow

### **Business Intelligence**
- User retention insights
- Feature adoption metrics
- Performance monitoring
- Support optimization

### **Product Development**
- Feature prioritization
- User journey optimization
- A/B testing support
- Success metric tracking

### **Detailed User Behavior Insights**
- **Carousel swipe patterns** - Navigation preferences and card popularity
- **Session list interactions** - History exploration and detail view preferences
- **Screen duration analysis** - Engagement depth and content effectiveness
- **Button click heatmaps** - Most used features and interaction patterns
- **Navigation flow analysis** - User journey optimization opportunities

## 📊 Dashboard Setup

### **Recommended Firebase Analytics Dashboard**
1. **User Engagement**: Daily/Monthly active users, session frequency
2. **Practice Consistency**: Streak patterns, session completion rates
3. **Feature Usage**: Most used features, discovery patterns
4. **Performance**: Loading times, error rates
5. **Onboarding**: Completion rates, drop-off analysis

### **Key Reports**
- User retention by cohort
- Feature adoption funnel
- Session completion analysis
- Streak break patterns
- Performance trends
- Carousel interaction analysis
- Session list engagement metrics
- Screen duration and engagement patterns
- Button click and interaction heatmaps
- Navigation flow and user journey analysis

This comprehensive analytics implementation provides deep insights into user behavior, enabling data-driven decisions to improve the Sadhana Tracker app and enhance user experience.
