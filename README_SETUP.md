# Disaster Procedures Dashboard

A professional, minimal emergency response management system with smooth animations and intuitive tab-based navigation.

## Features

✅ **Three Disaster Categories**: Tsunami, Fires, and Earthquakes with emoji indicators
✅ **Smooth Tab Navigation**: Professional transitions between disaster types
✅ **Procedure Management**: Add, edit, and delete procedures for each disaster
✅ **JSON Configuration**: `settings.json` stores all disaster data and theme settings
✅ **Responsive Design**: Works seamlessly on desktop, tablet, and mobile
✅ **Professional Styling**: Clean blue color scheme with smooth animations
✅ **Image Support**: Each disaster can display a featured image

## Project Structure

```
disaster-dashboard/
├── settings.json                    # Configuration file with disaster data
├── client/
│   ├── public/
│   │   └── assets/
│   │       └── images/             # Place your disaster images here
│   │           ├── tsunami.jpg
│   │           ├── fires.jpg
│   │           └── earthquakes.jpg
│   ├── src/
│   │   ├── pages/
│   │   │   └── Home.tsx           # Main dashboard component
│   │   ├── App.tsx                # Application root
│   │   └── index.css              # Global styles and theme
│   └── index.html
└── package.json
```

## Getting Started

### 1. Add Your Images

Place your disaster images in the `client/public/assets/images/` folder:

- `tsunami.jpg` - Tsunami emergency image
- `fires.jpg` - Fire emergency image
- `earthquakes.jpg` - Earthquake emergency image

The dashboard will automatically display these images in the disaster cards.

### 2. Customize Settings

Edit `settings.json` to modify:

```json
{
  "disasters": [
    {
      "id": "tsunami",
      "name": "Tsunami",
      "description": "Your custom description here",
      "image": "/assets/images/tsunami.jpg",
      "procedures": [],
      "animationDelay": 0
    }
    // ... more disasters
  ],
  "theme": {
    "primaryColor": "#1e40af",
    "secondaryColor": "#64748b",
    "accentColor": "#0ea5e9",
    "backgroundColor": "#ffffff",
    "textColor": "#0f172a"
  }
}
```

### 3. Using the Dashboard

#### Adding Procedures

1. Click on a disaster tab (Tsunami, Fires, or Earthquakes)
2. Click the **"Add Procedure"** button
3. Enter the procedure name and detailed description
4. Click **"Save Procedure"**

#### Editing Procedures

1. Click the **edit icon** (pencil) on any procedure
2. Modify the name and description
3. Click **"Save"** to confirm

#### Deleting Procedures

1. Click the **delete icon** (trash) on any procedure
2. The procedure will be removed immediately

## Design Philosophy

**Professional Minimal Aesthetic**
- Clean white background with subtle gradients
- Blue accent color (#1e40af) for primary actions
- Smooth transitions (300ms) for all interactions
- Generous whitespace for clarity
- Clear typography hierarchy

**Color Palette**
- Primary: Blue (#1e40af)
- Accent: Sky Blue (#0ea5e9)
- Text: Dark Slate (#0f172a)
- Background: White (#ffffff)
- Borders: Light Gray (#e2e8f0)

**Animations**
- Tab transitions: Smooth 300ms ease-out
- Procedure entries: Staggered fade-in animations
- Button interactions: 200ms smooth transitions
- Card hover effects: Subtle shadow enhancement

## Features Breakdown

### Tabs Component
- Three tabs with emoji indicators
- Smooth tab switching with Framer Motion animations
- Staggered animation delays for visual appeal

### Disaster Info Card
- Split layout: Image on left, info on right
- Responsive grid that stacks on mobile
- Procedure count indicator

### Procedures Table
- Add new procedures with modal form
- Inline editing with save/cancel options
- Delete with instant removal
- Empty state messaging

### Form Inputs
- Professional input styling
- Textarea for detailed descriptions
- Clear action buttons (Save, Cancel, Delete)
- Form validation (prevents empty submissions)

## Customization Guide

### Changing Colors

Edit `client/src/index.css` in the `:root` section:

```css
:root {
  --primary: var(--color-blue-600);      /* Main color */
  --accent: oklch(0.5 0.2 250);          /* Accent color */
  --border: oklch(0.9 0.005 250);        /* Border color */
  /* ... more colors */
}
```

### Adding New Disasters

1. Add a new entry to `settings.json`:

```json
{
  "id": "hurricanes",
  "name": "Hurricanes",
  "description": "Hurricane emergency procedures",
  "image": "/assets/images/hurricanes.jpg",
  "procedures": [],
  "animationDelay": 300
}
```

2. The dashboard will automatically add a new tab

### Modifying Animations

Edit animation delays in `settings.json` or adjust Framer Motion settings in `Home.tsx`:

```tsx
<motion.div
  initial={{ opacity: 0, y: -10 }}
  animate={{ opacity: 1, y: 0 }}
  transition={{ delay: disaster.animationDelay / 1000 }}
>
```

## Technical Stack

- **React 19** - UI framework
- **TypeScript** - Type safety
- **Tailwind CSS 4** - Styling
- **Framer Motion** - Animations
- **Radix UI** - Accessible components
- **Vite** - Build tool

## Data Persistence

Currently, procedures are stored in component state and will reset on page reload. To persist data:

1. **Option 1**: Use browser localStorage
2. **Option 2**: Upgrade to web-db-user feature for database storage
3. **Option 3**: Export/import procedures as JSON

## Responsive Behavior

- **Mobile**: Single column layout, stacked tabs
- **Tablet**: Two-column grid for images and info
- **Desktop**: Full responsive grid with optimal spacing

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Next Steps

1. Add your disaster images to `client/public/assets/images/`
2. Customize descriptions in `settings.json`
3. Start adding procedures through the dashboard UI
4. (Optional) Upgrade to web-db-user for persistent database storage

## Support

For questions or issues, refer to the component code in `client/src/pages/Home.tsx` or check the Tailwind/Radix UI documentation.
