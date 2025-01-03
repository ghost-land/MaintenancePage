# Ghost Land Maintenance

A multilingual maintenance page for Ghost Land services built with Nuxt.js and Vuetify.

![Version](https://img.shields.io/badge/version-2.0.0-brightgreen.svg)
![License](https://img.shields.io/badge/license-GPL--3.0-blue.svg)

## Features

- 🌍 Internationalization (i18n) support with 7 languages
- 🌓 Automatic dark/light theme based on system preference
- 📊 Real-time maintenance progress indicator
- 📱 Fully responsive Material Design
- ⚡ Dynamic configuration for maintenance periods
- 🔗 Centralized link management

## Build Setup

```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

## Project Structure

```
├── assets/            # Uncompiled assets
├── components/        # Vue components
├── config/           
│   ├── links.js      # Social and external links
│   └── maintenance.js # Maintenance configuration
├── layouts/          
│   └── default.vue   # Default layout with theme toggle
├── locales/          # Translation files
│   ├── en.js         # English
│   ├── fr.js         # French
│   ├── es.js         # Spanish
│   ├── de.js         # German
│   ├── ja.js         # Japanese
│   ├── pt.js         # Portuguese
│   └── ko.js         # Korean
├── pages/            
│   └── index.vue     # Main maintenance page
└── static/           # Static files
    └── favicon.ico   # Site favicon
```

## Configuration

### Maintenance Period

Configure maintenance dates in `config/maintenance.js`:

```js
export default {
  startDate: '2024-01-15T00:00:00Z',
  endDate: '2024-01-20T00:00:00Z'
}
```

### External Links

Manage all external links in `config/links.js`:

```js
export default {
  social: {
    status: 'https://status.ghostland.at/',
    community: 'https://social.ghostland.at/',
    wiki: 'https://wiki.ghosteshop.com/',
    donate: 'https://ko-fi.com/ghostland'
  }
}
```

## Features

### Theme Switching
- Automatically detects system theme preference
- Manual toggle with persistent preference
- Smooth transitions between themes

### Internationalization
- Supports 7 languages out of the box
- Easy language switching via toolbar
- Locale-aware date formatting

### Progress Indicator
- Real-time maintenance progress tracking
- Automatic updates
- Visual progress bar with percentage

## License

This project is licensed under the **GNU General Public License v3.0**.   
Copyright © 2020-2025 Ghost Land Team
