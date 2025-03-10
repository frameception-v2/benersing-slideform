```markdown
# Typeform Survey Frame v2 Specification

## 1. OVERVIEW

### Core Functionality
- Embedded multi-step survey experience within Farcaster feed
- Dynamic question progression with native frame navigation
- Full HTML/CSS interactive elements per question type (text input, multiple choice, ratings)
- Local persistence of survey responses using device storage
- Final submission through Ethereum wallet signature
- Progress indicator and navigation controls

### UX Flow
1. Frame initializes with welcome screen + start button
2. Sequential display of survey questions as individual "slides"
3. Per-question interactive elements:
   - Text input fields
   - Touch-friendly selection cards
   - Slider controls
4. Mobile-optimized navigation:
   - Swipe gestures (left/right)
   - Floating action buttons
5. Final confirmation screen with response summary
6. Wallet signature request for submission
7. Success state with shareable results

## 2. TECHNICAL REQUIREMENTS

### Responsive Design
- CSS Grid-based layout system
- Viewport-relative units (vw/vh) for sizing
- Media queries for mobile breakpoints (320px-768px)
- Touch target sizing (minimum 48px interactive elements)
- Dynamic font scaling with clamp()

### Data Handling
- LocalStorage for session persistence
- Frame state serialization/deserialization
- Wallet-connected identity verification
- Response compression for on-chain storage

## 3. FRAMES v2 IMPLEMENTATION

### Interactive Elements
- Custom form controls using HTML5 input types
- SVG-based progress indicators
- Animated transitions between questions
- Client-side validation with error states

### Input Handling
- Pointer events abstraction (touch/mouse)
- Gesture detection library (Hammer.js)
- Debounced text input handling
- Focus management between questions

### Storage/Sharing
- Frame SDK for context persistence
- Response encryption before localStorage
- Share-to-feed capability via SDK actions
- Transactional state updates

## 4. MOBILE CONSIDERATIONS

### Responsive Techniques
- Vertical stacking for small viewports
- Horizontal overflow containment
- Position: sticky navigation controls
- CSS transforms for off-canvas elements

### Touch Patterns
- Swipe direction detection (next/previous)
- Long-press for tooltips
- Virtual keyboard management
- Hover state fallbacks for mobile

## 5. CONSTRAINTS COMPLIANCE

### Storage Strategy
- Device-local persistence only
- Session-based data lifecycle
- No cross-device sync requirements

### Architecture Limits
- Zero external database dependencies
- No smart contract interactions
- Pure client-side rendering
- Minimal third-party libs (only Hammer.js)

### Development Scope
- Prototype-grade error handling
- Basic input validation only
- No internationalization
- Limited browser support matrix
- Performance budget: <100KB initial load
```