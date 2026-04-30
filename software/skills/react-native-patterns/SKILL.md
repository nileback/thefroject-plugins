---
name: react-native-patterns
description: Apply React Native and Expo best practices for component architecture, navigation, platform-specific behavior, gesture handling, and performance.
triggers:
  - react native help
  - expo patterns
  - mobile app development
  - react native best practices
---

# React Native Patterns

## Project Structure
Organize by feature, not file type: `src/features/auth/screens/`, `src/features/auth/components/`, `src/shared/`, `src/navigation/`.

## Component Patterns
- **Screens** receive navigation props, manage data fetching. **Components** are reusable, receive data via props.
- Use `Platform.select` for small platform differences, `.ios.tsx`/`.android.tsx` for large ones.
- Use `FlatList` for dynamic lists (never `ScrollView` + `.map()` for 20+ items). Provide `keyExtractor`, use `getItemLayout` for fixed heights, wrap items in `React.memo`.

## Navigation (React Navigation)
- Type all screens with `RootStackParamList`. Don't pass callbacks as route params.
- Use `useFocusEffect` instead of `useEffect` for screen-focus data fetching.
- Reset navigation stack after auth flows.

## Gestures and Animation
- Use `react-native-gesture-handler` + `react-native-reanimated` for complex gestures on UI thread.
- Never animate layout properties (`width`, `height`) — use `transform` instead.
- Test gestures on real devices, not simulators.

## Performance
- `React.memo` on list items. Stabilize callbacks with `useCallback`. Don't create objects inline in JSX.
- Use `expo-image` over built-in `Image`. Resize server-side.
- Defer non-critical init until after first render. Use dynamic `import()` for screens behind navigation.

## Expo-Specific
- Prefer Expo SDK libraries over community packages. Use `expo-router` for SDK 49+.
- Test with `expo-dev-client`, not Expo Go. Run `npx expo-doctor` for dependency conflicts.

## Testing
- `@testing-library/react-native` for components. Query by accessibility role, not testID.
- E2E with Detox or Maestro on CI.
