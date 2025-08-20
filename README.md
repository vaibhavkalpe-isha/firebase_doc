# Firebase Analytics Tracking

## Overview

This document outlines what data we collect in the Sadhana Tracker app using Firebase Analytics. We track user behavior and app usage patterns to improve the app experience.

## 📊 What We Track

### App Usage Events

**App Launch**
- Event: `app_launch`
- Values: timestamp, platform (react-native)
- Purpose: Track when users open the app

**Screen Views**
- Event: `screen_view`
- Values: screen_name, screen_class, timestamp
- Purpose: Track which screens users visit most

**Screen Duration**
- Events: `screen_entered`, `screen_exited`
- Values: screen_name, duration_ms, navigation_context
- Purpose: Track time spent on each screen

**Navigation Flow**
- Event: `navigation_flow`
- Values: from_screen, to_screen, navigation_type (push/pop)
- Purpose: Track user journey through the app

### Session & Practice Events

**Session Started**
- Event: `session_started`
- Values: practice_type, duration_minutes
- Purpose: Track when users begin practice sessions

**Session Completed**
- Event: `session_completed`
- Values: practice_type, duration_minutes, cycles_count
- Purpose: Track successful session completions

**Session Cancelled**
- Event: `session_cancelled`
- Values: practice_type, reason
- Purpose: Track when users cancel sessions

**Session Abandoned**
- Event: `session_abandoned`
- Values: practice_type, stage, reason
- Purpose: Track incomplete sessions

**Practice Selection**
- Event: `practice_selected`
- Values: practice_name, source (modal/tab/etc)
- Purpose: Track which practices users choose

**Practice Deselected**
- Event: `practice_deselected`
- Values: practice_name, reason
- Purpose: Track when users remove practices

### Streak & Consistency Events

**Streak Broken**
- Event: `streak_broken`
- Values: streak_length, reason
- Purpose: Track when users break practice streaks

**Streak Milestone**
- Event: `streak_milestone_reached`
- Values: milestone_number, streak_length
- Purpose: Track achievement milestones

**Streak Recovery**
- Event: `streak_recovery`
- Values: recovery_time_days, previous_streak_length
- Purpose: Track when users restart after breaking streaks

**Consistency Pattern**
- Event: `consistency_pattern`
- Values: pattern_type, consistency_score
- Purpose: Track user practice patterns over time

### Feature Usage Events

**Feature Accessed**
- Event: `feature_accessed`
- Values: feature_name, access_source
- Purpose: Track which features users use

**Feature Discovered**
- Event: `feature_discovered`
- Values: feature_name, discovery_method
- Purpose: Track how users find features

**Settings Changed**
- Event: `settings_changed`
- Values: setting_name, old_value, new_value
- Purpose: Track user preferences

**Settings Exploration**
- Event: `settings_exploration`
- Values: settings_section, time_spent_seconds
- Purpose: Track settings usage

### Notification Events

**Notification Enabled/Disabled**
- Events: `notification_enabled`, `notification_disabled`
- Values: notification_type, reason
- Purpose: Track notification preferences

**Reminder Time Changed**
- Event: `reminder_time_changed`
- Values: old_time, new_time, time_format
- Purpose: Track reminder timing preferences

**Sound Settings**
- Events: `sound_enabled`, `sound_disabled`
- Values: sound_type, reason
- Purpose: Track audio preferences

### User Engagement Events

**Daily/Weekly/Monthly Login**
- Events: `daily_login`, `weekly_login`, `monthly_login`
- Values: login_count, user_session_count
- Purpose: Track user retention patterns

**Session Frequency**
- Event: `session_frequency`
- Values: sessions_per_day, practice_types
- Purpose: Track practice frequency

### Onboarding Events

**Onboarding Started**
- Event: `onboarding_started`
- Values: timestamp, user_type
- Purpose: Track onboarding initiation

**Onboarding Completed**
- Event: `onboarding_completed`
- Values: steps_completed, total_time_seconds
- Purpose: Track successful onboarding

**Onboarding Abandoned**
- Event: `onboarding_abandoned`
- Values: step_abandoned, reason, time_spent_seconds
- Purpose: Track onboarding drop-offs

**First Session Completed**
- Event: `first_session_completed`
- Values: practice_count, total_duration_minutes
- Purpose: Track first-time user success

### UI Interaction Events

**Button Click**
- Event: `button_click`
- Values: button_name, screen_name, button_location
- Purpose: Track user interactions

**Carousel Swipe**
- Event: `carousel_swipe`
- Values: carousel_name, from_card, to_card, swipe_direction
- Purpose: Track carousel navigation

**Dot Navigation**
- Event: `dot_navigation`
- Values: carousel_name, target_card, navigation_method
- Purpose: Track carousel dot navigation

**Streak Card View**
- Event: `streak_card_view`
- Values: card_type, view_source, streak_length
- Purpose: Track streak information engagement

**Session List Toggle**
- Event: `session_list_toggle`
- Values: action (expand/collapse), session_count, context
- Purpose: Track session list interactions

**Session Card Click**
- Event: `session_card_click`
- Values: session_id, session_details, click_context
- Purpose: Track session detail views

### Performance Events

**Loading Time**
- Event: `loading_time`
- Values: screen_name, loading_time_ms, loading_type
- Purpose: Track app performance

**API Response Time**
- Event: `api_response_time`
- Values: endpoint, response_time_ms, status_code
- Purpose: Track backend performance

**Sync Events**
- Events: `sync_completed`, `sync_failed`
- Values: sync_type, records_count, error_message
- Purpose: Track data synchronization

### Error & Support Events

**Error Encountered**
- Event: `error_encountered`
- Values: error_type, error_message, screen_name
- Purpose: Track app errors

**Error Recovery**
- Event: `error_recovery`
- Values: recovery_method, recovery_time_seconds
- Purpose: Track error resolution

**Help Sought**
- Event: `help_sought`
- Values: help_topic, help_source
- Purpose: Track support requests

**Feedback Submitted**
- Event: `feedback_submitted`
- Values: feedback_type, feedback_rating
- Purpose: Track user feedback

**Frustration Point**
- Event: `frustration_point`
- Values: frustration_context, user_action
- Purpose: Track user pain points

## 🔒 Privacy & Data Protection

### What We Collect
- ✅ Anonymous usage patterns
- ✅ App performance metrics
- ✅ Feature usage statistics
- ✅ Practice session metadata (duration, type, completion)
- ✅ Navigation patterns
- ✅ Error and performance data

### What We Don't Collect
- ❌ Personal information (name, email, phone)
- ❌ Specific practice details or personal notes
- ❌ Location data
- ❌ Device identifiers
- ❌ Sensitive health information

### Data Security
- All data encrypted in transit
- Stored securely on Firebase servers
- Follows privacy best practices
- Users can request data deletion

## 📈 Key Metrics

### User Engagement
- Daily/Monthly Active Users
- Session frequency patterns
- Screen visit distribution
- Time spent in app

### Practice Consistency
- Session completion rates
- Streak patterns and breaks
- Practice selection preferences
- Consistency scores

### Feature Effectiveness
- Feature adoption rates
- Settings usage patterns
- Notification effectiveness
- Onboarding success rates

### App Performance
- Loading times
- Error rates
- API response times
- Sync success rates

## 🎯 Business Value

### Product Development
- Identify most/least used features
- Understand user workflows
- Optimize feature discovery
- Improve onboarding flow

### User Experience
- Reduce friction points
- Optimize performance
- Enhance feature usability
- Improve retention

### Data-Driven Decisions
- Feature prioritization
- Performance optimization
- User journey improvement
- Success metric tracking

## 📱 User Control

### Analytics Settings
- Users can disable analytics in app settings
- Disabling doesn't affect app functionality
- Can be re-enabled at any time

### Data Access
- Users can request analytics data copy
- Users can request data deletion
- Transparent about data collection

---

**Note**: This analytics data helps us improve the Sadhana Tracker app for all users. We're committed to privacy and only collect data that helps enhance the user experience.
