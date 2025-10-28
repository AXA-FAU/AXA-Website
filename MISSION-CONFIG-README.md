# Mission Configuration Guide

This guide explains how to edit the mission pages on your website.

## Config Files

Each mission has its own configuration file:
- `mission1-config.json` - Configuration for Mission 1
- `mission2-config.json` - Configuration for Mission 2
- `mission3-config.json` - Configuration for Mission 3

## How to Edit

### 1. Mission Title and Description

```json
"title": "MISSION 1",
"description": "Your mission description goes here..."
```

### 2. Team Members

Each team member needs:
- **name**: Full name of the team member
- **role**: Their role/position
- **photo**: Path to their photo (recommended: store in `media/leadership/`)

```json
"team": [
  {
    "name": "John Doe",
    "role": "Mission Lead",
    "photo": "media/leadership/john-doe.jpg"
  }
]
```

**Tips for team photos:**
- Use square images (e.g., 400x400px)
- Save photos in `media/leadership/` folder
- Use .jpg or .png format
- Keep file sizes reasonable (under 500KB)

### 3. Mission Images

Add paths to mission photos in the images array:

```json
"images": [
  "media/missions/mission1/photo1.jpg",
  "media/missions/mission1/photo2.jpg",
  "media/missions/mission1/photo3.jpg"
]
```

**Tips for mission images:**
- Recommended size: 800x600px or larger
- Store in organized folders like `media/missions/mission1/`
- Images will appear in a grid and can be clicked to expand

### 4. Sponsors

Add sponsor logo paths:

```json
"sponsors": [
  "media/logos/sponsor1.png",
  "media/logos/sponsor2.png"
]
```

**Tips for sponsor logos:**
- Use transparent PNG files when possible
- Logos will be displayed in grayscale and become colored on hover
- Recommended max size: 200x100px

## Folder Structure Recommendation

```
AXAsite/
├── index.html
├── mission1-config.json
├── mission2-config.json
├── mission3-config.json
└── media/
    ├── leadership/           # Team member photos
    │   ├── john-doe.jpg
    │   └── jane-smith.jpg
    ├── missions/            # Mission photos
    │   ├── mission1/
    │   ├── mission2/
    │   └── mission3/
    └── logos/               # Sponsor logos
        ├── fau.png
        └── sponsor2.png
```

## Example: Complete Mission Config

```json
{
  "title": "MISSION 1: Space Plant Research",
  "description": "Our first mission focuses on developing autonomous plant growth systems for long-duration space missions. This research is critical for future Mars colonization efforts.",
  "team": [
    {
      "name": "Dr. Sarah Johnson",
      "role": "Principal Investigator",
      "photo": "media/leadership/sarah-johnson.jpg"
    },
    {
      "name": "Michael Chen",
      "role": "Lead Engineer",
      "photo": "media/leadership/michael-chen.jpg"
    }
  ],
  "images": [
    "media/missions/mission1/lab-setup.jpg",
    "media/missions/mission1/testing.jpg",
    "media/missions/mission1/team-photo.jpg"
  ],
  "sponsors": [
    "media/logos/fau.png",
    "media/logos/nasa.png",
    "media/logos/spacex.png"
  ]
}
```

## Testing Your Changes

1. Save your changes to the config file
2. Refresh your website in the browser
3. Click on the mission block to view your changes
4. If images don't appear, check that the file paths are correct

## Troubleshooting

**Images not showing?**
- Verify the file path is correct (case-sensitive!)
- Make sure the image file exists in the specified location
- Check that the file extension matches (.jpg vs .JPG)

**Config not loading?**
- Ensure your JSON syntax is valid (use a JSON validator)
- Check for missing commas or quotes
- Look at the browser console (F12) for error messages

## Need Help?

If you encounter issues, check the browser's developer console (press F12) for error messages.

