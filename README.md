# Flutter-Topics

========================================

🔹 Flutter & Dart Fundamentals
1. Rendering process
Widget → Element → Render tree. Diffing updates only affected elements → efficient.
2. Stateful vs Stateless
Stateless = immutable UI. Stateful = dynamic, lifecycle (initState, dispose).
3. Keys
Preserve widget state. ValueKey (list id), GlobalKey (rare, access across tree).
4. Cross-platform consistency
Skia engine → same UI across platforms. Plugins differ.
5. Dart async/await vs JS promises
Dart: Future (single async result), isolate-based concurrency. JS: Promises.
🔹 State Management
6. Why GetX/BLoC
BLoC = scalable, testable. GetX = simple, reactive.
7. BLoC flow
Event → mapEventToState → State → UI rebuilds.
8. .obs in GetX
Reactive container → auto rebuild on value change.
9. Debug state transitions
Logs, BlocObserver, DevTools.
10. When to avoid
Use setState for very simple UIs.
🔹 API & Backend Integration
11. REST retries
Dio/retry package. Use exponential backoff.
12. Secure tokens
Use flutter_secure_storage. Never SharedPrefs.
13. Firebase Auth/Firestore
Realtime updates with snapshots. Use indexes for queries.
14. Payment gateway scenario
Q: How do you secure payments in a mobile app?
A: Use SDKs or backend-validated APIs. Always validate on backend. Handle failures gracefully.
15. API 200 but null
Check backend logs, serialization, Postman.
🔹 Advanced Features
16. Maps
google_maps_flutter/Mapbox. Secure keys. Custom markers possible.
17. WebRTC/Agora scenario
Q: If you need to build a video chat feature, what’s the approach?
A: WebRTC = peer-to-peer with signaling. Agora = SDK that handles signaling + media.
18. WebSocket vs REST
WebSocket = full-duplex, realtime. REST = stateless request/response.
19. Real-time performance
Streams, pagination, isolates, avoid full rebuilds.
20. Offline sync
SQLite/Hive → sync when online → conflict rules.
🔹 UI/UX & Performance
21. Responsive design
Use LayoutBuilder, MediaQuery, responsive frameworks.
22. const widgets
Compile-time constants → prevent rebuild.
23. Profiling
DevTools: timeline, memory, repaint rainbow.
24. Animations
Implicit (simple) vs Explicit (AnimationController, more control).
25. Reduce app size
--split-per-abi, remove assets, R8/ProGuard.
🔹 Scenario-Based Experience
26. Migrating old Flutter project
Q: How would you handle migrating a large Flutter app to the latest version?
A: Upgrade dependencies, fix deprecated APIs, test gradually with feature flags.
27. Live streaming app
Q: How do you handle real-time video + chat under unstable networks?
A: Use sockets/WebRTC with retry logic, buffering, fallback quality.
28. Booking system app
Q: How do you prevent double-booking in a slot-based system?
A: Backend validation + transaction locks, push notifications for updates.
29. Backward compatibility
Q: How do you ensure backward compatibility when upgrading Flutter/Dart?
A: Use feature flags, conditional imports, handle deprecated APIs carefully.
30. Proud feature scenario
Q: Tell me about a technically challenging feature you built.
A: Example: real-time video calls with Agora/WebRTC with offline handling.
🔹 Problem-Solving
31. Offline-first
Local DB + background sync.
32. Android works, iOS fails
Check iOS entitlements/permissions, Xcode logs.
33. Localization
intl + ARB/JSON files.
34. Crash handling
Firebase Crashlytics, runZonedGuarded.
35. DB migration
Use version numbers + upgrade scripts.
🔹 Retry Function (Dart)
36. Retry function purpose
Retries async action until success/maxRetries. Supports delay, shouldRetry, onError.
37. Retry block
Even on success, retry if result invalid (shouldRetry=true).
🔹 StreamedResponse
38. Null check in http.StreamedResponse
await response.stream.bytesToString(). Check .isEmpty or "null".
🔹 Resume Summary Hooks
39. Cross-platform test
Skia ensures UI consistency.
40. Performance tips
const, lazy loading, isolates, caching, DevTools.
41. Why BLoC
Predictable event→state, testable.
42. Responsive UI
MediaQuery, LayoutBuilder, frameworks.
43. Clean Architecture
Presentation (UI/Bloc) → Domain (Entities, UseCases) → Data (Repo, APIs).
🔹 BLoC vs GetX
44. Difference
GetX = reactive, simple. BLoC = event-driven, scalable.
45. Counter example
GetX: count++. BLoC: IncrementEvent → emits state.
46. Testing
BLoC easier to test → bloc_test with event/state.
🔹 Chat App (Scenario)
47. Best state mgmt
BLoC (event-driven chat).
48. One screen = one bloc?
No, one feature/domain per bloc.
49. Clean Arch with Chat
Domain: Entities/UseCases → Data: Firebase → Presentation: Blocs/UI.
🔹 Lazy Loading & Profiling
50. Widget-level lazy loading
ListView.builder, PageView.builder, IndexedStack.
51. Functional lazy loading
Load on demand (pagination, FutureBuilder).
52. Profiling
DevTools: jank, memory leaks, repaint rainbow.
🔹 Environments (Dev/QA/Prod)
53. Setup environments
Use flavors + multiple main_x.dart.
54. CI/CD environments
Branch → flavor mapping in App Center, GitHub Actions, Azure DevOps.
🔹 Dependencies
55. dependencies vs dev_dependencies
dependencies = runtime. dev_dependencies = test/build only.
56. dependency_overrides
Force specific package version (conflict resolution/testing).
57. Red flag
Don’t keep overrides long-term in production.
🔹 Networking & APIs
58. REST layers
Data (API), Domain (logic), Presentation (UI).
59. JSON serialization
Manual vs code-gen. Use json_serializable.
60. Retry function
Retries async action with delay, shouldRetry, onError.
61. Retry block
Retry on invalid results too (e.g., empty API response).
62. StreamedResponse check
await stream.bytesToString(), check empty/null.
