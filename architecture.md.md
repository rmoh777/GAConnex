# GA Connects Website Architecture

## Overview
This document outlines the architecture for the GA Connects website, a platform designed to connect Georgians to high-speed internet, provide advocacy resources, and share policy expertise in the low-income connectivity field.

## Technology Stack
- **Frontend**: HTML5
- **Styling**: Bootstrap 5 (via CDN)
- **Hosting**: Vercel
- **Future Considerations**: JavaScript functionality to be added later

## File & Folder Structure

```
ga-connects/
├── public/
│   ├── images/
│   │   ├── logo.png
│   │   ├── hero-image.jpg
│   │   └── icons/
│   │       ├── connectivity-icon.svg
│   │       ├── advocacy-icon.svg
│   │       └── policy-icon.svg
│   ├── documents/
│   │   ├── annual-report.pdf
│   │   ├── policy-briefs/
│   │   └── resources/
│   └── favicon.ico
├── styles/
│   └── custom.css
├── pages/
│   ├── index.html
│   ├── about.html
│   ├── connect/
│   │   ├── find-service.html
│   │   ├── assistance-programs.html
│   │   └── digital-literacy.html
│   ├── advocacy/
│   │   ├── current-initiatives.html
│   │   ├── success-stories.html
│   │   └── get-involved.html
│   ├── policy/
│   │   ├── research.html
│   │   ├── briefs.html
│   │   └── legislation.html
│   ├── news/
│   │   ├── index.html
│   │   └── archive.html
│   ├── contact.html
│   └── donate.html
├── includes/
│   ├── header.html
│   ├── footer.html
│   ├── nav.html
│   └── cta-section.html
├── vercel.json
└── README.md
```

## Component Details

### 1. Public Directory
The `public/` directory contains all static assets that will be served directly:

- **images/**: Contains all image assets including:
  - Logo and branding materials
  - Hero images for different pages
  - Icons for services and features
  - Team photos
  - Partner logos

- **documents/**: Houses downloadable resources:
  - Annual reports
  - Policy briefs
  - Educational materials
  - Resource guides

### 2. Styles Directory
Contains custom CSS to extend Bootstrap functionality:

- **custom.css**: Includes:
  - Brand color overrides
  - Custom component styles
  - Additional utility classes
  - Responsive adjustments

### 3. Pages Directory
All HTML pages of the website, organized by section:

- **index.html**: Homepage featuring:
  - Hero section highlighting mission
  - Service overview (connectivity, advocacy, policy)
  - Impact statistics
  - News highlights
  - Call-to-action sections

- **about.html**: Information about the organization:
  - Mission and vision
  - Team members
  - History
  - Partners and supporters

- **connect/**: Resources for internet connectivity:
  - **find-service.html**: Tool to find internet providers by location
  - **assistance-programs.html**: Information on subsidies and assistance
  - **digital-literacy.html**: Educational resources

- **advocacy/**: Advocacy-related content:
  - **current-initiatives.html**: Ongoing campaigns
  - **success-stories.html**: Past wins and impact stories
  - **get-involved.html**: Volunteer opportunities

- **policy/**: Policy expertise section:
  - **research.html**: Research findings and reports
  - **briefs.html**: Policy briefs and white papers
  - **legislation.html**: Current and proposed legislation tracking

- **news/**: Updates and announcements:
  - **index.html**: Latest news
  - **archive.html**: Historical news items

- **contact.html**: Contact information and form

- **donate.html**: Donation information and links

### 4. Includes Directory
Reusable HTML components for consistency across pages:

- **header.html**: Site header with logo and navigation
- **footer.html**: Site footer with links, contact info, and social media
- **nav.html**: Main navigation structure
- **cta-section.html**: Reusable call-to-action component

### 5. Configuration Files

- **vercel.json**: Configuration for Vercel deployment:
  ```json
  {
    "trailingSlash": false,
    "rewrites": [
      { "source": "/api/:path*", "destination": "/api/:path*" }
    ]
  }
  ```

- **README.md**: Documentation for the project

## Data and State Management

Since this is currently a static site without JavaScript, data management will be handled through:

1. **Static Content**: Most content will be hardcoded in HTML files
2. **URL Parameters**: Simple data passing between pages via URL parameters
3. **Form Submissions**: Forms will submit to external services (to be added later)

### External Services (for future implementation)

1. **Form Handling**: Consider using Formspree or a similar service for contact forms
2. **Provider Database**: Future implementation of a database for internet provider lookup
3. **Donation Processing**: Integration with payment processors for donations

## Page Structure Pattern

Each page will follow this general HTML structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title | GA Connects</title>
    <meta name="description" content="Page description">
    
    <!-- Bootstrap CSS from CDN -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    
    <!-- Custom CSS -->
    <link rel="stylesheet" href="/styles/custom.css">
    
    <!-- Favicon -->
    <link rel="icon" href="/public/favicon.ico">
</head>
<body>
    <!-- Include header -->
    <!-- Content specific to the page -->
    <!-- Include footer -->
</body>
</html>
```

## Responsive Design

The site will be built with a mobile-first approach using Bootstrap's responsive grid system:

- **Mobile**: Single column layout
- **Tablet**: Two-column layout for most sections
- **Desktop**: Multi-column layout with sidebar where appropriate

## Performance Considerations

1. **Image Optimization**: All images will be properly sized and compressed
2. **Minimal CSS**: Only using necessary Bootstrap components
3. **Static Generation**: Vercel's static site generation for fast loading

## Accessibility Features

1. **Semantic HTML**: Proper use of headings, landmarks, and ARIA attributes
2. **Keyboard Navigation**: Ensuring all interactive elements are keyboard accessible
3. **Color Contrast**: Meeting WCAG 2.1 AA standards for text contrast
4. **Alt Text**: Descriptive alternative text for all images

## Deployment Strategy

1. **Version Control**: Host code in a GitHub repository
2. **CI/CD**: Connect repository to Vercel for automatic deployments
3. **Environment Branches**:
   - `main` branch deploys to production
   - `staging` branch deploys to staging environment
   - Feature branches for development

## Future Enhancements

Once JavaScript is incorporated, consider:

1. **Interactive Map**: For finding internet service providers by location
2. **Subsidy Calculator**: To help users determine eligibility for assistance programs
3. **Dynamic Content Loading**: For news and resources sections
4. **Search Functionality**: Site-wide search capability
5. **User Accounts**: For saving preferences and accessing personalized resources

## SEO Strategy

1. **Semantic Structure**: Proper use of headings and HTML5 elements
2. **Meta Tags**: Descriptive title and meta description tags
3. **Sitemap**: XML sitemap for search engines
4. **Structured Data**: Schema.org markup for organization information

## Content Update Process

Without a CMS, content updates will require HTML edits:

1. Make changes to the appropriate HTML files
2. Commit changes to the repository
3. Vercel will automatically deploy the updates

---

This architecture provides a solid foundation for the GA Connects website with room for growth and additional functionality as needed. The structure emphasizes clarity, accessibility, and ease of maintenance while using Bootstrap via CDN for styling and Vercel for hosting.
