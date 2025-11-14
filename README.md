# Parameter-Based Routing System

This routing system allows you to redirect between `index.html` (staging) and `live.html` (production) based on URL parameters.

## Files Created

### 1. `router.html`
Main router file that handles parameter-based routing with a loading interface.

### 2. `js-router.html`
Alternative JavaScript-based router with manual selection options.

### 3. `.htaccess`
Apache configuration for URL rewriting (if supported by your server).

### 4. `live.html`
Production environment page (previously empty, now has basic content).

## Usage Examples

### URL Parameters
Use any of these parameter names with the following values:

**Parameter Names:**
- `env`
- `environment` 
- `mode`
- `stage`

**Values for Staging (→ index.html):**
- `staging`
- `development`
- `dev`
- `stage`

**Values for Live (→ live.html):**
- `live`
- `production`
- `prod`

### Example URLs

```
# Route to staging (index.html)
https://yoursite.com/router.html?env=staging
https://yoursite.com/router.html?environment=development
https://yoursite.com/router.html?mode=dev

# Route to live (live.html)
https://yoursite.com/router.html?env=live
https://yoursite.com/router.html?environment=production
https://yoursite.com/router.html?stage=prod
```

### Clean URLs (with .htaccess)
If your server supports .htaccess, you can use:

```
https://yoursite.com/?env=staging
https://yoursite.com/staging
https://yoursite.com/live
```

## Implementation Options

### Option 1: Use router.html as entry point
Set `router.html` as your main landing page and pass parameters.

### Option 2: Use js-router.html for manual selection
Provides a user interface for environment selection plus auto-routing.

### Option 3: Direct parameter routing
Modify your existing pages to include the routing logic.

## Server Requirements

- **Basic Setup:** Any web server (works with router.html)
- **Clean URLs:** Apache server with mod_rewrite enabled (for .htaccess)
- **Alternative:** Any server supporting URL rewriting

## Customization

You can easily modify the routing logic in the JavaScript files to:
- Add more environments
- Change parameter names
- Modify redirect logic
- Add custom validation

## Testing

1. Open `router.html?env=staging` - should redirect to index.html
2. Open `router.html?env=live` - should redirect to live.html
3. Open `js-router.html` - provides manual interface and examples
4. Test clean URLs if .htaccess is supported

## Default Behavior

If no valid parameter is provided, the system defaults to staging (index.html).