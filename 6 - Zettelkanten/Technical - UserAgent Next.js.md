
2025-04-18 15:20

Status:

Tags:


# Technical - UserAgent Next.js

### GitHub Copilot

# Implement Mobile Device Access Restriction for Back Office

I'll add logic to prevent mobile device users from accessing the back office section, and redirect them to a mobile-not-supported page.

## Step 1: Update App Selector Content to Conditionally Display Options

### [app-selector-content.tsx](vscode-file://vscode-app/c:/Users/ifham/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html)

app-selector-content.tsx+37-13

## Step 2: Create a middleware file to handle route protection

### [middleware.ts](vscode-file://vscode-app/c:/Users/ifham/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html)

middleware.ts+30-2

## Step 3: Create a "Mobile Not Supported" page

### [page.tsx](vscode-file://vscode-app/c:/Users/ifham/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html)

page.tsx

## Explanation

This implementation creates a comprehensive solution for restricting mobile access to the back-office section:

1. **App Selector Modifications**:
    
    - Added a `mobileSupported` flag to each app option
    - Added client-side mobile detection using user agent and screen size
    - Visually disabled back-office option on mobile devices with a warning message
    - Added logic to redirect to a dedicated error page if mobile users try to access restricted areas
2. **Middleware Protection**:
    
    - Created a server-side middleware that intercepts requests to protected routes
    - Uses the Next.js userAgent utility to detect mobile devices
    - Redirects mobile users attempting to access restricted routes to a dedicated error page
    - Configuration ensures it only runs on necessary routes to minimize performance impact
3. **Mobile Not Supported Page**:
    
    - Created a dedicated, user-friendly page explaining the limitation
    - Provides a clear way to return to the app selector
    - Maintains the app's design language and branding

This approach provides multiple layers of protection: visual cues in the UI, client-side prevention, and server-side enforcement through middleware.

# Improve Mobile Detection to Block "Request Desktop Site" Mode

I'll enhance the mobile detection to prevent mobile users from accessing restricted areas even when they've enabled "Desktop site" mode in their browser settings.

## Step 1: Create a middleware.ts file to properly detect mobile devices

middleware.ts+41-18

## Step 2: Update the Mobile Not Supported page to include client-side detection script

page.tsx+56-2

## Step 3: Update App Selector to include enhanced mobile detection

app-selector-content.tsx+32-17

## Explanation

This implementation provides robust detection of mobile devices, even when "Request desktop site" is enabled:

1. **Middleware Enhancement**:
    
    - Added multiple checks to detect mobile devices beyond just user agent
    - Added support for a custom header/cookie that client-side detection can set
    - Implemented additional UA pattern checking that may reveal mobile fingerprints
2. **Client-Side Detection Enhancement**:
    
    - Added sophisticated checks that detect mobile properties like:
        - Touch capabilities with multiple touch points
        - Screen dimension ratios typical of mobile devices
        - Device pixel ratio (typically higher on mobile)
        - Mobile-specific browser features like 'orientation'
    - Sets a cookie that the middleware can read on subsequent requests
3. **Desktop Mode Warning**:
    
    - Added specific detection for "desktop site" mode on mobile
    - Shows additional warning when this state is detected
    - Explains why this won't provide a good experience

This implementation creates a robust defense against mobile users trying to access the back office, even when they've enabled desktop site mode in their browser.



# Reference