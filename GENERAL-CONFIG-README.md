# General Website Configuration

## Overview
The website now uses a comprehensive JSON configuration system (`general.json`) to manage all text content, site settings, and favicon. This allows you to easily customize the entire website without editing HTML code.

## Configuration Files

### `general.json` - Main Configuration
Controls all text content, site settings, and favicon.

### `sponsors.json` - Sponsor Management
Controls which sponsor images are displayed in the carousel.

## How to Use

### Changing Text Content
1. **Edit `general.json`** with your desired text
2. **Refresh the page** - changes apply immediately!

### Changing the Favicon
1. **Add your favicon image** to the `media/logos/` directory
2. **Update `general.json`**:
   ```json
   {
     "site": {
       "favicon": "media/logos/your-favicon.png"
     }
   }
   ```
3. **Refresh the page**

## Configuration Structure

### Site Settings
```json
{
  "site": {
    "title": "Your Website Title",
    "favicon": "media/logos/your-favicon.png",
    "description": "Your website description"
  }
}
```

### Navigation
```json
{
  "navigation": {
    "home": "Home",
    "about": "About", 
    "missions": "Missions",
    "join": "Join",
    "support": "Support",
    "contact": "Contact"
  }
}
```

### Hero Section
```json
{
  "hero": {
    "title": "Your Main Headline",
    "description": "Your main description text"
  }
}
```

### About Section
```json
{
  "about": {
    "title": "About",
    "content": "Your about section content"
  }
}
```

### Missions
```json
{
  "missions": {
    "mission1": {
      "title": "MISSION 1",
      "subtitle": "2024 - Your Mission"
    },
    "mission2": {
      "title": "MISSION 2", 
      "subtitle": "2024 - Another Mission"
    },
    "mission3": {
      "title": "MISSION 3",
      "subtitle": "2024 - Third Mission"
    },
    "cta": "CLICK TO READ MORE",
    "mobileCta": "Click to learn more"
  }
}
```

### Contact Form
```json
{
  "contact": {
    "title": "Contact Us",
    "subtitle": "Reach out and we'll get back to you as soon as possible.",
    "form": {
      "name": {
        "label": "Name",
        "placeholder": "Your full name"
      },
      "email": {
        "label": "Email",
        "placeholder": "you@example.com"
      },
      "phone": {
        "label": "Phone Number", 
        "placeholder": "(555) 867-5309"
      },
      "reason": {
        "label": "Reason for Contact",
        "placeholder": "Select a reason",
        "options": [
          "General Inquiry",
          "Sponsorship",
          "Partnership", 
          "Join the Team",
          "Media"
        ]
      },
      "message": {
        "label": "Message",
        "placeholder": "Type your message..."
      },
      "submit": "Send"
    }
  }
}
```

### Footer
```json
{
  "footer": {
    "contact": {
      "title": "Contact Us",
      "email": "your-email@example.com",
      "phone": "1800 123 4567"
    },
    "address": {
      "title": "Address",
      "content": "Your Address<br>City, State ZIP"
    },
    "socials": {
      "title": "Socials"
    },
    "bottom": {
      "copyright": "© 2025 Your Company. All rights reserved.",
      "designedBy": "Designed by",
      "designerName": "Your Name",
      "designerUrl": "https://yourwebsite.com/"
    }
  }
}
```

### Settings
```json
{
  "settings": {
    "showConsoleLogs": true,
    "autoRefresh": true
  }
}
```

## Developer Tools

Available in browser console:

- `loadGeneralConfig()` - Reload general configuration
- `refreshSponsors()` - Reload sponsor configuration
- `getSponsorsConfig()` - View current sponsor config

## Benefits

✅ **Complete Control** - All text content is configurable via JSON  
✅ **Easy Updates** - Change text without touching HTML  
✅ **Favicon Management** - Easy favicon switching  
✅ **Consistent Structure** - Organized configuration system  
✅ **Error Handling** - Graceful fallbacks for missing content  
✅ **Debug Friendly** - Console logs show what's happening  

## Example: Changing the Site Title and Favicon

1. **Add your favicon** to `media/logos/my-favicon.png`
2. **Edit `general.json`**:
   ```json
   {
     "site": {
       "title": "My Awesome Space Company",
       "favicon": "media/logos/my-favicon.png"
     }
   }
   ```
3. **Refresh the page** - title and favicon update instantly!

## Troubleshooting

- **Changes not appearing?** Make sure to refresh the page after editing JSON
- **Favicon not updating?** Check that the image file exists in the specified path
- **Want to see what's happening?** Open browser console to see debug logs
- **Need to reload config?** Call `loadGeneralConfig()` in the console

## File Structure

```
your-website/
├── general.json          # Main configuration
├── sponsors.json         # Sponsor management  
├── index.html           # Main website file
├── media/
│   └── logos/
│       ├── axa2.png     # Current favicon
│       └── your-favicon.png  # Your custom favicon
└── README files...
```

The system is now completely configurable through JSON files - no more hardcoded text or manual HTML editing required!
