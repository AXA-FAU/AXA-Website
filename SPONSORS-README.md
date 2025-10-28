# Sponsor Carousel Management

## Overview
The sponsor carousel is now managed through a JSON configuration file (`sponsors.json`) instead of hardcoded values. This gives you complete control over which sponsors are displayed.

## How to Manage Sponsors

### Adding a New Sponsor
1. **Add the image file** to the `media/sponsors/` directory
2. **Edit `sponsors.json`** and add a new entry to the `sponsors` array:

```json
{
  "filename": "new-sponsor.png",
  "alt": "New Sponsor Name",
  "enabled": true
}
```

3. **Refresh the page** - the new sponsor will appear automatically!

### Removing a Sponsor
1. **Edit `sponsors.json`** and either:
   - Set `"enabled": false` to temporarily hide it, OR
   - Remove the entire entry from the array
2. **Refresh the page** - the sponsor will disappear!

### Temporarily Disabling a Sponsor
Set `"enabled": false` in the JSON file:

```json
{
  "filename": "sponsor.png",
  "alt": "Sponsor Name",
  "enabled": false
}
```

## JSON Configuration Structure

```json
{
  "sponsors": [
    {
      "filename": "sponsor-image.png",
      "alt": "Sponsor Display Name",
      "enabled": true
    }
  ],
  "settings": {
    "autoRefresh": true,
    "showConsoleLogs": true,
    "fallbackMessage": "No sponsor images found"
  }
}
```

### Sponsor Properties
- **`filename`**: The image filename in `media/sponsors/` (required)
- **`alt`**: Alternative text for accessibility (required)
- **`enabled`**: Whether to display this sponsor (optional, defaults to true)

### Settings Properties
- **`autoRefresh`**: Whether to automatically refresh on page load (optional, defaults to true)
- **`showConsoleLogs`**: Whether to show debug logs in browser console (optional, defaults to true)
- **`fallbackMessage`**: Message shown when no sponsors are found (optional)

## Developer Tools

You can use these functions in the browser console:

- `refreshSponsors()` - Reload sponsors from JSON config
- `getSponsorsConfig()` - View current JSON configuration
- `validateSponsorImage('filename.png')` - Check if an image exists

## Example Usage

### Complete sponsors.json Example:
```json
{
  "sponsors": [
    {
      "filename": "exhale.png",
      "alt": "Exhale",
      "enabled": true
    },
    {
      "filename": "fau.png",
      "alt": "FAU",
      "enabled": true
    },
    {
      "filename": "nasa.webp",
      "alt": "NASA",
      "enabled": true
    },
    {
      "filename": "old-sponsor.png",
      "alt": "Old Sponsor",
      "enabled": false
    }
  ],
  "settings": {
    "autoRefresh": true,
    "showConsoleLogs": true,
    "fallbackMessage": "No sponsor images found"
  }
}
```

## Benefits

✅ **No more hardcoded values** - Everything is configurable via JSON  
✅ **Easy to manage** - Just edit the JSON file and refresh  
✅ **Flexible** - Enable/disable sponsors without deleting entries  
✅ **Error handling** - Missing images are automatically skipped  
✅ **Debug friendly** - Console logs show what's happening  
✅ **Accessible** - Proper alt text for all images  

## Troubleshooting

- **Sponsor not appearing?** Check that the filename in JSON matches the actual file
- **Image not loading?** Verify the file exists in `media/sponsors/`
- **Want to see what's happening?** Open browser console to see debug logs
- **Need to refresh?** Call `refreshSponsors()` in the console or reload the page
