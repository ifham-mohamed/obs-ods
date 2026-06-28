
2025-04-18 15:21

Status:

Tags:


# Technical - API Debounce

### GitHub Copilot

# Fix Search Query Issue in Customer View

The search functionality has a problem where entered characters are sometimes getting cut off in API requests. This happens because the debouncing mechanism is triggering searches too quickly before the user has finished typing.

## Steps to solve this:

1. Increase the debounce timer from 500ms to a more generous value
2. Add minimum character length requirement for search
3. Improve the debouncing implementation for search queries
4. Fix search type parameter handling

### [customer-view.tsx](vscode-file://vscode-app/c:/Users/ifham/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html)

customer-view.tsx+23-5

These changes address the issue by:

1. Increasing the debounce time from 500ms to 1000ms to give users more time to finish typing
2. Fixing the search parameter handling to use the correct parameter name based on search type
3. Adding an onBlur handler to immediately trigger search when the input loses focus
4. Making sure search type changes immediately update the search results
5. Ensuring the actual parameter name sent to the API matches what you need (name or phone)

This should prevent the issue where the API receives incomplete search queries like "070532339" instead of the full "0705323399".


# Reference